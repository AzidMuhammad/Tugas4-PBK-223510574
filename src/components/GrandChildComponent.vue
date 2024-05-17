<template>
  <div class="grandchild">
    <h2>Grandchild Component</h2>
    <textarea name="" id="" cols="30" rows="10">{{ message }}</textarea>
  </div>
</template>

<script>
export default {
  name: 'GrandchildComponent',
  data() {
    return {
      message: 'Ini Komponen Cucu'
    }
  },
  methods: {
    sendMessageToChild() {
      this.$emit('grandchildEvent', 'Ini Komponen Cucu');
    },
  },
};
</script>

<style scoped>

.grandchild {
  padding: 20px;
  border: 2px solid #D2B48C;
  border-radius: 10px;
  margin-top: 15px;
  background-color: #FFE4B5;
  transition: all 0.3s ease;
}
.grandchild:hover {
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

</style>
