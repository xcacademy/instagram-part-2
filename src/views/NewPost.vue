<script setup>
import Navbar from '../components/Navbar.vue';


function submitPost() {
    let username = document.getElementById('postname').value
    let userimage = document.getElementById('userimage').value
    let imagelink = document.getElementById('imagelink').value
    let likes = document.getElementById('likes').value
    let caption = document.getElementById('caption').value
    

    let params = {
    method: 'POST',
    headers: {
      'Accept': 'application/json',
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({username: username, likes: likes, postimage: imagelink, likes: likes, caption: caption, userimage: userimage})
  }



    fetch('https://66ccd18b8ca9aa6c8cc8cbc0.mockapi.io/post', params)
    .then(response => response.json())
    .then(json => {
        console.log(json)
    })
}

</script>

<template>
    <Navbar></Navbar>

    <div class="flex">
   
            <label for="postname">Username: </label>
            <input type="text" id="postname">
    
            <label for="userimage">User Image: </label>
            <input type="text" id="userimage">
        
            <label for="imagelink">Image Link: </label>
            <input type="text" id="imagelink">
       
            <label for="likes">Likes: </label>
            <input type="text" name="likes" id="likes">
      
            <label for="caption">Caption: </label>
            <input type="text" id="caption">
    
       

         <button @click="submitPost()">Submit!</button>
    </div>

    
</template>


<style scoped>
    .flex {
        display: flex;
        flex-direction: column;
        justify-content: left;
        align-items: center;
        gap: 10px
    }   

    button {
      background-color: white; 
      color: #008CBA;
      padding: 15px 22px;
      text-align: center;
      text-decoration: underline;
      font-size: 20px;
      border: none;
      box-shadow: none;
      cursor: pointer;
  
    
    }

    /* input {
        position: absolute;
        left: 900px;
    } */


</style>