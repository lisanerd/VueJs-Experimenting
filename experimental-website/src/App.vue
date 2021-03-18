<template>
  <div id="app">
    <img
      alt="Vue logo"
      src="./assets/MathVueJsWebsite.jpeg"
      height="200px"
      width="300px"
    />
    <ParticleBtn :options="btnOps" cls="btn-cls"> Cklick me! </ParticleBtn>
    <button @click="btnOps.visible = !btnOps.visible">toggle</button>
    <ParticleBtn v-on:click="isHidden = true">Hide the text below</ParticleBtn>
    <ParticleBtn v-on:click="isHidden = !isHidden">
      Toggle hide and show
    </ParticleBtn>

    <h1 v-if="!isHidden">Hide me on click event!</h1>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ParticleBtn from "vue-particle-effect-buttons";

export default {
  name: "App",
  components: {
    HelloWorld,
    ParticleBtn,
  },
  data() {
    return {
      btnOps: {
        type: "circle",
        easing: "easeOutQuart",
        size: 6,
        particlesAmountCoefficient: 4,
        oscillationCoefficient: 2,
        color: function () {
          return Math.random() < 0.5 ? "#000000" : "#ffffff";
        },
        onComplete: () => {
          console.log("complete");
        },
        onBegin: () => {
          console.log("begin");
        },
      },
    };
  },
  mounted() {
    let recaptchaScript = document.createElement("script");
    recaptchaScript.setAttribute(
      "src",
      "https://cdn.jsdelivr.net/npm/vue@2.5.13/dist/vue.js"
    );
    document.head.appendChild(recaptchaScript);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
