<script>
export default {
  name: 'App',
  data() {
    return {
      message: 'Vue',
      firstName: '',
      lastName: '',
      text: 'text-primary',
      activeImg: 0,
      slider: {
        name: 'Mandalorian',
        imgs: [
          'https://image.tmdb.org/t/p/original/9zcbqSxdsRMZWHYtyCd1nXPr2xq.jpg',
          'https://image.tmdb.org/t/p/original/aZ4fmjMUAhS6PWhVLDDfT0RAdNe.jpg',
          'https://image.tmdb.org/t/p/original/p7fwOnlxYYlB4A8U2b0JfX21Rr1.jpg',
          'https://image.tmdb.org/t/p/original/qruRhG6jE5M8lWnW1AGOBxtdmCO.jpg',
          'https://image.tmdb.org/t/p/original/lMu3y10KgIYtXFPeCMim3D8iihV.jpg'
        ]
      }
    }
  },
  methods: {
    sayHi() {
      const pEl = document.querySelector('p');
      const message = `Hi Vue! ~${this.firstName} ${this.lastName}`;
      console.log(message);
      pEl.innerHTML = message
    },
    prev() {
      console.log(this.activeImg);
      if (this.activeImg <= 0) {
        this.activeImg = this.slider.imgs.length - 1
      } else {
        this.activeImg--
      }
    },
    next() {
      console.log(this.activeImg);
      if (this.activeImg >= this.slider.imgs.length - 1) {
        this.activeImg = 0
      } else {
        this.activeImg++
      }
    }
  }
}
</script>

<template>
  <div class="container centered">
    <div>
      <h1>Hello from {{ message }}!</h1>
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
  </div>


  <div class="container">
    <h2 class="text-center mb-3">{{ slider.name }}</h2>

    <img :src="slider.imgs[activeImg]" class="rounded-5" alt="">
    <div class="d-flex justify-content-between my-4">
      <button class="btn btn-primary" @click="prev">prev</button>
      <button class="btn btn-primary" @click="next">next</button>
    </div>
  </div>
</template>

<style></style>
