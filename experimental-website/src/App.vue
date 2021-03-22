<template>
  <div id="app">
    <particles-bg type="lines" :bg="true" />
    <h1>All About Math!</h1><div><br><action-text-attachment presentation="gallery"></action-text-attachment></div>
    <img
      alt="Vue logo"
      src="./assets/MathVueJsWebsite.jpeg"
      height="200px"
      width="300px"
    />
    <h2>Absolute Values</h2><div>Today we will be learning about absolute values, and how they are used in context. Press the "Next" button below to read more.<br><action-text-attachment presentation="gallery"></action-text-attachment></div>
    <h2></h2><div><br><action-text-attachment presentation="gallery"></action-text-attachment></div>

    <ParticleBtn :visible.sync="btnOps.visible" :options="btnOps" cls="btn-cls"> Next </ParticleBtn>

    <h3 v-if="!isHidden">The first thing we will be covering today is the biggest question there is; what is "absolute value"? Well, to answer that question, we need to know what makes up an absolute value.</h3>
    <h2 v-if="!isHidden">Absolute Value Bars</h2>
    <h3 v-if="!isHidden">Absolute value bars are the bars that you put around an intger to get it's absolute value.</h3>


  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import ParticleBtn from "vue-particle-effect-buttons";
import { ParticlesBg } from "particles-bg-vue";


export default {
  name: "App",
  components: {
    HelloWorld,
    ParticleBtn,
    ParticlesBg,
  },
  data() {
    return {
      isHidden: true,
      btnOps: {
        type: "circle",
        easing: "easeOutQuart",
        color: function () {
          return Math.random() < 0.5 ? "#000000" : "#ffffff";
        },
        onComplete: () => {
          console.log("complete");
          this.isHidden = !this.isHidden
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
  font-size: 2rem;
  text-align: center;
  color: #dcdae7;
  margin-top: 60px;
}
/* html, 
body {
    margin: 0;
    padding: 0;
    background-color:rgb(228, 238, 230);
} */
</style>
