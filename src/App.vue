<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="What is your favorite color?"/>
    <br>
    <section class="hsl-sliders">
        Hue = {{this.hue}}
        <br>
      <input type="range" min="0" max="360" v-on:input="HueUpdated" v-model="hue"/>
      </section>
      <section>
        Lightness = {{this.lightness}}
        <br>
      <input type="range" min="0" max="100" v-on:input="LightnessUpdated" v-model="lightness"/>
      </section>
      <section>
        Saturation = {{this.saturation}}
        <br>
      <input type="range" min="0" max="100" v-on:input="SaturationUpdated" v-model="saturation"/>
      </section>
      <section>
        Transparency = {{this.transparency}}
        <br>
      <input type="range" min="0" max="100" v-on:input="TransparencyUpdated" v-model="transparency"/>
      </section>
  <section id="color-box" :style="backgroundColor"> 
  </section>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  // name: "color-box",
  components: {
    HelloWorld
  },
  

  data: function() {
    return {
      hue: 180,
      saturation: 50,
      lightness: 50,
      transparency: 50
    };
  },
  computed:{
    backgroundColor:function(){
      return `background-color : hsla(${this.hue}, ${this.saturation}%, ${this.lightness}%, ${this.transparency}%)`
    }
  },
  methods: {
    HueUpdated: function() {
      console.log("Hue was updated", this.hue);
      // this.bgc.hue = this.hue;
    },
    SaturationUpdated: function() {
      console.log("Saturation was updated", this.saturation);
      // this.bgc.saturation = this.saturation;

    },
    LightnessUpdated: function() {
      console.log("Lightness was updated", this.lightness);
      // this.bgc.lightness = this.lightness;
    },
    TransparencyUpdated: function() {
      console.log("Transparency was updated", this.transparency);
    },
  }
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

#color-box {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 10em;
  margin: 3px;
  height: 40vh;
}

#hsl-sliders {
  height: 3vh;
  font-size: large;
}

</style>
