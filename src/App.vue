<template>
  <div id="app">
    <h1 class="site-title">{{ title }}</h1>
    <h2 class="site-description">{{ currentDate() }}</h2>

    <ul v-if="entries" class="ul">
      <li class="li" v-for="entry in entries" :key="entry">
        <span class="entry-date"
          >{{ entry[0] }} Uhr {{ entry[1].replaceAll("/", ".") }}</span
        ><br />
        <h3 class="entry-title">{{ entry[2] }}</h3>
        <h4 class="entry-description">{{ entry[3] }}</h4>
        <br />
      </li>
    </ul>

    <h1 v-else>NO EVENTS!</h1>

    <footer>
      <img class="img-footer" alt="Logo" src="./assets/STZH_SEB_Logo.png" />
      <img class="img-footer2" alt="Logo" src="./assets/Opportunity.png" />
      <img class="img-footer3" alt="Logo" src="./assets/SAG_Logo_De.png" />
    </footer>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      title: "Welcome to Opportunity",
      sheet_id: "1a81aI0Y8ViZO0tI92h2YSMqVQJ8hmNNMyMylXgvwiU4",
      api_token: "AIzaSyA-qeDXOhEeQDA0vQf7LgkF7DQtGnAtmAU",
      entries: [],
    };
  },

  computed: {
    gsheet_url() {
      return `https://sheets.googleapis.com/v4/spreadsheets/${this.sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${this.api_token}`;
    },
  },

  methods: {
    getData() {
      axios.get(this.gsheet_url).then((response) => {
        this.entries = response.data.valueRanges[0].values;
      });
    },

    currentDate() {
      const current = new Date();
      const day = current.getDate();
      const month = current.getMonth() + 1;
      const year = current.getFullYear();
      const dateTime = day + "." + month + "." + year;
      if (month < 10) {
        return day + "." + "0" + month + "." + year;
      }
      return dateTime;
    },

    refreshData: function () {
      this.currentDate();
      this.getData();
    },
  },
  mounted() {
    this.refreshData();
    setInterval(
      () => {
        this.refreshData();
      } /*20000*/
    );
  },
};
</script>


<style>
#app {
  font-family: "Inter", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
html,
body {
  background-color: aliceblue;
}

h1 {
  font-size: 65px;
  text-align: left;
  font-weight: 300px;
  margin-bottom: 15px;
  padding-left: 85px;
}

h2 {
  font-size: 52px;
  font-weight: 10;
  text-align: left;
  padding-left: 85px;
  margin: 0px;
  color: rgba(119, 136, 153, 0.644);
}

h3 {
  color: rgb(251, 188, 169);
  font-weight: 70%;
  padding-top: 20px;
  font-size: 30px;
  padding-left: 0px;
}

h4 {
  color: rgb(251, 188, 169);
  padding-left: 5px;
  padding-top: 10px;
  font-size: 22px;
  background-color: #0f05a0;
}

span {
  font-size: 40px;
  font-weight: bolder;
}

.img-footer {
  width: 240px;
  height: 44px;
  left: 40px;
  padding-left: 70px;
}

.img-footer2 {
  width: 290px;
  height: 52px;
  left: 392px;
  padding-left: 70px;
}

.img-footer3 {
  width: 273px;
  height: 52px;
  left: 767px;
  padding-left: 80px;
  padding-top: 40px;
}

footer {
  display: fixed;
  justify-content: space-between;
  box-sizing: border-box;
  position: fixed;
  width: 100%;
  left: 0;
  bottom: 0;
  padding: 20px;
  padding-top: 20px;
  background: white;
  margin-top: 50px;

}

.ul {
  list-style-type: none;
}

.li {
  width: 80%;
  height: 190px;
  padding: 2rem;
  margin: 50px;
  background: #0f05a0;
  font-style: normal;
  font-weight: 1200;
  font-size: 28px;
  line-height: 5px;
  color: #eb5e00;
}
</style>
