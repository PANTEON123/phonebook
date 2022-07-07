<template>
  <div id="list">
    <ul>
      <li class="item" v-for="(line, index) in lines" :key="index">
        <span class="name">{{ line.name }}: </span>
        <span>{{ line.number }}</span>
        <button class="button" @click="$emit('delete', index)">
          <img
            src="https://cdn-icons-png.flaticon.com/512/151/151882.png"
            alt="Удалить контакт"
          />
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "contacts-list",
  data() {
    return {};
  },
  props: ["lines"],
};
</script>

<style scoped>
#list {
  margin-left: -14px;
}

img {
  width: 10px;
}

button {
  background-color: transparent;
  border-style: none;
  margin: 0px 20px 0px auto;
}

.item {
  display: flex;
  align-items: center;
  padding: 10px 0px;
}

.item:not(:last-child) {
  margin-bottom: 5px;
  border-bottom: 1px solid #000;
}

.name {
  width: 150px;
}
</style>