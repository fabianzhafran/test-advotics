<template>
  <div class="graph-card">
    <div class="title">
      <span class="title-text">AVERAGE PURCHASE VALUE</span>
      <div class="right-side-title">
        <b-dropdown text="Last 6 months" variant="light" class="m-2">
          <b-dropdown-item href="#">Last 3 months</b-dropdown-item>
          <b-dropdown-item href="#">Last month</b-dropdown-item>
        </b-dropdown>
        <img src="../../../assets/img/more-button.png" class="more-icon">
      </div>
    </div>
    <Graph />
  </div>
</template>

<script>
import Graph from './Graph.vue'

export default {
  name: 'GraphCard',
  components: {
    Graph
  }
}
</script>

<style scoped>
.graph-card {
  flex: 2;
  margin: 10px 10px;
  padding: 0 15px;
  background: #FFFFFF 0% 0% no-repeat padding-box;
  box-shadow: 0px 2px 6px #0000000A;
  border: 0.5px solid #CACED5;
  border-radius: 2px;
  opacity: 1;
}

.title {
  margin: 10px 0;
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.more-icon {
  height: 20px;
  margin: 0 10px;
}
</style>
