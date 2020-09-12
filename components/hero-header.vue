<template>
  <header id="home">
        <div class="container">
            <nav class="navbar navbar-expand-lg navbar-dark">
                <nuxt-link to="/" class="navbar-brand">
                    <h2>RK</h2>
                </nuxt-link>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarTogglerDemo" aria-controls="navbarTogglerDemo" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div id="navbarTogglerDemo" class="collapse navbar-collapse">
                    <ul class="navbar-nav ml-auto">
                        <!-- <li class="nav-item active">
                            <a href="#home" class="nav-link">Home</a>
                        </li> -->
                        <li class="nav-item">
                            <a href="#portfolio" class="nav-link">Portfolio</a>
                        </li>
                        <li class="nav-item">
                          <nuxt-link to="/about" class="nav-link" :prefetch="false">About</nuxt-link>
                        </li>
                        <li class="nav-item">
                            <a href="mailto:raffi.website@gmail.com" class="nav-link">Contact</a>
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
    finishingHoverOver: false, 
    editorsHoverOver: false, 
    }
  },
}
</script>

<style scoped>
.header-liner {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  color: #fff;
}

.logo-wrap {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.logo {
  max-width: 40px;
}

.exile {
  font-family: 'Bitter', serif;
  text-transform: uppercase;
  letter-spacing: 5px;
  margin-left: 20px;
}

.bar {
  background: #fff;
  height: 1px;
  width: 90px;
  margin: 0 25px;
  position: absolute;
  right: 28px;
  top: 60px;
  transition: all .3s ease-in-out 0s;
}

.menu {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-family: 'lotasemibold';
  text-transform: uppercase;
  font-size: 18px;
}

.editors-item {
  position: relative;
  transition: left .3s ease-in-out 0s;
  left: 0;
}

span.editors-item {
  margin-right: 15px;
}


@media(min-width:768px) {

  .bar {
    background: #fff;
    height: 1px;
    width: 100px;
    margin: 0 25px;
    position: absolute;
    right: 90px;
    top: auto;
    transition: all .3s ease-in-out 0s;
  }

  span.editors-item {
      margin-right: 150px;
  }

  .is-hovering-editors .editors-item {
    transition: left .3s ease-in-out 0s;
    left: -20px;
  }

  .is-hovering-editors .bar {
    right: 90px;
    width: 110px;
  }

  .finishing-item {
    position: relative;
    transition: right .3s ease-in-out 0s;
    right: 0;
  }

  .is-hovering-finishing .bar {
    right: 80px;
    width: 110px;
  }

  .is-hovering-finishing .finishing-item {
    transition: right .3s ease-in-out 0s;
    right: -20px;
  }

}

</style>