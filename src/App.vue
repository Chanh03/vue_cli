<template>
  <app-header ref="header" />
  <app-modal
    title="Chào chuột ngoooooooo"
    content="Còn cái này hay lắm"
    theme="d"
  />
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppModal from "./components/AppModal.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppModal,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>
