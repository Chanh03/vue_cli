<template>
  <div class="modal fade show">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1>{{ title }}</h1>
        </div>
        <div class="modal-body" :class="{ 'bg-purple': theme == 'purple' }">
          <p>{{ content }}</p>
          <img
            src="https://reviewamthuc.net/wp-content/uploads/2024/04/chuot-nuong-4.jpg"
            alt=""
          />
        </div>
        <div class="modal-footer">
          <h3>
            <button @click="onCloseModal">CLOSE</button>
          </h3>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      default: "",
    },
    footer: {
      type: String,
      default: "",
    },
    theme: {
      type: String,
      default: "white",
      validator(value) {
        return ["purple", "green", "red", "yellow", "white"].includes(value);
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    onCloseModal() {
      this.$emit("cancel");
    },
  },
};
</script>
<style scoped>
.bg-purple {
  background: purple;
}
</style>
