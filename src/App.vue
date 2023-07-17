<template>
  <div id="app">
    <header>
      <nav>
        <ul>
          <li><router-link to="/">CUACA</router-link></li>
          <li><router-link to="/location">LOKASI</router-link></li>
          <li><router-link to="/stopwatch">STOPWATCH</router-link></li>
          <li><router-link to="/tictactoe">GAME</router-link></li>
          <li><router-link to="/photo">FOTO</router-link></li>
        </ul>
      </nav>
    </header>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
/* Global Styles */
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

#app {
  text-align: center;
}

/* Header Styles */
header {
  background: #427983;
  padding: 20px;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

nav li {
  display: inline-block;
  margin-right: 10px;
}

nav a {
  color: #fff;
  text-decoration: none;
  padding: 5px 10px;
  border-radius: 5px; /* Add rounded corners to the buttons */
  background-color: #4f9e7de5; /* Change the button color */
  transition: background-color 0.3s; /* Add a smooth transition effect on hover */
}

nav a:hover {
  background-color: #a09a45; /* Change the button color on hover */
}
body {
      margin: 0;
      padding: 0;
      background-image: url(https://www.wisesecurity.net/wp-content/uploads/2019/11/160-1600491_autodesk-wallpaper-website-background.jpg);
      background-repeat: no-repeat;
      background-attachment: fixed; /* Tetap berada di posisi tetap */
      background-size: cover; /* Memastikan background image mencakup seluruh area body */
      background-position: center center; /* Posisi background image di tengah-tengah */
      height: 100vh; /* Set tinggi body untuk mencakup seluruh layar */
    }
</style>