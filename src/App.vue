<template>
  <div><DC/></div>
  
  <div v-for="(i, j) in room" :key="j">
    <h4>{{room[j].title}}</h4>
    <img src="room[j].image">

    <div>{{room[j].price}}원</div>
    
    <button @click="modalChange(j)">{{modal[j]}}상세 정보</button>  
      <div class="black-bg" v-if="modal[j] == true">
        <Modal/>
      </div>
  </div>
  
</template>

<script>
import roomdata from './oneroom.js'
import Discount from './Discount.vue'
import Modal from './modal.vue'
export default {
  name: 'App',
  data(){
    return { 
      modal : [false, false, false, false, false, false],
      room : roomdata
    }
  },
  methods :{
    modalChange(i){
      if (this.modal[i] == false){
          this.modal[i] = true;
      }else{
          this.modal[i] = false;
      }
    }
  },
  components: {
    DC : Discount,
    Modal:Modal,
  }
}
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

.menu {
  background-color: darkslateblue;
  padding : 15px;
  border-radius: 5ps;
}

.menu a {
  color : white;
  padding : 10px;
}

body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 

</style>
