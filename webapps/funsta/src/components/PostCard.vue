

<template>
    <div class="post-card">
      <div class="post-header">
        <h3>{{ post.userName }}</h3>
      </div>
      <div class="post-image">
        <img :src="postImage" alt="Post image"/>
      </div>
      <div class="post-description">
        <p>{{ post.description }}</p>
      </div>
      <div class="layout-row">
        <div class="post-likes layout-row">
            <span>❤️  </span> <div @click="toggleLikes">{{ post.likesCount }}</div>
            <!-- <ul v-if="showLikes">
            <li v-for="user in post.likedUsers" class="overflow-auto" :key="user">{{ post.user }}</li>
            </ul> -->
        </div>
        <div class="post-comments layout-row" @click="toggleComments" style="cursor: pointer;">
            <span>💬  </span><div > {{ post.commentsCount }}</div>
            
        </div>
      </div> 
      <div>
        <ul v-if="showComments">
            <li v-for="comment in post.comments" class="overflow-auto" :key="comment.userID">
                <strong>{{ comment.userName }}:</strong> {{ comment.description }}
            </li>
        </ul>
      </div>     
    </div>
  </template>
  
  <script>
  export default {
    name: 'PostCard',
    props: {
      post:Object
    },
    data() {
      return {
        postImage : null,
        showLikes: false,
        showComments: false
      };
    },
    mounted(){
        if(this.post.img instanceof Promise){
            this.post.img.then(res=>{
                this.postImage = res.default;
            })
        }else{
            this.postImage = this.post.img;
        }
    },
    methods: {
      toggleLikes() {
        this.showLikes = !this.showLikes;
      },
      toggleComments() {
        this.showComments = !this.showComments;
      }
    }
  }
  </script>
  
  <style scoped>
  .post-card {
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 16px;
    width: 400px;
    margin: 16px auto;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    background-color: #fff;
  }
  
  .post-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 16px;
  }
  
  .post-image img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-bottom: 16px;
  }
  
  .post-description {
    margin-bottom: 16px;
  }
  
  .post-likes, .post-comments {
    width: 40px;

    margin-left: 6px;
    margin-right: 6px;
  }
  
  .post-likes ul, .post-comments ul {
    list-style: none;
    padding: 0;
    width :400px;
  }
  
  .post-likes li, .post-comments li {
    margin: 4px 0;
    width :400px;

  }
  
  .post-likes p, .post-comments p {
    cursor: pointer;
  }
  </style>
  