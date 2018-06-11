<template>
  <div>
    <h1>Welcome to the  {{ msg2 }}</h1>
    <h2> Please add something to your list </h2>
      <input v-model="newItem" type="text" placeholder="your item">
      <button v-on:click="addItem()" class="btn btn-primary"> add </button>
      <button v-on:click="removeItem()" class="btn btn-danger"> clear </button>
    <li v-for="(item, index) in items" :key="index"> {{ item }} </li>

  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "Welcome to the ToDoList",
      msg2: "List test",
      newItem: "",
      items: [],
    };
  },
  methods: {
    addItem() {
      this.items.push(this.newItem);
      this.newItem = "";
    },
    removeItem() {
      this.items = [];
    }
  },
  computed: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
