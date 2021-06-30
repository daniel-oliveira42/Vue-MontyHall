<template>
  <div id="app">
    <h1>Monty Hall Problem</h1>
    <div class="form">
      <div v-if="!started">
        <label for="doorAmount">Número de portas: </label>
        <input type="text" id="doorAmount" size="3"
        v-model.number="doorAmount">
      </div>
      <div v-if="!started">
          <label for="selectedDoor">Qual porta certa? </label>
          <input type="text" id="selectedDoor" size="3"
          v-model.number="selectedDoor">
      </div>
      <button v-if = "!started" @click= "started = true">Iniciar</button>
      <button v-if = "started" @click = "started = false">Reiniciar</button>
    </div>
    <div class="doors" v-if = "started">
      <div v-for= "i in doorAmount" :key= "i">
        <Door :hasGift="i === selectedDoor" :number ="i"/>
      </div>
    </div>
  </div>
</template>

<script>
import Door from './components/door'

export default {
  name: 'App',
  components: { Door },
  data: function() {
    return {
      started: false,
      doorAmount: 3,
      selectedDoor: null
    }
  }
}
</script>

<style>
 * {
   box-sizing: border-box;
   font-family: 'Montserrat', sans-serif;
   user-select: none;
 }

 body {
    background: #659999;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #f4791f, #659999);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #f4791f, #659999); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
 }

 #app {
   display: flex;
   flex-direction: column
 }

 #app h1 {
   color: white;
   text-align: center;
   text-transform: uppercase;
 }

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-self: center;
  margin: 10px;
  color: white;
  font-size: 36px;
  padding: 10px;
  text-align: center;
}

.doors {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

button {
  min-width: 200px;
  width: 100%;
  height: 50px;
  border-radius: 50px;
  background-color: rgb(223, 201, 5);
  color: white;
  font-size: 24px;
  font-weight: 500;
  margin-top: 50px;
}

input {
  height: 36px;
  font-size: 36px;
}
</style>
