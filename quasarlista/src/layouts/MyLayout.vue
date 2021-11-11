<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-purple-10 q-mx-none">
        <div class=" q-py-xl q-sb-md q-mx-auto">
          <div class="text-h3">
            Dyndo - Lista de tarefas
            <span v-if="$q.platform.is.ios">IOS</span>
            <span v-else-if="$q.platform.is.mac">Mac</span>
          </div>
          <div class="text-subtitle q-py-sm q-mr-none">{{ todaysDate }}</div>
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <keep-alive>
        <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { date } from "quasar";

export default {
  name: "MyLayout",

  data() {
    return {
      leftDrawerOpen: false
    };
  },
  computed: {
    todaysDate() {
      let timeStamp = Date.now();
      return date.formatDate(timeStamp, "dddd M MMMM YYYY");
    }
  }
};
</script>

<style lang="scss">
.header-image {
  height: 100%;
  z-index: -1;
  opacity: 0.5;
  filter: grayscale(100%);
}
</style>
