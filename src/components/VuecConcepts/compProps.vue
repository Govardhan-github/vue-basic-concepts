<template>
  <h2>Computed Props</h2>
  <div>
      <!-- props are used to reduce the reptitive code for that we have to write props and have to pass datatypes
      and just have to call those properties in main components and nedd to bind the data on props component
      whe we are using number and boolean props we will give data in strings by defaukt it will take as string 
      only for number and boolean so it will show a wanring in console so to overcome that we have to apply 
      v-bind : then it will take input as number for number and boolean for boolean only..
        -->
    <h3>hello {{ name }} a.k.a {{ anotherName }}</h3>
    <h3>hello {{ fistname }} a.k.a {{ secondName }}</h3>
    </div>

    <div>
        Article  Title : {{ title }}  Likes : {{ likes }} Publish : {{isPublished ? 'yes' : 'no'}}
    </div>

<div>
 
<h2>Non Prop  computed properties</h2>
<div v-bind="$attrs">
    Article id="my-article" Title : {{ title }}  Likes : {{ likes }} Publish : {{isPublished ? 'yes' : 'no'}}

</div>

</div>




</template>

<script>
export default {
  name: "Props",

  props: {
    fistname: String,
    secondName: String,
    name: String,
    anotherName: String,
    title: {
        title : String,
        required : true,
        default : 'default title'
    },
    likes: Number,
    isPublished:Boolean,
    },
    inheritAttrs:false
};
</script>

<style scoped>
</style>