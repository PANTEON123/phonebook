<template>
  <div id="inpContacts">
    <div class="label">
      <span class="title">Имя: </span>
      <input v-model="inputs.name" type="text" class="inputName" />
    </div>
    <div class="label">
      <span class="title">Номер: </span>
      <input v-model="inputs.number" type="text" class="inputName" />
    </div>
    <div>
      <button class="button" @click="$emit('cancel')">Отмена</button>
      <button class="button" @click="$emit('save', inputs)">Сохранить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "appContacts",
  data() {
    return {
      inputs: {
        name: "",
        number: "",
      },
    };
  },
};
</script>

<style scoped>
#inpContacts {
  display: flex;
  flex-direction: column;
  padding: 20px;
}

.label {
  display: flex;
  margin-bottom: 20px;
}

.title {
  width: 80px;
  margin-right: 20px;
}

.button:first-child {
  margin-right: 10px;
}

.button {
  background: transparent;
  padding: 5px;
}
</style>