<template>
  <div class="postalcode">
    <input type="text" v-model="adress">
    <button @click="sendAddress">住所自動入力</button>
  </div>
</template>


<script>
import axios from "axios";
export default {
  data() {
    return {
      adress: "",
      info: ""
    };
  },
  methods: {
    async sendAddress() {
      let item = await axios.get(`https://apis.postcode-jp.com/api/v2/postcodes/${this.adress}?apiKey=lbUy6EDin3FRQynBwSx7CBxPrlrIHVs2htSdDQG`);
      this.info = item.data.allAddress;
      return this.$emit("sendData",this.info);
    }
  }
};
</script>

<style scoped>
.postalcode {
  margin-bottom: 10px;
}
.postalcode button:hover {
  transition: 0.5s;
}
</style>