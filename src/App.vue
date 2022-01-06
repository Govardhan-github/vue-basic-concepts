<template>
  <!-- <props name="Gopi" anotherName="Govardhan"   :likes=45 :isPublished="true" :fistname="name" 
  :secondName="channel" />
  -->

  <div>
    <!-- <button @click="showPopup= true">Show Popup</button>
  <popup v-show="showPopup" @close="closepopup" @message="msg" /> -->
    <!-- <comp-a /> -->
    <!-- App components userName :{{userName}} -->
    <slotParent />
  </div>
</template>

<script>
import slotParent from "./components/DataSharing/SlotsParent.vue";

export default {
  name: "App",
  data() {
    return {
      message: "",
      showPopup: false,
      userName: "Govardhan Reddy",
      name: "nandu",
      channel: "YT",
    };
  },
  methods: {
    closepopup(name) {
      this.showPopup = false;
      console.log(name);
    },
    msg(message) {
      console.log(message);
      this.message = message;
    },
  },

  provide() {
    return {
      userName: this.userName,
    };
  },
  components: {
    slotParent,
  },
};
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
