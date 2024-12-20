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
  <div>
    <table>
      <tr v-for="pet in petData" :key="pet.petID">
        <td>{{ pet.petID }}</td>
        <td>{{ pet.createDate }}</td>
        <td>{{ pet.petCategoryID.petCategoryName }}</td>
      </tr>
    </table>
  </div>
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
      petData: [],
    };
  },
  methods: {
    onToggleModal() {
      console.log("Runningggg...");
      this.isShowModal = !this.isShowModal;
    },
  },
  mounted() {
    fetch("http://localhost:8080/api/pet")
      .then((res) => res.json())
      .then((data) => {
        console.log(data); // Kiểm tra dữ liệu
        this.petData = data;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>
