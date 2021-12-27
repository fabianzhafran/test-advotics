<template>
  <div>
    <Navbar />
    <div class="content">
      <Sidebar />
    </div>
  </div>
</template>

<script>
import Navbar from '../modules/components/Navbar.vue'
import Sidebar from '../modules/components/Sidebar.vue'

export default {
  name: 'Home',
  components: {
    Navbar,
    Sidebar
  }
}
</script>

<style scoped>
.content {
  display: flex;
  flex-direction: row;
  min-height: 90vh;
}
</style>
