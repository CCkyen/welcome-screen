<template>
  <div id="app">
    <h1>Welcome to Opportunity</h1>

    <h2>16.05.2022</h2>

    <ul class="ul">
      <li class="li">
        <span> 14:00 Uhr </span>
        <h3>Basisbeschäftigung Besuch</h3>

        <h4>Interessierte für den zweiten Kurs werden uns besuchen</h4>
      </li>
    </ul>

    <ul class="ul">
      <li class="li">
        <span> 14:00 Uhr </span>
        <h3>Basisbeschäftigung Besuch</h3>

        <h4>Interessierte für den zweiten Kurs werden uns besuchen</h4>
      </li>
    </ul>

    <ul class="ul">
      <li class="li">
        <span> 14:00 Uhr </span>
        <h3>Basisbeschäftigung Besuch</h3>

        <h4>Interessierte für den zweiten Kurs werden uns besuchen</h4>
      </li>
    </ul>

    <footer>
      <img class="img-footer" alt="Logo" src="./assets/STZH_SEB_Logo.png" />
      <img class="img-footer2" alt="Logo" src="./assets/Opportunity.png" />
      <img class="img-footer3" alt="Logo" src="./assets/SAG_Logo_De.png" />
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
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
  padding-left: 50px;
  margin-bottom: 15px;
}

h2 {
  font-size: 52px;
  font-weight:10 ;
  text-align: left;
  padding-left: 50px;
  margin: 0px;
  color: rgba(119, 136, 153, 0.644);
}

h3 {
  color: rgb(251, 188, 169);
  font-weight: 70%;
  padding-top: 5px;
}

h4 {
  color: rgb(251, 188, 169);
  padding-left: 0px;
  font-size:25px ;
}

span {
  font-size:33px;
  font-weight: bolder;
}

.img-footer {
  width: 240px;
  height: 44px;
  left: 40px;
  padding-left: 70px;
  /* top: 1833px;
  position:left; */
}

.img-footer2 {
  width: 290px;
  height: 52px;
  left: 392px;
  padding-left: 70px;
  /* top: 1828px; */
}

.img-footer3 {
  width: 273px;
  height: 52px;
  left: 767px;
  padding-left: 80px;
  padding-top: 40px;
  /* top: 1829px; */
}

footer {
  position: absolute;
  width: 1080px;
  height: 130px;
  left: 0px;
  top: 1790px;

  background: rgb(255, 255, 255);
}

.ul {
  margin-top: 40px;
  margin-bottom: 40px;
  margin-left: 45px;
  padding-left: 0px;
  height: 182px;
  width: 970px;
  left: 0px;
  right: 0px;
  top: 0px;
  background: #0f05a0;
  list-style-type: none;
}

.li {
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 50px;
  padding-top: 40px;

  font-style: normal;
  font-weight: 1200;
  font-size: 28px;
  line-height: 5px;
  /* or 129% */

  color: #eb5e00;
}
</style>
