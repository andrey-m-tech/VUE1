<template>
  <MyComponent></MyComponent>

  <!-- HTML Input Types
  https://www.w3schools.com/html/html_form_input_types.asp -->

 <br>
 Домашнее задание 1 
 <br>
 Введите количество товара (1 - 10)
 <br>
 {{num}}
 <button @click="numminus">-</button>
  <input type='number' v-bind:value="num"    />
 <button @click="numplus">+</button>
 <br>
 <br>

  <label>
    Введите email:
    <input type='email' v-bind:value='email' v-on:input="emailInput"/>
  </label>
<br>
  <label>
    Введите пароль:
    <input type='password' v-bind:value='password'/>
  </label>
</template>

<script>
import MyComponent from './components/MyComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      email: '123example@mail.ru',
      password: '12345',
      num: 1,
      n: 0
    }
  },
  methods: {
    
    numplus() {
      if (this.num < 10) {
        this.num += 1
      }
        
    },
    numminus() {
      if (this.num > 1) {
        this.num -= 1
      }
    },
    m() {
      this.email = this.email + '*'
    },
    emailInput(event) {
      //this.email = event.target.value
      console.log(event.target.value)
      this.m()
    }
    
  },
  components: {
    MyComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
