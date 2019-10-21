<template>
  <div>
    <Header />
    <router-view />
  </div>
</template>

<script>
import Header from './Header'
export default {
  name: 'index-layout',
  components: {
    Header
  }
}
</script>
