<template>
  <div class="child">
    <h2>Child Component</h2>
    <textarea v-model="message" cols="30" rows="10"></textarea>
    <button @click="showGrandchild = true" class="open-modal-button">Grandchild Component</button>
    <button @click="sendMessageToParent" class="send-message-button">Send Message to Parent</button>
    <Modal v-if="showGrandchild" @close="showGrandchild = false">
      <GrandchildComponent @grandchildEvent="handleGrandchildEvent" />
    </Modal>
  </div>
</template>

<script>
import GrandchildComponent from './GrandChildComponent.vue';
import Modal from './Modal.vue';

export default {
  name: 'ChildComponent',
  components: {
    GrandchildComponent,
    Modal,
  },
  data() {
    return {
      showGrandchild: false,
      message: 'Ini Komponen Anak'
    };
  },
  methods: {
    sendMessageToParent() {
      this.$emit('childEvent', this.message);
    },
    handleGrandchildEvent(message) {
      this.$emit('childEvent', message);
    },
  },
};
</script>

<style scoped>
.child {
  padding: 20px;
  border: 2px solid #D2B48C;
  border-radius: 10px;
  margin-top: 15px;
  background-color: #FFE4B5;
  transition: all 0.3s ease;
  font-size: 20px;
}
.child:hover {
  background-color: #FFDAB9;
}
button {
  padding: 10px 20px;
  background-color: #D2B48C;
  color: #333;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  margin-top: 10px;
}
button:hover {
  background-color: #EED8AE;
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

h2 {
  font-size: 20px;
}

.send-message-button {
  margin-left: 10px;
}
</style>