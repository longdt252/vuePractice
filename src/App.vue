<template>
  <div class="container">
      <div class="row">
        <Header :propsMaxItem="maxItem" :propsItemCount="items.length"></Header>
      </div>
      <div class="row">
        <AddItem @item-added="addItemParent" :propsItems="items"></AddItem>
        <ItemsLayout :propsItems="items" @deleted-item="delItem"></ItemsLayout>
      </div>
  </div>
</template>
<script>
import Header from './components/Header.vue';
import ItemsLayout from './components/ItemsLayout.vue';
import AddItem from './components/AddItem.vue';

export default {
  name: 'App',
  components: {
    Header, ItemsLayout , AddItem
  },
  data:() => {
    return {
      items: [],
      maxItem: 10,
    }
  },
  methods: {
    addItemParent(item){
      this.items.push(item);
    },
    delItem(index){
      this.items.splice(index, 1);
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
</style>
