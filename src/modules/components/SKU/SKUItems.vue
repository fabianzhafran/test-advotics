<template>
  <div :class="bestSelling ? 'sku-item best-selling' : 'sku-item'">
    <img src="../../../assets/img/product-competitor.png" class="more-icon">
    <div class="detil-product">
      <p class="nama-product">[Nama Product]</p>
      <div class="rincian">
        <p class="harga">Rp XXXX</p>
        <p class="harga">[jml terjual]</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SKYItem',
  props: {
    bestSelling: {
      default: false,
      type: Boolean
    }
  }
}
</script>

<style scoped>
.sku-item {
  display: flex;
  flex-direction: row;
  font-size: 0.8rem;
  border: 0.5px solid #C5C5C59C;
  border-radius: 4px;
  margin: 7px 0;
  height: 70px;
  padding-right: 10px;
}

.sku-item > img {
  height: 100%;
}

.best-selling {
  height: 90px;
  border: none;
  background: #FFE7BD 0% 0% no-repeat padding-box;
}

.detil-product {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin-left: 10px;
  width: 80%;
}

.nama-product {
  letter-spacing: 0px;
  color: #4D4F5C;
  font-size: 0.9rem;
  margin: 2px 0 0 0;
}

.best-selling .nama-product {
  font-size: 1rem;
  font-weight: bold;
}

.rincian {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  color: #00000099;
}
</style>
