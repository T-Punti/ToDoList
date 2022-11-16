<template>
  <div class="container">
    <CreateItem :createItem="createItem" />
    <ToDoList :toDoList="data" :deleteData="removeItem" />
  </div>
</template>

<script>
import { ref } from 'vue';
import CreateItem from './CreateItem.vue';
import ToDoList from './ToDoList.vue';
export default {
  components: {
    CreateItem,
    ToDoList,
  },

  setup() {
    let data = ref([
      { name: 'Eating' },
      { name: 'Drinking' },
      { name: 'Sleeping' },
    ]);

    function createItem(item) {
      console.log('added' + item);
      if (!data.value.includes(item)) data.value.push({ name: item });
    }
    function removeItem(index) {
      data.value.splice(index, 1);
    }

    return {
      data,
      createItem,
      removeItem,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style: none;
}
</style>
