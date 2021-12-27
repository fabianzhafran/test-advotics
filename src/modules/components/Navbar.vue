<template>
  <div>
    <b-navbar toggleable="lg" type="light" variant="light" class="navbar white">
      <b-navbar-brand href="#">
        <img src="../../assets/img/advotics-logo.jpg" class="d-inline-block align-top advotics-logo" alt="Advotics Logo">
        <span class="powered-by">
          powered by <img src="../../assets/img/advotics-logo.jpg" class="d-inline-block align-top advotics-logo-mini" alt="Advotics Logo">
        </span>
      </b-navbar-brand>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <div class="username-wrapper">
            <p>Username</p>
            <p>Company Name</p>
          </div>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
  padding: 0 2vw;
  box-shadow: 0px 3px 6px #00000029;;
}

.white {
  background-color: white !important;
}

.username-wrapper {
  
}
</style>
