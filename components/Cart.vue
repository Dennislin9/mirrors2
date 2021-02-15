<template>
  <div class="container">
    <div class="winkelmand" :style="winkelmandjestyle">
       <ul>
       <li>
           hjtyjtyj
           </li> 
        </ul>
    </div>
    <div class="overlay" v-on:click="hideCart"></div>
   
  </div>
</template>

<script>
export default {
    
    data() {
    return {
      winkelmandjestyle: {
        transform: "translateX(100%)",
      },
    };
  },
  mounted() {
      document.querySelector(".overlay").style["display"]="none"
     this.$store.dispatch("getcart");

      const button = document.querySelector(".PlayerMandje");
    button.addEventListener("click", (event) => {
      this.showCart();
      console.log("geklikt knop")
    });
  },

  methods: {
    showCart() {
      console.log("triggerrrr");
      this.winkelmandjestyle.transform = "translateX(0)";
      console.log(this.winkelmandjestyle);
      document.querySelector(".overlay").style["display"]="block"
    },
     hideCart() {
      console.log("werkt");
      this.winkelmandjestyle.transform = "translatex(100%)";
      document.querySelector(".overlay").style["display"]="none"
    },
  },
  
};
</script>

<style >
.overlay {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 100%;
  background:none;
}
.winkelmand {
  width: 500px;
  height: 100%;
  background: whitesmoke;
  align-content: right;
  position: absolute;
  right: 0;
  bottom: 0;
  padding: 10px;
  transition: all 0.3s ease;
  z-index: 2;
}

</style>