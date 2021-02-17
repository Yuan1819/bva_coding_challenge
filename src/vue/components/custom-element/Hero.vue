<template>
  <div>
    <h1>Vue Component</h1>
    <p>Shopify Prop: {{ settings.title }}</p>
    <p>Store Value: </p>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  props: {
    settings: Object,
  },
  computed: {
    ...mapGetters("example", ["value"])
  }
};
console.log("settings", props.settings)
</script>
