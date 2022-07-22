<template>
  <div class="home">
    <img alt="Vue logo" width="30" src="../assets/logo.png">
    <UsuarioPosts :id="this.id"/>
  </div>
</template>

<script>
// @ is an alias to /src
import UsuarioPosts from '@/components/UsuarioPosts.vue'

export default {
  name: 'UsuarioView',
  props: ["id"],
  components: {
    UsuarioPosts
  }
}
</script>