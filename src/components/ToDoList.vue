<template>
  <div>
    <ul>
      <li v-for="(item, index) in toDoList" :key="index">
        <span class="item">{{ item.name }}</span>
        <span class="delete" @click="deleteData(index)">X</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    toDoList: {
      type: Array,
      required: true,
    },
    deleteData: {
      type: Function,
      required: true,
    },
  },
  setup() {
    return {};
  },
};
</script>

<style scoped>
li {
  display: flex;
  margin-top: 10px;
  justify-content: center;
}
.delete {
  background-color: red;
  color: white;
  padding: 0px 10px;
  border: black solid;
  border-radius: 8px;

  cursor: pointer;
}

.item {
  width: 100px;
}
</style>
