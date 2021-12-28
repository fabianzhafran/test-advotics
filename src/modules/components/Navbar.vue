<template>
  <div class="navbar">
    <b-navbar toggleable="lg" type="light" variant="light" class="navbar white">
      <b-navbar-brand href="#">
        <img src="../../assets/img/advotics-logo.jpg" class="d-inline-block align-top advotics-logo" alt="Advotics Logo">
        <span class="powered-by">
          powered by <img src="../../assets/img/advotics-logo.jpg" class="d-inline-block align-top advotics-logo-mini" alt="Advotics Logo">
        </span>
      </b-navbar-brand>
      <b-navbar-nav class="ml-auto">
        <div>
          <p class="username">Username</p>
          <p class="company-name">Company Name</p>
        </div>
        <div class="logo-wrapper">
          <img src="../../assets/img/profile.png" class="d-inline-block align-top" alt="Profile">
          <img src="../../assets/img/logout.png" class="d-inline-block align-top logout" alt="Log Out">
        </div>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Navbar'
}
</script>

<style scoped>
.navbar {
  position: fixed;
  width: 100%;
  left: 0;
  z-index: 1;
}

.logo {
  height: 20px;
}

.advotics-logo {
  height: 30px;
  margin-right: 5px;
}

.powered-by {
  font-size: 0.7rem;
  line-height: 0;
  position: relative;
}

.advotics-logo-mini {
  height: 15px;
  position: absolute;
  bottom: 0;
  margin-left: 5px;
}

.navbar {
  height: 8vh;
  padding: 0 30px;
  box-shadow: 0px 3px 6px #00000029;
}

.white {
  background-color: white !important;
}

.username {
  font-size: 1rem;
  color: #727272;
}

.company-name {
  font-size: 0.7rem;
  line-height: 0;
  color: #727272;
}

.logo-wrapper {
  width: 65px;
  display: flex;
  align-items: center;
  margin-left: 20px;
  justify-content: space-between;
}

.logout {
  height: 15px;
}
</style>
