<template>
  <!-- Main Parent Index Div -->
  <div class="main-parent">


    <header class="header-wrap">
      <!-- Import hero header -->
      <hero-header />
    </header>
    
    <div class="centering-block">

        <img src="~/static/images/25.gif" alt="">

        <p>
            Hello, My Name Is Raffi. I'm A Web Developer Based In Los Angeles, CA. 
        </p>
    </div>

    <footer class="footer-wrap">
        <footer-cmp />
      <!-- Import hero footer -->
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
          hid: 'description', //  Must use hid
          name: 'description', // Type of meta property
          content: "About Raffi Keklikian" // Insert description from API
        }
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
.centering-block {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
}
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

p {
     font-family: 'lotasemibold';
     font-size: 30px;
     line-height: 1;
}
</style>