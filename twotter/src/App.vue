<template>
  <div id="app">
    @{{ user.username }} - {{ fullName }}
    <strong> Followers: </strong> {{ followers }}
    <button @click="followUser"> 
      Follow 
    </button>
  </div>
</template>


<script>

export default {
  name: 'App',   //You can make any key value pairs in export default
  data(){        //data is inbuilt hence not a key value pair
    return {
      followers: 0,
      user: {
        id:1,
        username: '_sk8erBoi',
        firstName: 'Kaustubh',
        lastName: 'Shetty',
        email: 'kaustubhshetty8@gmail.com',
        isAdmin: true
      }
    }
  },
  watch : { //watches a datapoint, and when it changes you can run a function //like setstate
            //watch will automatically run the functions inside it to check
    followers(newFollowerCount , oldFollowerCount){
      if(oldFollowerCount < newFollowerCount) {
        console.log(`${this.user.username} has gained a follower!`);
      }
    }
  },
  computed: {
      fullName() {    //this function will generate a full Name
        return `${this.user.firstName} ${this.user.lastName}`;
      }
    },
  methods: {
    followUser(){
      this.followers++;
    }  
  }, 
  mounted() {   //This is like init state of Flutter //Also called life cycle hook
    this.followUser();
  }
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
