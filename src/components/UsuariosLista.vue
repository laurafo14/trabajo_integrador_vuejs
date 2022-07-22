<template>
  <div>
    <h3>Cantidad de usuarios: {{ this.usuarios.length }}</h3>    
    <ul>
      <li v-for="usuario in usuarios" :key="usuario.id">
        <span> {{usuario.name}} - {{usuario.email}} - </span>
        
        <router-link :to="`/usuario/${usuario.id}`" class="btn btn-primary">Posts</router-link>
      </li>
    </ul>
    
  </div>
</template>

<script>
import {mapActions, mapGetters} from "vuex"

export default {
  name: 'UsuariosLista',
  data(){
    return{
    }
  },
  computed: {
    ...mapGetters(['usuarios'])
  },
  async created() {
    this.fetchUsuarios();
  },
  methods: {
    ...mapActions(['fetchUsuarios']),
    verDetalle(){
      //return this.$store.dispatch("verDetalle")
    }
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
router-link {
  color: #42b983;
}
</style>
