<template>
  <navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index) => (activePage = index)"
  >
  </navbar>
  <page-viewer :page="pages[activePage]"></page-viewer>
</template>

<script>
import PageViewer from "./components/PageViewer.vue";
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    Navbar,
    PageViewer,
  },
  data() {
    return {
      activePage: 0,
      pages: [
        {
          link: { text: "Home", url: "index.html" },
          pageTitle: "Hello, Vue",
          content: "Welcome to a wonderful world of View",
        },
        {
          link: { text: "About", url: "about.html" },
          pageTitle: "About",
          content: "Welcome to about page",
        },
        {
          link: { text: "Contact", url: "contact.html" },
          pageTitle: "Contact",
          content: "Contact me",
        },
      ],
    };
  },
};
</script>
