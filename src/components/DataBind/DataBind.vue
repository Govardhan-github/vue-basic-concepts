<template lang="">
    <!-- DataBinding -->
    <div class="DataBind">
      <h2>DataBinding</h2>
      {{ greet }} {{ name }} {{ channe }}
      <div v-text="channel"></div>
      <div v-html="channel"></div>
    </div>

    <!-- Binding ATtributes -->
    <div class="ClassBind">
      <h2>CLASS BINDING</h2>
      <h3 v-bind:76id="headingId">HEADING</h3>
      <button v-bind:disabled="isDisabled">bind</button>
      <h3 class="under">UnderLine Text</h3>
      <h3 v-bind:class="status">Status checking class</h3>
      <h3 v-bind:class="isPromoted && 'promoted'">
        double and operator class applying
      </h3>
      <h3 v-bind:class="isTrue ? 'green' : 'red'">
        Conditional class checking
      </h3>
      <h3 v-bind:class="['under', 'red']">multiple classes applying</h3>
    </div>

    <div class="StyleBind">
      <h2>Style Binding</h2>
      <!-- Style Binding will have 2 types 1.object Syntax 2.Array Syntax -->
      <h3 v-bind:style="{ color: highLightColor, fontSize: headerSize + 'px' }">
        Object Style Binding
      </h3>
      <h3 v-bind:style="headerStyleObject">Object style bidning</h3>
      <div v-bind:style="[baseStyleArray, successStyleArray]">
        Style Binding Array
      </div>
    </div>
    <div class="vbindshort">
      <h2>V Bind ShortCut</h2>
      <h4 v-bind:class="shortcut">V Bind ShortCut</h4>
    </div>  
</template>

<script>
export default {
  name: "DataBind",
  data() {
    return {
      greet: "hello",
      name: "Gopi Reddy",
      channel: "<b>Vue js tutorial</b>",
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: true,
      isTrue: true,
      highLightColor: "orange",
      headerSize: 20,
      headerStyleObject: {
        color: "orange",
        fontSize: "20px",
      },
      baseStyleArray: {
        color: "yellow",
      },
      successStyleArray: {
        background: "red",
      },
    };
  },
};
</script>


<style>
.StyleBind {
  background-color: cadetblue;
}
.DataBind {
  background-color: burlywood;
}
.ClassBind {
  background-color: lightblue;
}

.promoted {
  color: black;
  font-size: 25px;
}
.under {
  text-decoration: underline;
}
.green {
  color: green;
}
.red {
  color: red;
}
.shortcut {
  color: black;
}
</style>