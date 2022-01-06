<template>
  <div class="methods">
    <h2>Methods</h2>
    <h3>Add method - {{ add(2, 5, 7) }}</h3>
    <h3>Multiply method - {{ Multiply(5) }}</h3>
    <h4>sum is {{ s }}</h4>
    <button class="addbtn" @click="sum(10, 5, 8)"><b>Sum</b></button>
  </div>

  <div class="Events">
    <div>
      <h2>Event Handling</h2>
      <h4>Changed Name : {{ name }}</h4>
      <h4>No.of times changed : {{ click }}</h4>

      <button class="namebtn" @click="changeName(), clicking()">
        Change Name
      </button>
    </div>
    <br />

    <div class="counterAPP">
      <div class="count">
        <b>counter is : {{ count }}</b>
        <hr />
      </div>
      <div class="btns">
        <button class="incre" @click="Increment()">Increment</button>
        <button class="decre" @click="Decrement()">Decrement</button>
        <button class="reset" @click="reset()">Reset</button>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  name: "Methods",
  data() {
    return {
      s: 0,
      name: "Gopi",
      count: 0,
      click: 0,
    };
  },

  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    Multiply(num) {
      return num * this.s;
    },
    sum(a, b, c) {
      this.s = a + b + c;
      return this.s;
    },
    changeName(event) {
      this.name = "Govardhan";
      console.log("Event", event);
    },
    clicking() {
      return this.click++;
    },
    Increment() {
      return (this.count += 5);
    },
    Decrement() {
      return (this.count -= 5);
    },
    reset() {
      return (this.count = 0);
    },
  },
};
</script>


<style>
.methods {
  margin-left: 100px;
  background-color: lightgrey;
  height: 230px;
  width: 450px;
  border-radius: 10px;
  border: 2px solid red;
}
.addbtn {
  background-color: purple;
  height: 30px;
  width: 120px;
  font-size: 15px;
  border-radius: 10px;
  font-size: 20px;
}
.Events {
  margin-left: 100px;
  margin-top: 15px;
  background-color: lightgrey;
  height: 190px;
  width: 450px;
  border-radius: 10px;
  border: 2px solid red;
}
.namebtn {
  background-color: skyblue;
  height: 30px;
  width: 120px;
  font-size: 15px;
  border-radius: 10px;
}

.counterAPP {
  margin-top: 10px;
  margin-left: 0px;
  background-color: lightblue;
  height: 150px;
  width: 450px;
  border-radius: 10px;
  border: 2px solid black;
}
.count {
  color: black;
  font-size: 20px;
}
.btns {
  margin-top: 20px;
}
.incre {
  height: 40px;
  width: 90px;
  font-size: 15px;
  background-color: Green;
  border-radius: 10px;
  z-index: 99;
}
.decre {
  height: 40px;
  font-size: 15px;
  width: 90px;
  border-radius: 10px;
  margin-left: 10px;
  background-color: red;
}
.reset {
  height: 40px;
  font-size: 15px;
  border-radius: 10px;
  width: 90px;
  margin-left: 10px;
  background-color: yellow;
}
</style>