<template>
  <div class="home">
    <img alt="Vue logo" width="30" src="../assets/logo.png">
    <UsuariosLista/>
  </div>
</template>

<script>
// @ is an alias to /src
import UsuariosLista from '@/components/UsuariosLista.vue'

export default {
  name: 'HomeView',
  components: {
    UsuariosLista
  }
}
</script>
