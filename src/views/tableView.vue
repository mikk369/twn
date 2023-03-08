<template>
  <div class="main-container">
    <div class="main-contnent">
      <navView></navView>

      <menuView></menuView>
      <section>
        <body>
          <table>
            <thead>
              <tr>
                <th>Eestnimi</th>
                <th>Perekonnanimi</th>
                <th>Sugu</th>
                <th>Sünnikuupäev</th>
                <th>telefon</th>
              </tr>
            </thead>
            <tbody v-for="list in list" :key="list.id">
              <tr>
                <td>{{ list.firstname }}</td>
                <td>{{ list.surname }}</td>
                <td>{{ list.sex }}</td>
                <td>{{ list.date }}</td>
                <td>{{ list.phone }}</td>
              </tr>
            </tbody>
          </table>
          <pagination></pagination>
        </body>
      </section>
    </div>
  </div>
</template>
<script>
import axios from 'axios';
import pagination from '../components/paginationView.vue';
import menuView from './../components/menuItem.vue';
import navView from '../components/navView.vue';
export default {
  name: 'requirements',
  components: {
    menuView,
    navView,
    pagination,
  },
  data() {
    return {
      list: [],
    };
  },
  async created() {
    try {
      const response = await axios.get(
        'https://midaiganes.irw.ee/api/list?limit=500'
      );
      this.list = response.data.list;
      console.log(response.data.list);
    } catch (err) {
      console.log(err);
    }
  },
};
</script>
<style scoped>
@import url('./../style.css');

/* main content styles desktop */
body {
  display: flex;
  flex-direction: column;
}
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
body {
  color: #fff;
  font-family: 'Inter', sans-serif;
  line-height: 1;
  display: flex;
  justify-content: center;
  padding: 5rem 2.5rem;
}
table {
  border-collapse: collapse;
  margin-top: 100px;
  border-collapse: collapse;
  font-size: 18px;
}
th,
td {
  padding: 16px 24px;
  text-align: left;
}
tr {
  border-bottom: 1px solid #a4a5a7;
}
thead th {
  background-color: #333;
  color: #fff;
  width: 25%;
}
tbody tr:nth-child(odd) {
  background-color: #3a3d57;
}
tbody tr:nth-child(even) {
  background-color: #565657;
}
</style>
