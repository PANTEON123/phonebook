<template>
  <div id="app">
    <div id="title">Список контактов</div>
    <headMenu @clear="clearHandler" @add="pageName = 'adding'" />
    <List v-if="pageName === 'main'" :lines="lines" @delete="deleteContacts" />
    <appContacts
      v-if="pageName === 'adding'"
      @cancel="pageName = 'main'"
      @save="saveHandler"
    />
    <endMenu />
  </div>
</template>

<script>
import headMenu from "@/components/headMenu";
import List from "@/components/List";
import appContacts from "@/components/appContacts";

export default {
  name: "App",
  components: {
    headMenu,
    List,
    appContacts,
  },
  data() {
    return {
      pageName: "main",
      lines: [
        { name: "Brikov Evgeny", number: "123125235" },
        { name: "Ivan Ivanov", number: "98374597" },
      ],
    };
  },
  methods: {
    clearHandler() {
      this.lines = [];
    },
    saveHandler(data) {
      this.lines.push(data);
      this.pageName = "main";
    },
    deleteContacts(index) {
      this.lines.splice(index, 1);
    },
  },
};
</script>

<style>
body {
  margin: 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: url('https://proprikol.ru/wp-content/uploads/2019/08/kartinki-na-zadnij-fon-16.jpg')
}

#app {
  width: 40vw;
  height: 60vh;
  background: rgba(255, 255, 255, 0.9);
  color: #000;
  font-family: Lucida Console;
  border-radius: 0px 0px 20px 20px;
  overflow: auto;
}

#title {
  padding: 20px;
  padding-bottom: 0px;
  margin-bottom: 20px;
  text-align: right;
  font-size: 35px;
}

button:hover {
  cursor: pointer;
  transform: translateY(-2px);
}
</style>
