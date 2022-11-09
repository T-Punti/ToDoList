<template>
  <div class="container">
    <CreateItem :createItem="createItem" />
  </div>
</template>

<script>
import { ref } from 'vue';
import CreateItem from './CreateItem.vue';
export default {
  components: {
    CreateItem,
  },

  setup() {
    let data = ref(
      { name: 'Eating' },
      { name: 'Drinking' },
      { name: 'Sleeping' }
    );

    function createItem(item) {
      //data.value.push({ name: item });
      console.log('added' + item);
    }

    return {
      data,
      createItem,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
