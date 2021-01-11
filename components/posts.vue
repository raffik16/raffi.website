<template>
  <div class="container portfolio-section" id="portfolioSection">
    <h1>
      My Art
    </h1>

    <!-- Post main parent has a hovering class. -->
    <div class="posts-center" :class="{ 'is-hovering': hoverOver }">
      <!-- Use Native transtion-group -->
      <!-- <transition-group class="slider" name="slide" tag="div"> -->

      <!-- Loop through and assign slides a unique key. -->
      <div v-for="(item, index) in database" :key="index" class="post-item">
        <img :src="item.meta.full_port_img" />
        <span v-html="item.title.rendered"></span>

        <!-- <button class="" @click="openModal">Open Modal</button> -->

        <!-- <a class="btn" :href="item.meta.site_link" target="_blank">link</a> -->

        <!-- Post Title wrap with hover state -->
        <div
          class="posts-title-wrap"
          @mouseenter="hoverOver = true"
          @mouseleave="hoverOver = false"
          @click="hoverOver = true"
        >
          <!-- Post title Render -->
          <div class="posts-header">
            <!-- <span v-html="title"></span> -->
          </div>

          <!-- Post Subtitle Render -->
          <div class="posts-sub-header">
            <!-- <span v-html="currentTitle"></span> -->
          </div>
        </div>

        <!-- <img :src="currentImage" /> -->
      </div>
      <!-- </transition-group> -->
    </div>

    <!-- <modal-direction v-model="modalOpen"></modal-direction> -->
  </div>
</template>

<script>
import ModalDirection from "~/components/modal";

export default {
  name: "Post",
  // Fetch API data
  // async fetch() {
  //   this.database = await fetch(
  //       "https://raffi.website/wp-json/wp/v2/posts"
  //       // Format result as json
  //       ).then((res) => res.json())
  // },

  // startRotation and dataMap on mount().
  mounted: function() {
    // this.startRotation();
  },

  methods: {
    openModal() {
      this.modalOpen = !this.modalOpen;
    }
  },

  components: {
    ModalDirection
  },

  data: () => {
    return {
      database: [], // Set top level array
      images: [], // Set images array to be updated with api.
      titles: [], // Set titles array to be updated with api.
      subTitles: [], // Set subTitles array to be updated with api.
      currentNumber: 0, // Default currentNumber = 0
      timer: 0, // Default timer = 0
      hoverOver: false, // Default hoverOver = false
      modalOpen: false

      // showModal: false,
      // selectedItem: undefined,
      // items: [
      //   {id:1, name:"name1"},
      //   {id:2, name:"name2"},
      //   {id:3, name:"name3"}
      // ]
    };
  }
};
</script>

<style lang="scss" scoped>
h1 {
  font-family: "lotasemibold";
  padding: 120px 0 20px;
}

.post-item {
  display: flex;
  flex-direction: column;
  flex: 1 0 30%;
  margin: 0 5px 20px;
  font-family: "lotasemibold";

  img {
    width: 100%;
  }

  // &:hover {
  //   background: #91e8c4;
  // }
}

.posts-center {
  display: flex;
  flex-wrap: wrap;
  padding: 0 0 100px;
}
</style>
