<template>
  <div class="main-contnent">
    <navView></navView>
    <menuView></menuView>
    <section>
      <div class="text-wrapper">
        <h1>TRINIDAD WISEMAN</h1>
        <p>SPA proovitöö</p>
      </div>
    </section>
  </div>
</template>
<script>
import navView from '../components/navView.vue';
import menuView from './../components/menuItem.vue';
export default {
  name: 'requirements',
  components: {
    menuView,
    navView,
  },
};
</script>
<style scoped>
@import url('./../style.css');

/* main content styles desktop */
.main-contnent {
  font-family: booster;
  font-size: 1.1875rem;
  font-weight: lighter;
  color: #fff;
  display: grid;
  grid-template-columns: 220px 1fr;
  grid-template-rows: 1fr;
  height: 100vh;
}
/* main content at width 960 row height */
@media (max-width: 960px) {
  .main-contnent {
    grid-template-rows: 50px;
  }
}

/* SECTION STYLES */
section {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #3a3d57;
  background-image: url('/bg-deco-right.svg'), url('/bg-deco-left.svg');
  background-repeat: no-repeat;
  background-position: top right, bottom left;
  background-size: 200px;
}
@media (max-width: 960px) {
  section {
    grid-row: 2 / 3;
    grid-column: 1 / 3;
  }
}
.text-wrapper {
  text-align: center;
}
h1 {
  color: #14cc76;
  font-size: 45px;
}
p {
  font-size: 40px;
  font-weight: bold;
}
</style>
