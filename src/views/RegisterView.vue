<template>
  <div class="container">
   <register-component/>
  </div>
</template>

<script>
// @ is an alias to /src
import RegisterComponent from '@/components/RegisterComponent.vue'

export default {
  name: 'RegisterView',
  components: {
    RegisterComponent
  }
}
</script>