<template>
  <app-navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index) => (activePage = index)"
  >
  </app-navbar>

  <page-viewer v-if="pages.length > 0" :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from "./components/PageViewer.vue";
import AppNavbar from "./components/AppNavbar.vue";

export default {
  components: {
    AppNavbar,
    PageViewer,
  },
  created() {
    this.getPages();
  },
  data() {
    return {
      activePage: 0,
      pages: [],
    };
  },
  methods: {
    async getPages() {
      let res = await fetch("pages.json");
      let data = await res.json();

      this.pages = data;
    },
  },
};
</script>
