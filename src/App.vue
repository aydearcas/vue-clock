<template>
  <div class="container">
    <div class="dark-box">
      <div class="hours">{{hours}}</div>
      <div class="dots">:</div>
      <div class="mins">{{mins}}</div>
      <div class="dots">:</div>
      <div class="secs">{{secs}}</div>
      <div class=""></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      hours: 0,
      mins: 0,
      secs: 0
    };
  },
  methods: {
    setTime () {
      setInterval(() => {
        const date = new Date();
        this.hours = date.getHours().toString().padStart(2, '0');
        this.mins = date.getMinutes().toString().padStart(2, '0');
        this.secs = date.getSeconds().toString().padStart(2, '0');
      }, 1000);
    }
  },
  mounted () {
    this.setTime();
  }
};
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=DotGothic16&display=swap');
  strong {
    color: aquamarine;
  }
  p {
    color:greenyellow;
  }

  .container {
    background: linear-gradient(to right, grey, rgb(46, 44, 44));
    display: flex;
    justify-content: center;
    align-items: center;
    width: 700px;
    height: 200px;
  }

  .dark-box {
    font-family: 'DotGothic16', sans-serif;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 600px;
    height: 150px;
    background: black;
    border-radius: 20px;
    color: yellow;
    font-size: 120px;
  }
</style>
