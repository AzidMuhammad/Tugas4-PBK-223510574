<template>
  <div class="parent">
    <h2 class="header">Parent Components</h2>
    <textarea name="" id="" cols="30" rows="10">{{ message }}</textarea>
    <button @click="showChild = true" class="open-modal-button">Child Component</button>
    <Modal v-if="showChild" @close="showChild = false">
      <ChildComponent @childEvent="updateMessage" />
    </Modal>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';
import Modal from './Modal.vue';

export default {
  name: 'ParentComponent',
  components: {
    ChildComponent,
    Modal,
  },
  data() {
    return {
      message: 'Ini Komponen Orang Tua',
      showChild: false,
    };
  },
  methods: {
    updateMessage(newMessage) {
      this.message = newMessage;
    },
  },
};
</script>

<style scoped>

.parent {
  padding: 20px;
  border: 2px solid #C4A484;
  border-radius: 10px;
  background-color: #F3E5AB !important;
  transition: all 0.3s ease;
  height: 85%;
}

.parent:hover {
  background-color: #F5DEB3;
}

textarea {
  width: 97%;
  padding: 10px;
  font-family: 'Times New Roman', Times, serif;
  font-size: 18px;
  border: 2px solid #D2B48C;
  border-radius: 5px;
  resize: vertical;
  margin-bottom: 10px;
  text-align: center;
  background-color: #FFF5E1;
  color: #333;
  height: 100px;
}

.header {
  font-size: 20px;
  color: #333;
}

.open-modal-button {
  padding: 10px 20px;
  background-color: #D2B48C;
  color: #333;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.open-modal-button:hover {
  background-color: #EED8AE;
}

</style>
