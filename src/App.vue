<template>
  <app-header ref="header" />
  <button @click="onToggleModal">Toggle Modal</button>
  <app-modal
    v-if="isShowModal"
    title="Chào chuột ngoooooooo"
    content="Còn cái này hay lắm"
    theme="purple"
    @cancel="onToggleModal"
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
    return {
      isShowModal: false,
    };
  },
  methods: {
    onToggleModal() {
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>
