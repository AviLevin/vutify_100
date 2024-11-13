<template>
  <div
    class="d-flex flex-column justify-content align-center"
    style="row-gap: 15px"
  >
    <br />
    <h1 style="font-weight: bold; font-family: Trebuchet MS">{{ title }}</h1>

    <div>
      <v-btn
        color="blue"
        rounded="lg"
        variant="outlined"
        type="button"
        @click="count++"
        >+
      </v-btn>
      <v-btn variant="outlined" color="blue" rounded="lg" type="button">
        {{ count }}</v-btn
      >
      <v-btn
        variant="outlined"
        color="blue"
        rounded="lg"
        type="button"
        @click="count--"
      >
        -</v-btn
      >
    </div>
    <div>
      <!-- <v-btn type="button" @click="title = 'welcome'">Change Title</v-btn> -->
      <!-- <v-btn color="#5865f2" size="small" type="button" @click="toggleTitle"
        >Change Title</v-btn
      > -->

      <zz-button @click="toggleTitle">Change Title</zz-button>
      <br />
      <br />
      <zz-button @click="toggleShowBooks">
        <span v-if="showBooks">Hide Books</span>
        <!-- <span v-if="!showBooks">Show Books</span> -->
        <span v-else>Show Books</span>
      </zz-button>
      <br />
      <transition name="grow-shrink">
        <div v-if="showBooks">
          <v-img
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTudN8Com396LDgdLI1R57J7754r1KnnFWHAA&s"
            alt="Vue logo"
            class="image-style"
          />
        </div>
      </transition>
    </div>
  </div>
</template>  
  
<script setup>
import { ref } from 'vue';
import ZzButton from '/src/components/ZzButton.vue';
//import { ZzButton } from 'ZzButton.vue'

defineProps({
  msg: String,
});

             const title = ref('hello');
const count = ref(1);
const showBooks = ref(true);

function                 toggleTitle() {
  title.value = title.value === 'hello' ? 'welcome' : 'hello';
}

function toggleShowBooks() {
  // this.showBooks.value = !this.showBooks.value;
  showBooks.value = !showBooks.value;
}
</script>

<style scoped>



.read-the-docs {
  color: #888;
}

.grow-shrink-enter-active {
  animation: growShrink 1s ease-out;
  transform: rotateY(180deg);
}

@keyframes growShrink {
  0% {
    transform: scale(0.2);
    opacity: 0;
  }
  50% {
    transform: scale(1.3);
    opacity: 1;
  }
  100% {
    transform: scale(1);
    /* transform: rotateY(180deg); */
    transform-style: preserve-3d;
    opacity: 1;

  }
}
</style>
