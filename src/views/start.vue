<template>
  <div id="ordering">

    <button id="langButton" v-on:click="switchLang()">

      <img id='langPic' v-on:click="switchFlag()" v-if="flag_sv" src='https://cdn.pixabay.com/photo/2017/01/31/16/46/banner-2025451__340.png'  width=40 >
      <img id='langPic' v-on:click="switchFlag()" v-if="flag_en" src='https://upload.wikimedia.org/wikipedia/commons/thumb/f/f2/Flag_of_Great_Britain_%281707%E2%80%931800%29.svg/1024px-Flag_of_Great_Britain_%281707%E2%80%931800%29.svg.png' width=40 >

      {{ uiLabels.language }}
    </button>

    <h1 class="header" align = "center"> {{ uiLabels.startHeader}} <br> {{ uiLabels.startTO}} <br> {{ uiLabels.startHeaderCont }} </h1>

    <div class = "row">

      <div class = "buttonL">
        <button id="orderButtons" type="button" onclick="window.location = '/#/menu_burger';" > {{uiLabels.menu_button}} </button>
      </div>

      <div class = "buttonR">
        <button id="orderButtons" type="button" onclick="window.location = '/#/choose_burger';" > {{uiLabels.choose_button}} </button>
      </div>

    </div>
  </div>
</template>


<script>
import OrderItem from '@/components/OrderItem.vue'
import OrderItemToPrepare from '@/components/OrderItemToPrepare.vue'
//import methods and data that are shared between ordering and kitchen views
import sharedVueStuff from '@/components/sharedVueStuff.js'

export default {
  name: 'Ordering',
  components: {
    OrderItem,
    OrderItemToPrepare
  },
  mixins: [sharedVueStuff], // include stuff that is used in both
  //the ordering system and the kitchen
  data: function(){
    return {

    }
  },
  methods: {


  }
}

</script>


<style scoped>

button:hover {
  cursor: pointer;
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}
.header{
  font-size: 60px;
  color: pink;
  text-shadow: 0 0 3px #875187, 0 0 5px #875187;
}
#ordering {
  margin: auto;
  padding-top: 50px;
  padding-bottom: 200px;
  max-width: 50em;
  background: radial-gradient(lightgray, darkgray);
  /* background-image: url("https://images.unsplash.com/photo-1530554764233-e79e16c91d08?ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80"); */

  color: white;
}

#langButton{
  position: absolute;
  top: 16px;
  right: 250px;
}

#orderButtons {
  /* height: 150px;
  width: 150px; */
  background-color: #BB86BB;
  border-radius: 20px;
  border: 5px solid #875187;
  color: black;
  font-size: 20px;
  padding: 10px 10px 10px 10px;
  margin: 15px 15px 15px 15px;
  text-align: center;
  display: inline-block;

}
.row {
  display: grid;
  padding-top: 100px;
  grid-gap: 15px;
  grid-template-columns:25% 25%;
  justify-content: center;
  justify-items: center;
}

.buttonL{
  grid-column: 1;
}
.buttonR {
  grid-column: 2;
}


</style>
