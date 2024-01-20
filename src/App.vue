<script>
export default {
  name: 'App',
  data() {
    return {
      message: 'Vue',
      firstName: '',
      lastName: '',
      text: 'text-primary'
    }
  },
  methods: {
    sayHi() {
      const pEl = document.querySelector('p');
      const message = `Hi Vue! ~${this.firstName} ${this.lastName}`;
      console.log(message);
      pEl.innerHTML = message
    }
  }
}
</script>

<template>
  <h1>Hello from {{ message }}!</h1>

  <div>
    <div class="mb-3">
      <label class="form-label" :class="text" for="firstName">First Name:</label>
      <input class="form-control" id="firstName" type="text" v-model="firstName">
    </div>
    <div class="mb-3">
      <label class="form-label" :class="text" for="lastName">Last Name:</label>
      <input class="form-control" id="lastName" type="text" v-model="lastName">
    </div>

    <button class="btn btn-primary mb-3" @click="sayHi">Say Hi to Vue!</button>

    <p></p>


  </div>
</template>

<style></style>
