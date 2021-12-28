<template>
  <div class="sale-turnover">
    <div class="title">
      <span>Sales Turnover</span>
      <img src="../../assets/img/more-button.png" class="more-icon">
    </div>
    <div class="sale-statistics">
      <div class="wrapper">
        <p class="amount-of-profit">Rp 3,600,000</p>
        <span class="products-sold"><span class="percentage">↓ 13.8%</span>last period in products sold</span>
      </div>
      <img src="../../assets/img/sales-turnover.png" class="sales-turnover">
    </div>
  </div>
</template>

<script>

export default {
  name: 'SaleTurnover'
}
</script>

<style scoped>
.sale-turnover {
  flex: 1;
  margin: 10px 0;
  padding: 10px 15px;
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

.sale-statistics {
  display: flex;
  flex-direction: row;
}

.amount-of-profit {
  font-size: 1.4rem;
  font-weight: bold;
}

.products-sold {
  font-size: 0.7rem;
}

.percentage {
  font-weight: bold;
  color: red;
  margin-right: 10px;
}

.more-icon {
  height: 20px;
}

.wrapper {
  width: 100%;
}

.sales-turnover {
  object-fit: cover;
  height: 30px;
}
</style>
