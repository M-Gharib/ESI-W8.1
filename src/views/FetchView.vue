<template>
    <div class="fetch">
      <h1>This is FetchAPI page</h1>
      <get-data :posts="posts"/>
    </div>
  
  </template>
  
  
  <script>
  // @ is an alias to /src
  import getData from "@/components/getData.vue";   
  export default {
    name: "FetchView",
    components: {
      getData
    },
    data: function() {
      return {
      
      posts:[    
      ]
      }
      },
      mounted() {
          fetch('https://jsonplaceholder.typicode.com/posts')
          .then((response) => response.json())
          .then(data => this.posts = data)
          .catch(err => console.log(err.message))
      }
  };
  </script>
  