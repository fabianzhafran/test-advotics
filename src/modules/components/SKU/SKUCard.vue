<template>
  <div class="sku-card">
    <div class="title">
      <span>{{ msg }}</span>
      <img src="../../../assets/img/more-button.png" class="more-icon">
    </div>
    <div v-for="i in listItem" :key="i" class="item selected">
      <SKUItems v-if="i === 1" :bestSelling="true" />
      <SKUItems v-else />
    </div>
  </div>
</template>

<script>
import SKUItems from './SKUItems.vue'

export default {
  name: 'SKUCard',
  components: {
    SKUItems
  },
  data() {
    return {
      listItem: [1, 2, 3, 4, 5]
    }
  },
  props: {
    msg: {
      default: 'BEST SELLING SKU',
      type: String
    }
  }
}
</script>

<style scoped>
.sku-card {
  flex: 1;
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
}
</style>
