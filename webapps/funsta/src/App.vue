<template>
  <div id="app">
    <PostCard v-for="post of posts"
      :post="post"
    />
  </div>
</template>

<script>
import PostCard from './components/PostCard.vue';

export default {
  name: 'App',
  data(){
    return{
      posts : [
      {
        userName: "ash",
        userId: 1,
        description: "Such a beautiful day",
        img: import("./postImages/post1.jpeg"),
        likedUsers: ["ben", "cara", "dan"],
        likesCount: 3,
        comments: [
          { userName: "ben", userID: 2, description: "Indeed it is!" },
          { userName: "cara", userID: 3, description: "Lovely photo!" }
        ],
        commentsCount: 2
      },
      {
        userName: "ben",
        userId: 2,
        description: "Having a great time at the beach",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "dan", "eve"],
        likesCount: 3,
        comments: [
          { userName: "ash", userID: 1, description: "Enjoy!" },
          { userName: "dan", userID: 4, description: "Looks fun!" }
        ],
        commentsCount: 2
      },
      {
        userName: "cara",
        userId: 3,
        description: "My new painting",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "ben", "eve", "fay"],
        likesCount: 4,
        comments: [
          { userName: "ash", userID: 1, description: "Beautiful!" },
          { userName: "ben", userID: 2, description: "Amazing work!" }
        ],
        commentsCount: 2
      },
      {
        userName: "dan",
        userId: 4,
        description: "Hiking adventure",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["cara", "fay", "glen"],
        likesCount: 3,
        comments: [
          { userName: "cara", userID: 3, description: "Great view!" },
          { userName: "fay", userID: 6, description: "I want to go there!" }
        ],
        commentsCount: 2
      },
      {
        userName: "eve",
        userId: 5,
        description: "Delicious homemade cake",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "cara", "dan", "glen"],
        likesCount: 4,
        comments: [
          { userName: "ash", userID: 1, description: "Yummy!" },
          { userName: "glen", userID: 7, description: "Looks tasty!" }
        ],
        commentsCount: 2
      },
      {
        userName: "fay",
        userId: 6,
        description: "Sunset by the lake",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "ben", "eve", "helen"],
        likesCount: 4,
        comments: [
          { userName: "ben", userID: 2, description: "So peaceful!" },
          { userName: "eve", userID: 5, description: "Love this!" }
        ],
        commentsCount: 2
      },
      {
        userName: "glen",
        userId: 7,
        description: "My pet cat",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["cara", "eve", "fay"],
        likesCount: 3,
        comments: [
          { userName: "cara", userID: 3, description: "Cute cat!" },
          { userName: "fay", userID: 6, description: "Adorable!" }
        ],
        commentsCount: 2
      },
      {
        userName: "helen",
        userId: 8,
        description: "Coffee time",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "ben", "dan", "ian"],
        likesCount: 4,
        comments: [
          { userName: "ash", userID: 1, description: "Enjoy!" },
          { userName: "dan", userID: 4, description: "Love coffee!" }
        ],
        commentsCount: 2
      },
      {
        userName: "ian",
        userId: 9,
        description: "Workout session",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ben", "cara", "eve", "helen"],
        likesCount: 4,
        comments: [
          { userName: "ben", userID: 2, description: "Keep it up!" },
          { userName: "cara", userID: 3, description: "You got this!" }
        ],
        commentsCount: 2
      },
      {
        userName: "jack",
        userId: 10,
        description: "City lights",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "cara", "dan", "glen"],
        likesCount: 4,
        comments: [
          { userName: "ash", userID: 1, description: "Great shot!" },
          { userName: "glen", userID: 7, description: "Nice view!" }
        ],
        commentsCount: 2
      },
      {
        userName: "kate",
        userId: 11,
        description: "New recipe experiment",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ben", "eve", "fay"],
        likesCount: 3,
        comments: [
          { userName: "ben", userID: 2, description: "Looks delicious!" },
          { userName: "eve", userID: 5, description: "I want to try it!" }
        ],
        commentsCount: 2
      },
      {
        userName: "liam",
        userId: 12,
        description: "Mountain biking",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "dan", "glen"],
        likesCount: 3,
        comments: [
          { userName: "ash", userID: 1, description: "Nice ride!" },
          { userName: "dan", userID: 4, description: "Looks awesome!" }
        ],
        commentsCount: 2
      },
      {
        userName: "mia",
        userId: 13,
        description: "New hairstyle",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ben", "eve", "fay", "ian"],
        likesCount: 4,
        comments: [
          { userName: "ben", userID: 2, description: "Looks great!" },
          { userName: "helen", userID: 8, description: "Love it!" }
        ],
        commentsCount: 2
      },
      {
        userName: "nina",
        userId: 14,
        description: "Nature walk",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ash", "cara", "glen"],
        likesCount: 3,
        comments: [
          { userName: "ash", userID: 1, description: "Beautiful scenery!" },
          { userName: "glen", userID: 7, description: "So relaxing!" }
        ],
        commentsCount: 2
      },
      {
        userName: "oliver",
        userId: 15,
        description: "My latest drawing",
        img: import("./postImages/post2.jpeg"),
        likedUsers: ["ben", "dan", "fay"],
        likesCount: 3,
        comments: [
          { userName: "ben", userID: 2, description: "Nice work!" },
          { userName: "fay", userID: 6, description: "Impressive!" }
        ],
        commentsCount: 2
      }
    ]
  
    }
  },
  components: {
    PostCard
  }
}
</script>

<style>
body {
  font-family: Arial, sans-serif;
  background-color: #f0f0f0;
  margin: 0;
  padding: 0;
}

#app {
  padding: 20px;
}
</style>
