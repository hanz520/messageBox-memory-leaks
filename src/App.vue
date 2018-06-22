<template>
  <div id="app">
    <my-link></my-link>
    <router-view/>
  </div>
</template>

<script>
import link from '@/components/link'
export default {
  name: 'App',
  components: {
    'my-link': link
  }
}
</script>
