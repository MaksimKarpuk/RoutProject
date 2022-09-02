<template>
  <div>
    <NuxtLink to="/">Main</NuxtLink>
    <NuxtLink
      v-for="link in links"
      :key="link.id"
      :to="link.path"
      :class="[{ [$style.active]: link.isActive }]"
      @click.native="changeLinkStatus(link.text)"
    >
      {{ link.text }}</NuxtLink
    >
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          isActive: false,
          path: "/contacts",
          id: 2,
          text: "Contacts",
        },
        {
          isActive: false,
          path: "/delivery",
          id: 3,
          text: "Delivery",
        },
        {
          isActive: false,
          path: "/promotions",
          id: 4,
          text: "Promotions",
        },
      ],
      fullPath: this.$route.path,
    };
  },
  mounted() {
    this.setActiveLink();
  },
  computed: {
    getPath() {
      return this.$route.path;
    },
  },
  methods: {
    setActiveLink() {
      let activeLink = "";
      const fullPath = this.$route.path;
      switch (fullPath) {
        case "/contacts":
          activeLink = "Contacts";
          break;
        case "/delivery":
          activeLink = "Delivery";
          break;
        case "/promotions":
          activeLink = "Promotions";
          break;
        default:
          activeLink = "";
      }
      this.changeLinkStatus(activeLink);
    },
    changeLinkStatus(text) {
      this.links.map((link) =>
        link.text === text ? (link.isActive = true) : (link.isActive = false)
      );
    },
  },
  watch: {
    getPath() {
      this.setActiveLink();
    },
  },
};
</script>

<style lang="scss" module>
.active {
  color: red;
}
</style>

