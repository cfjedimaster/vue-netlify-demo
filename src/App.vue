<template>
  <div id="app">
    <h1>Welcome to Your Vue.js App</h1>
    <p>
    Message from severless function: {{ msg }}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg:''
    }
  },
  async created() {
    let resp = await fetch('/.netlify/functions/hello-world?name=ray');
    this.msg = (await resp.json()).message;
  }
}
</script>