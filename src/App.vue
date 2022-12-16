<template>
  <div>
    <button @click="increaseLikeCount">Like</button>
    <button v-on:click="increaseDislikeCount">Dislike</button>
  </div>
  <div>
    Likes count <strong>{{ likes }}</strong>
  </div>
  <div>
    Dislike count <strong>{{ dislike }}</strong>
  </div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislike: 0,
    };
  },
  methods: {
    increaseLikeCount() {
      this.likes += 1;
    },
    increaseDislikeCount() {
      this.dislike += 1;
    },
  },
};
</script>

<style></style>
