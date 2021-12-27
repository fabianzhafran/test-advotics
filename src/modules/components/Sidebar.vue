<template>
  <div class="sidebar">
    <div class="item">
      <img src="../../assets/img/menu-icon.jpg" class="menu-icon">
    </div>
    <div class="item selected">
      <img src="../../assets/img/dashboard-icon.png" class="dashboard-icon">
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

<style scoped>
.sidebar {
  width: 75px;
  border: 0.5px solid #D2D2D2;
}

.item {
  margin: 10px 0;
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.selected {
  background-color: #D2D2D2;
  padding: 0;
}

.menu-icon {
  height: 50px;
}

.dashboard-icon {
  background-color: white;
  padding: 3px;
  border-radius: 3px;
}
</style>
