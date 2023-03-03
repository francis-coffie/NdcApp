<!-- eslint-disable no-unused-vars -->
<!-- eslint-disable no-unused-vars -->
<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable no-unused-vars -->

<template>
  <div class="home">
    <div class="toogle-button mt-5 mb-5">
      <div class="container nav-f">
        <button
          @click="pullToggle('sailers')"
          class="labelButton btn btn-outline-success text-green p200 btn-shadow text-center hover:bg-[#B5461D] bg-[#8F95B2] focus:outline-none focus:ring-2 focus:bg-[#DD5928]"
          :class="sailersToggle ? 'active-toogle-button' : 'inactive-toogle-button'"
        >
          1
        </button>
        <p class="block N800 P200 ml-5 mr-5 mt-2 text-lowercase fs-6 px-1">
          Sailers<span class="arrow-color">></span>
        </p>
        <button
          @click="pullToggle('ase_Park')"
          class="labelButton text-green btn-shadow text-center hover:bg-[#B5461D] bg-[#8F95B2] btn btn-outline-success focus:outline-none focus:ring-2 focus:bg-[#DD5928] active:bg-[#DD5928]"
          :class="aseparkToggle ? 'active-toogle-button' : 'inactive-toogle-button'"
        >
          2
        </button>
        <p class="block N800 P200 ml-5 mr-5 mt-2 text-lowercase fs-6 px-1">
          Ase_Park <span class="arrow-color">></span>
        </p>
        <button
          class="labelButton btn btn-outline-success text-green btn-shadow text-center hover:bg-[#B5461D] bg-[#8F95B2] focus:outline-none focus:ring-2 focus:bg-[#DD5928] active:bg-[#DD5928]"
        >
          3
        </button>
        <!-- <p class="block N800 P200 ml-5 mr-5 mt-2 text-lowercase fs-6 px-3">
          Ase_Park<span class="arrow-color"> ></span>
        </p> -->
        <!-- <span class="bg-red-600 border-2 border-blue-700">Hello world</span> -->
      </div>
      <hr />
    </div>
  </div>
  <AseParkComponent v-if="sailersToggle" />
  <SailersComponent v-if="aseparkToggle" />
</template>

<script setup>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
// eslint-disable-next-line no-unused-vars
import AseParkComponent from "../components/pullstatios/SailersComponent.vue";
// eslint-disable-next-line no-unused-vars
import SailersComponent from "../components/pullstatios/AseParkComponent.vue";

import { ref } from "vue";
const sailersToggle = ref(true);
const aseparkToggle = ref(false);

// eslint-disable-next-line no-unused-vars
const pullToggle = (view) => {
  if (view === "sailers") {
    sailersToggle.value = true;
    aseparkToggle.value = false;
  } else if (view === "ase_Park") {
    sailersToggle.value = false;
    aseparkToggle.value = true;
  } else {
    // this.sailersToggle = false;
    // this.aseparkToggle = true;
  }
};
</script>
<style scoped>
.labelButton {
  border-radius: 50%;
  justify-content: center;
  align-items: center;
  width: 34px;
  height: 35px;
}
.nav-f {
  display: flex;
}
.arrow-color {
  color: green;
  font-size: large;
}

.active-toogle-button {
  background-color: #198754;
  color: #ffffff;
}
</style>
