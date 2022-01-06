<template>
  <div>
    <!-- <slots>card content</slots>
    <slots></slots>
    <slots>card content2</slots>

    <slots>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <h3>Gopi</h3>
      </template>
      <template v-slot:footer>
        <h3>Govardhan</h3>
      </template>
    </slots> -->
    <slots>
        <template v-slot:default="slotProps">
            {{slotProps.firstName}} {{slotProps.lastName}}
        </template>
    </slots>
    <slots>
        <template v-slot:default="slotProps">
            {{slotProps.lastName}}  {{slotProps.firstName}}
        </template>
    </slots>
  </div>
</template>

<script>
import slots from "./slots.vue";
export default {
  name: "slotParent",
  components: {
    slots,
  },
};
</script>

<style scoped>
</style>