<template>
  <div class="home">
    <h1>ToDo list</h1>
    <p>Esta app de prueba es una clásica ToDo list</p>
    <button v-on:click="gotoList">Tocá para comenzar</button>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

// const router = this.$router;
console.log(this);

export default {
  name: "home",
  methods: {
    gotoList() {
      this.$router.push({ name: "list" });
    }
  }
};
</script>
