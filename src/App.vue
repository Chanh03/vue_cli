<template>
  <app-header ref="header" />
  <button @click="onToggleModal">Toggle Modal</button>
  <app-modal
    v-if="isShowModal"
    title="Chào chuột ngoooooooo"
    theme="purple"
    @cancel="onToggleModal"
  >
    <template v-slot:content>
      <img
        src="https://reviewamthuc.net/wp-content/uploads/2024/04/chuot-nuong-4.jpg"
        alt=""
      />
    </template>
  </app-modal>
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
      console.log("Runningggg...");
      this.isShowModal = !this.isShowModal;
    },
  },
};
</script>
