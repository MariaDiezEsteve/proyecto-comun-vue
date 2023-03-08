<template>
 
    <div class="container">
      <div>
        <h1>Write your opinion about your favorite film</h1>
            <input v-model="newName" type="text" name="name" id="name" placeholder="Input a name">
            <input v-model="newTitle" type="text" name="title" id="title" placeholder="Input a title">
            <textarea v-model="newNote" name="notes" id="notes" cols="30" rows="10"></textarea>
            <button @click="addNote" class="btn btn-primary">Create a opinion</button>
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

  const reviews = reactive([])


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
  }



  
  </script>

    <style scoped>
    .container{
      display: flex;
      flex-direction: column;
      width: 50%;
      padding: 2rem ;
    }

    #name, #title{
      margin-top: 2rem;
      width: 50%;
    }
 
    </style>