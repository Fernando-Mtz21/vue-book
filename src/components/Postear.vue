<template>
  <div>
    <form action="" v-on:submit.prevent="postear">
      <textarea
        v-model="post"
        name=""
        id=""
        cols="30"
        rows="10"
        placeholder="Postea algo..."
      ></textarea>
      <button type="submit">Publicar</button>
    </form>
  </div>
</template>
<script>
export default {
  name: 'Postear',
  data() {
    return {
      post: '',
    };
  },
  methods: {
    postear() {
      this.$emit('posting', this.post);
      this.post = '';
    },
  },
};
</script>
