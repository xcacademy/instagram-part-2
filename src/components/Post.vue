<script setup>
    const props = defineProps(['post'])
</script>

<template>
  <div class="instagram-card">
    <div class="instagram-card-header">
      <img :src="post.userimage" class="instagram-card-user-image"/>
      <a class="instagram-card-user-name" href="https://www.instagram.com/followmeto/">{{ post.username }}</a>
    </div>
  
    <div class="intagram-card-image">
      <img :src="post.postimage" alt="">
    </div>
  
    <div class="instagram-card-content">
      <p class="likes">{{ post.likes }} Likes</p>
      <p><a class="instagram-card-content-user" href="https://www.instagram.com/followmeto/">{{ post.username }}:   </a>{{ post.caption }}</p>
    </div>
    


  </div>
</template>

<style scoped>
    template{
	background-color: blue;
	padding: 60px;
	font-family: 'Droid Sans', sans-serif;

}

a{
  text-decoration: none;
}



.instagram-card{
	background: white;
	border: 1px solid black;
	border-radius: 3px;
	width: 100%;
	max-width: 600px;
	margin: auto;
  box-shadow: 5px 2px 2px 2px grey;
  
}

img {
  width: 100%;
}
.instagram-card-header{
	padding: 20px;
	height: 40px;
}

.instagram-card-image {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.instagram-card-user-image{
	border-radius: 50%;
	width: 40px;
	height: 40px;
	vertical-align: middle;
}

.instagram-card-time{
	float: right;
	width: 80px;
	padding-top:10px;
	text-align: right;
	color: #999;
}

.instagram-card-user-name{
	margin-left:20px;
	font-weight:bold;
  color: #262626;
}

.instagram-card-content{
  padding: 20px;
}

.likes{
  font-weight: bold;
}

.instagram-card-content-user{
  font-weight: bold;
  color: #262626;
}

.hashtag{
  color: #003569;
}

.comments{
  color:#999;
}

.user-comment{
  color: #003569;
}

.instagram-card-footer{
  padding: 20px;
  display: flex;
  align-items: center;
}

hr{
  border: none;
  border-bottom: 1px solid #ccc;
  margin-top: 30px;
  margin-bottom: 0px;
 
}


.footer-action-icons{
  font-size: 16px;
  color: #ccc;
}

.comments-input{
  border: none;
  margin-left: 10px;
  width: 100%;
}


</style>