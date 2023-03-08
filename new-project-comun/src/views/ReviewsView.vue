<template>
  <div class="tituloYBtn">
    <h1>Reviews</h1>
    <button @click="esconder = true" class="btn btn-primary">Write your review</button>
  </div>
      <div v-show="esconder" class="overlay">
        <div class="tarjetaEscondida">
          <h3>Your Review</h3>
            <input v-model="newName" type="text" name="name" id="name" placeholder="Your name">
            <input v-model="newTitle" type="text" name="title" id="title" placeholder="Movie title">
            <textarea v-model="newNote" name="notes" id="notes" cols="30" rows="5" placeholder="Opinion"></textarea>
            <div class="btns">
              <button @click="addNote" class="btn btn-primary">Post</button>
              <button @click="esconder = false" class="btn btn-primary bg-danger">Close</button>
          </div>
        </div>
      </div>




    <div>
      <ReviewNote :reviews="reviews"/>

    </div>

  </template>

  <script setup>

  import { reactive, ref } from "vue";
  import ReviewNote from '../components/ReviewNote/ReviewNote.vue'

  const newNote = ref("")
  const newTitle = ref("")
  const newName= ref("")
  const esconder = ref(false)
  const reviews = reactive([
   {
    name:"Juana",
    title: "Wakankanda",
    text:"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Harum sequi deleniti accusantium quae?",
    date: new Date
   },
   {
    name:"Dexter",
    title: "Pinotxo",
    text:"Lorem ipsum, dolor sit amet consectetur adipisicing elit. Harum sequi deleniti accusantium quae?",
    date: new Date
   }
  ])


  const addNote = () => {

    reviews.push({
      name: newName.value,
      title: newTitle.value,
      text: newNote.value,
      date: new Date()
    })

    newName.value = "";
    newNote.value = "";
    newTitle.value = "";
    esconder.value = false;
  }




  </script>

    <style scoped>
    .tarjetaEscondida{
      width: 40%;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      margin: 0 auto;
      border: 1px solid;
      background-color: rgb(161, 175, 145);
      padding: 1rem;
      margin-top: 5rem;
    
    }
      .overlay{
        position: absolute;
        z-index: 10;
        background-color: rgba(0, 0, 0, 0.719);
        width: 100%;
        height: 100%; 
      }
      button{
        margin: 0 1rem;
        width: 10rem;
      }
      .btns{
        margin-top: 1rem;
        display: flex;
      }
      input{
        margin-top: 1rem;
        width: 25rem;
      }
      textarea{
        margin-top: 1rem;
        width: 25rem;
      }

      .tituloYBtn{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 30rem;
        margin-bottom: 2rem;
        margin-top: 3rem;
      }


     
    </style>