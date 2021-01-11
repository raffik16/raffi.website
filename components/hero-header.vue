<template>
  <header id="home">
    <div class="container">
      <nav class="navbar navbar-expand-lg navbar-dark">
        <nuxt-link to="/" class="navbar-brand">
          <h2>RK</h2>
        </nuxt-link>
        <button
          @click="myFilter"
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarTogglerDemo"
          aria-controls="navbarTogglerDemo"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          id="navbarTogglerDemo"
          class="collapse navbar-collapse"
          :class="{ show: isActive }"
        >
          <ul class="navbar-nav ml-auto">
            <!-- <li class="nav-item active">
                            <a href="#home" class="nav-link">Home</a>
                        </li> -->
            <li class="nav-item">
              <nuxt-link
                to="/#portfolioSection"
                class="nav-link portfolio-li"
                :prefetch="false"
                >Home</nuxt-link
              >
            </li>
            <li class="nav-item">
              <nuxt-link to="/about" class="nav-link" :prefetch="false"
                >About</nuxt-link
              >
            </li>
            <li class="nav-item">
              <a href="mailto:raffi.website@gmail.com" class="nav-link"
                >Contact</a
              >
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  name: "hero-header",
  data: () => {
    return {
      isActive: false
    };
  },
  methods: {
    scrollToElement() {
      // var element = document.getElementById("portfolioSection");
      // var top = element.offsetTop;
      // window.scrollTo(0, top);
    },
    myFilter: function() {
      this.isActive = !this.isActive;
      // some code to filter users
    }
  }
};
</script>

<style scoped lang="scss">
.header-liner {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  color: #fff;
}

.menu {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: "lotasemibold";
  text-transform: uppercase;
  font-size: 18px;
}

header {
  width: 100%;
  background: none;

  li {
    text-align: right;
    font-family: "lotasemibold";
    font-size: 18px;
  }
}

@media (max-width: 768px) {
  .navbar .navbar-nav .nav-item .nav-link {
    padding-right: 0;
  }

  .navbar {
    padding: 8px 17px;
    margin: 0;
  }

  .navbar .navbar-toggler {
    background: none;
  }
}

nav.navbar.navbar-expand-lg.navbar-dark {
  background: none;
  position: fixed;
  z-index: 50;
  left: 0;
  top: 0;
  width: 100%;
}
</style>
