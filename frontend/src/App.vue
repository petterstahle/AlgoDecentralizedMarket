<template>
  <div id="app">
    <AlgoDeMarket />
  </div>
</template>

<script>
import AlgoDeMarket from './components/AlgoDeMarket.vue'
export default {
  name: 'App',
  components: {
    AlgoDeMarket
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  position: relative;
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 50px;
  box-sizing: border-box;
}

/* For devices larger than 400px */
@media (min-width: 400px) {
  .container {
    width: 85%;
    /* padding: 0; */
   }
}

/* For devices larger than 550px */
@media (min-width: 550px) {
  .container {
    width: 80%; 
    }
  .header-container {
    width: 80%;
  }

}

label {
  padding: 0 10px;
}

.button,
button,
input[type="submit"],
input[type="reset"],
input[type="button"] {
  display: inline-block;
  height: 38px;
  padding: 0 30px;
  color: #555;
  text-align: center;
  font-size: 11px;
  font-weight: 600;
  line-height: 38px;
  letter-spacing: .1rem;
  text-transform: uppercase;
  text-decoration: none;
  white-space: nowrap;
  background-color: transparent;
  border-radius: 4px;
  border: 1px solid #bbb;
  cursor: pointer;
  box-sizing: border-box; }
.button:hover,
button:hover,
input[type="submit"]:hover,
input[type="reset"]:hover,
input[type="button"]:hover,
.button:focus,
button:focus,
input[type="submit"]:focus,
input[type="reset"]:focus,
input[type="button"]:focus {
  color: #333;
  border-color: #888;
  outline: 0; }
.button.button-primary,
button.button-primary,
input[type="submit"].button-primary,
input[type="reset"].button-primary,
input[type="button"].button-primary {
  color: #FFF;
  background-color: #0fbaee;
  border-color: #0fbaee; }
.button.button-primary:hover,
button.button-primary:hover,
input[type="submit"].button-primary:hover,
input[type="reset"].button-primary:hover,
input[type="button"].button-primary:hover,
.button.button-primary:focus,
button.button-primary:focus,
input[type="submit"].button-primary:focus,
input[type="reset"].button-primary:focus,
input[type="button"].button-primary:focus {
  color: #FFF;
  background-color: #1EAEDB;
  border-color: #1EAEDB; }

.header-container {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 3;
    width: 100%;
    background-color: rgb(255, 194, 114);
}

.header-stripe {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 100px;
  padding: 20px;
}

#title {
  /* font-family: monospace; */
  font-size: 20px;
  font-style: normal;
  /* font-weight: 700; */
  font-variant: normal;
  line-height: 50px;
  letter-spacing: 0.2em;
  text-align: center;
  padding-top: 30px;
  margin-bottom: 10px;
}


.tabs {
  padding-top: 20px;
  padding-bottom: 50px;
  width: 100%;
  font-size: auto;
  color: black;
}

@media (max-width: 750px) {
  #title {
    font-size: 10px;
    line-height: 20px;
  }
  button .button, .button-primary {
    height: 30px;
    padding: 0 15px;
    font-size: 7px;
    font-weight: 600;
    line-height: 30px;
    letter-spacing: .1rem;
  }
  .tabs {
    font-size: 10px;
  }

  .tabs .button {
    height: 30px;
    padding: 0 15px;
    font-size: 7px;
    font-weight: 600;
    line-height: 30px;
    letter-spacing: .1rem;
  }
}

.footer-container {
    position: static;
    /* margin-top: 500px; */
    bottom: 0;
    left: 0;
    z-index: 3;
    width: 100%;
    background-color: rgb(100, 100, 100);
    text-align: center;
}

.footer-stripe {
  position: relative;
  text-align: center;
  /* display: flex; */
  align-items: center;
  justify-content: space-between;
  width: 100%;
  height: 220px;
  padding: 10px;
}

.footer-stripe img {
  width: 200px;
}


body  {
  /* background-image: url("logo.png"); */
  background-color: #ffffff;
  background-position: center;
  background-repeat: no-repeat;

}

</style>
