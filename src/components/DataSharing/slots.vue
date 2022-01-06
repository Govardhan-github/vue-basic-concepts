<template>
  <!-- Actually by using props 
1.have to write props in script and write which one is doing prop
2.bind the data in that component only
3.after that in main component in that selector tag have to write like this 
ex: props name = "card content" -->

  <!-- By using slots we can maange the total things of this component in app component only
so for this
1.have to write slot tag
2.just write the content inside selector in app componnet -->
  <div class="card">
    <!-- <div id="card-header">
      <slot name="header"></slot>
    </div>

    <div id="card-content">
      <slot></slot>
    </div>

    <div id="card-footer">
      <slot name="footer"></slot>
    </div> -->
    <h4>list of names by using v-for</h4>
    <h3 v-for="name in names" :key="name.first">
      <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
    </h3>
  </div>
</template>

<script>
export default {
  name: "slots",
  data() {
    return {
      names: [
        {
          firstName: "gopi",
          lastName: "reddy",
        },
        {
          firstName: "Govardhan",
          lastName: "Reddy",
        },
      ],
    };
  },
};
</script>

<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0.2);
  transition: 0.3;
  padding: 16px;
  margin-bottom: 20px;
  width: 200px;
}
.card:hover {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0.2);
}
</style>