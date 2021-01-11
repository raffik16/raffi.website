<template>
  <!-- Main Parent Index Div -->
  <div class="main-parent about-page">
    <header class="header-wrap">
      <!-- Import hero header -->
      <hero-header />
    </header>

    <div class="container meta">
      <img src="~/static/images/25.gif" class="img" />
      <div>
        <p>
          Howdy! Here's some fun about me; I LOVE making the internet a safer
          and more useable place. Experiencing a glitch free web page is a BIG
          WIN. I can find a glitch in just about every website. I've been doing
          this for 11 years.
        </p>
        <p>
          Finding a solution for the glitch is the next step. At times the
          approach can be extremely simple or extremely complicated.
        </p>
        <p>
          My favorite sport is baseball as its one of the most strategic major
          league sports. It takes 100% commitment from each player to win a ball
          game. Similarly to winning a product launch. It takes 100% commitment
          from everyone.
        </p>
        <p>
          Being outdoors is another one of my favorite hobbies. It's Another
          thing that requires granular a nitty-gritty lifestyle in order to
          Succeed.
        </p>
        <p>
          There are a lot of real world applications that we can take notes from
          and apply them to our art.
        </p>
      </div>
    </div>

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
          content: "About Raffi Keklikian" // Insert description from API
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
/deep/ nav.navbar {
  position: relative !important;
}
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
  position: relative;
  z-index: 40;
  width: 100%;
  left: 0;
  top: 0;
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
  font-family: "lotasemibold";
  font-size: 18px;
  line-height: 1;
  padding: 0 30px;
}

.meta {
  display: flex;
  margin-bottom: 45px;

  @media (max-width: 1024px) {
    flex-direction: column;
  }
}

.img {
  @media (max-width: 1024px) {
    margin-bottom: 30px;
  }
}
</style>
