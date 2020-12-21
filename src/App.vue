<template>
  <div id="app">
    <UserCard 
    v-bind:cats="cats"
    />
  </div>
</template>

<script>
import UserCard from "./components/UserCard.vue";
export default {
  name: "app",
  components: {
    UserCard
  },
  data() {
      info: [],
  },
  methods: {
    update() {
    this.axios.get(" http://188.225.47.187/api/cats/random-fact.php")
      .then(response => {
        this.info = response.data;
      });
    }
  },
  mounted() {
    this.update()
  }
};
</script>
<style>
  button{
    width:200px;
    height:200px;
  }
</style>