<template>
  <div class="home">
    <div>
      <h2 ref="appTitleRef">{{ appTitle }}</h2>
      <h3>{{ counterData.title }}</h3>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>
    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" v-autofocus />
    </div>
  </div>
</template>

// script setup
<script setup>
// reactive objects
import {
  ref,
  reactive,
  computed,
  watch,
  onBeforeUnmount,
  onMounted,
  onBeforeMount,
  onUnmounted,
  onBeforeUpdate,
  onUpdated,
} from "vue";

import { vAutofocus } from "@/directives/vAutofocus";
const counterData = reactive({
  count: 0,
  title: "Countertile",
});

//computed property

const oddOrEven = computed(() => {
  if (counterData.count % 2 === 0) return "even";
  return "odd";
});

//watcher
watch(
  () => counterData.count,
  (newCount) => {
    console.log("newCount", newCount);
    if (newCount === 20) {
      alert("yaaay!!!");
    }
  }
);

//template refs

const appTitleRef = ref(null);

onMounted(() => {
  console.log(`The app title is ${appTitleRef.value.offsetWidth}px wide`);
  console.log(`The app title is ${appTitleRef.value.offsetHeight}px high`);
});

//onBeforeUpdated, fired befre template is updated
onBeforeUpdate(() => {
  console.log("onBeforeUpdate");
});

// fired when updated
onUpdated(() => {
  console.log("onUpdated");
});

//beforeMount Hook, this fires before the component is mounted
onBeforeMount(() => {
  console.log("onBeforeMount");
});

//onMounted, when the component is mounted
onMounted(() => {
  console.log("onMounted");
});

//
onBeforeUnmount(() => {
  console.log("onBeforeUnmounted");
});

onUnmounted(() => {
  console.log("onUnmounted");
});

//non-reactive object
const appTitle = "Counter App";

//using methods, we'll add props to increase or decrease the counter by a specific number.

const increaseCounter = (amount) => {
  counterData.count += amount;
};

const decreaseCounter = (amount) => {
  counterData.count -= amount;
};
</script>

<!--
//script setup
<script setup>
//  normal ref 
import { ref } from "vue";

const counter = ref(0),
  counterTitle = ref("Countertile");


const increaseCounter = () => {
  counter.value++;
};

const decreaseCounter = () => {
  counter.value--;
};
</script>
-->

<!--
// Composition API
<script>
import { ref } from "vue";
export default {
  //setup function
  setup() {
    const counter = ref(0);
    const increaseCounter = () =>{
      counter.value++
    }
    const decreaseCounter = () =>{
      counter.value--
    }
    return {
      counter,
      increaseCounter,
      decreaseCounter
    };
  },
};
</script>
-->

<!--
// Option API
<script>
export default {
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    increaseCounter(){
      this.counter++
    },
    decreaseCounter(){
      this.counter--
    }
  },
};
</script>
-->

<style>
.home {
  text-align: center;
  padding: 20px;
}
.btn,
.counter {
  font-size: 40px;
  margin: 10px;
}
</style>
