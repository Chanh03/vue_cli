<template>
  <div class="modal fade show" @click="onCloseModal">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1>{{ title }}</h1>
        </div>
        <div class="modal-body" :class="{ 'bg-purple': theme == 'purple' }">
          <slot name="content" />
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
