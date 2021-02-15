<template>
  <div class="speler" v-bind:style="`background:${color};`">
    <img v-bind:src="img" alt="" />
    <p>&euro; {{ value }}</p>
    <button class="buy" v-on:click="buy(name)">kopen</button>
  </div>
</template>


<script>
import VanillaTilt from "vanilla-tilt";
export default {
  props: ["name", "value", "color", "img"],

  mounted() {
    //this.buy(this.name)

    console.log(this.color);
    const elements = document.querySelectorAll(".speler");
    elements.forEach((element) => {
      VanillaTilt.init(element, {
        scale: 1.1,
      });
    });
    console.log(elements);

    //  console.log(this.spelers);
  },
  methods: {
    buy(spelerNaam) {
      alert(`You just bought ${spelerNaam}`);
      console.log("werkt");
    },
    
    },
};
</script>

<style scoped>
body {
  width: 100vw;
  height: 100vh;
  position: absolute;
  text-align: center;
}
.buy {
  height: 30px;
  width: 150px;
  margin: 0 auto;
  margin-top: 2px;
  border-radius: 20px;
  font-weight: bold;
  background: linear-gradient(30deg, black, black);
  border: none;
  display: block;
  color: white;
  outline: none;
  transform: translateZ(100px);
}

.speler {
  min-height: 500px;
  width: 250px;
  float: left;
  border-radius: 10px;
  margin: 30px;
  margin-top: 50px;
  transform-style: preserve-3d;
  transform: perspective(1000px);
}
.speler img {
  margin-top: 50px;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
  width: 90%;
  margin-bottom: 1px;
  transform: translateZ(100px);
}

.speler p {
  margin-top: 5px;
  font-size: 30px;
  font-weight: bold;
  margin-top: 20px;
  color: white;
  text-align: center;
}
</style>