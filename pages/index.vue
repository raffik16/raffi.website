<template>
  <!-- Main Parent Index Div -->
  <div class="main-parent">
    <header class="header-wrap">
      <!-- Import hero header -->
      <hero-header />
    </header>

    <!-- Import hero images + titles -->
    <hero />
    <!-- <posts /> -->

    <footer-cmp />

    <footer class="footer-wrap">
      <!-- Import fixed footer -->
      <fixed-footer />
    </footer>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "my website", // Grab title from API
      meta: [
        {
          hid: "description", //  Must use hid
          name: "description", // Type of meta property
          content: "Welcome to raffi.website" // Insert description from API
        }
      ]
    };
  }
};
</script>

<style scoped>
.header-wrap {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  position: absolute;
  z-index: 40;
  width: 90%;
  left: 50%;
  margin-left: -45%;
  top: 30px;
}

.footer-wrap {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  position: absolute;
  z-index: 40;
  width: 90%;
  left: 50%;
  margin-left: -45%;
  bottom: 30px;
}
</style>
