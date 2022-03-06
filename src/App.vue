<template>
<div class="first">
<h1>Vuejs App using slot to make a Modal</h1>
</div>
<p>Welcome....</p>
<div v-if="showModal" class="mode">
  <Modal theme="" @close="toggleModal">
     <template v-slot:links>
       <a href="#">sign up now</a>
       <a href="#">more info</a>
    </template>
    <h1>Give away</h1>
    <p>Grab your copy now</p>
    </Modal>
  </div>

  <div v-if="showModalTwo" class="mode">
  <Modal @close="toggleModalTwo">
    <h1>Sign up to the newsletter</h1>
    <p>For updates and promo codes!</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModalTwo">Open Modal2</button>
  <!-- <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div> -->
  <!-- <router-view/> -->
</template>
<script>
import Modal from './components/Modal.vue'
  export default {
    components:{
      Modal
    },
    data(){
      return{
        title: " Hello world",
        header: "Sign up guys",
        text: "Grab your copy now",
        showModal: false,
        showModalTwo: false
      }
    },
    methods:{
       toggleModal(){
         this.showModal = !this.showModal
      },
      toggleModalTwo(){
        this.showModalTwo = !this.showModalTwo
      }
    }
  }
</script>
<style>
.first{
  text-align: center;
}
.mode{
  align-content: center;
}
h1{
  text-align: center;

}
p{
  text-align: center;
}
</style>
