<template>
  <div class="app">
    <form class="form" @submit.prevent>
      <h4>Create post</h4>
      <input @input="title = $event.target.value" v-bind:value="title" class="input" type="text" placeholder="title" />
      <input @input="body = $event.target.value" v-bind:value="body" class="input" type="text" placeholder="description" />
      <button class="button" @click="createPost">Add post</button>
    </form>
    <div class="post" v-for="post in posts" v-bind:key="post.id">
      <div><strong>Title:</strong>{{ post.title }}</div>
      <div><strong>Description:</strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        { id: 1, title: "JS", body: "JSJSJS1" },
        { id: 2, title: "JS 2", body: "JSJSJS2222222222222" },
        { id: 3, title: "JS 3", body: "JSJSJS333333333333333333" },
      ],
      title: "333",
      body: "",
    };
  },
  methods: {
    createPost() {
      const newPost = {
        id: new Date(),
        title: this.title,
        body: this.body,
      };
      this.posts.push(newPost);
      this.title = "";
      this.body = "";
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.post {
  border: 2px solid saddlebrown;
  padding: 15px;
  margin-top: 15px;
}

.input {
  width: 100%;
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}
.app {
  padding: 15px;
}

.form {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
}

.button {
  margin-top: 10px;
  align-self: flex-end;
  padding: 5px 10px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
