<template>
  <div id="app">
    <strong> Followers: </strong> {{ followers }}
    <UserProfile/>
  </div>
</template>


<script>
import UserProfile from "./components/UserProfile";

export default {
  name: 'App',   //You can make any key value pairs in export default
  components: { UserProfile }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display:flex;
  flex-direction: column;
  text-align: center;
}
</style>
