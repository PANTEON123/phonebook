<template>
  <div id="headMenu">
    <button @click="$emit('clear')" id="delButt" class="menuBut">
      Удалить все
    </button>
    <button id="addButt" class="menuBut" @click="$emit('add')">
      Добавить +
    </button>
  </div>
</template>

<script>
export default {
  name: "headMenu",
  data() {
    return {};
  },
};
</script>

<style scoped>
#headMenu {
  display: flex;
  border-bottom: 1px solid #000;
  padding: 0px 20px 20px;
}

.menuBut:first-child {
  margin-right: 10px;
}

.menuBut {
  width: 150px;
  padding: 5px;
  background: transparent;
  font-family: Lucida Console;
  border-radius: 1px;
}
</style>