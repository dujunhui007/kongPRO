<template>
  <div class="topic-contain">
    <input type="text" v-model.trim="secret">
    <button @click="login">确认</button>
  </div>
</template>

<script>
export default {
  name: 'login',
  data() {
    return {
      secret: '',
    };
  },
  methods: {
    login() {
      const that = this;
      this.$store.dispatch('loginAction', {
        secret: this.secret,
        that,
      });
      this.$router.push('/');
    },
  },
};
</script>

<style scoped>
  .topic-contain{
      box-sizing: border-box;
      margin: 90px auto 0;
      max-width: 1600px;
      min-width: 1024px;
      width: 100%;
      height: 600px;
      padding: 0 1.5% 0;
  }
  .topic-contain input{
    border: 1px solid red;
  }
</style>
