<template>
  <div class="home">
    <Postalcode @sendData="showPostalcode"></Postalcode>
    <p>Address：{{text}}</p>
  </div>
</template>

<script>
import Postalcode from "../components/Postalcode.vue";
export default {
  data() {
    return {
      text: ""
    }
  },
  methods: {
    showPostalcode(info) {
      return this.text = info;
    }
  },
  components: {
    Postalcode
  }
}
</script>

<style scoped>
.home {
  margin: 20px 0 0 20px;
}
.home a{
  
}
.home input {
  padding: 5px 10px;
}
</style>