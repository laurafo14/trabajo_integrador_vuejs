<template>
  <div> 
    <h3>Cantidad de post: {{ this.posts.length }}</h3>    
    <ul>
      <li v-for="post in posts" :key="post.id">
        <span> {{post.title}} <br> {{post.body}} <br></span>
        -------------------------------------
      </li>
    </ul>
    
  </div>
</template>

<script>
import {mapActions, mapGetters} from "vuex"

export default {
  name: 'UsuarioPosts',
  props: ["id"],
  data(){
    return{
    }
  },
  computed: {
    ...mapGetters(['posts'])
  },
  async created() {
    this.fetchPosts(this.id);
  },
  methods: {
    ...mapActions(['fetchPosts'])
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none; 
  padding: 10px;
}
li {
  display: list-item; 
  margin: 10px 10px;
}
</style>
