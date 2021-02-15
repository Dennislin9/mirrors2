<template>
    <div class="container">
      <button class="PlayerMandje"> Show Players </button>
    <Speler
          :name="player.naam"
          :value="player.waarde"
          :img="player.img"
          :color="player.color"
          v-for="(player, index) in players"
          :key="index"
          
        />

        <Cart/>
       
    </div>
</template>

<script>
import Speler from '@/components/Speler';
 import Cart from '@/components/Cart';
export default {
  components: { Speler,Cart },
  computed: {
    players() {
      return this.$store.state.spelersWaarde;
    },
  },  
}
</script>

<style scoped>
.container{
    height:100vh;
    width:100vw;
    background: mediumaquamarine;

}
.PlayerMandje{
  height: 50px;
  min-width: 150px;
   background: linear-gradient(33deg,red,white,blue);
  border: none;
  display: block;
  border-radius: 20px;
  font-weight: bold;
  color: black;
  outline: none;
}

</style>