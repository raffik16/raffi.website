<template>
<div>

  <!-- Hero main parent has a hovering class. -->
  <div class="hero-center" :class="{'is-hovering' : hoverOver }">

    <!-- Use Native transtion-group -->
      <transition-group class="slider" name="slide" tag="div">
        
        <!-- Loop through and assign slides a unique key. -->
        <div
          v-for="number in [currentNumber]"
          :key="number"
          class="slider-parent">

          <!-- Hero Title wrap with hover state -->
          <div class="hero-title-wrap"
              @mouseenter="hoverOver = true"
              @mouseleave="hoverOver = false"
              @click="hoverOver = true">

            <!-- Hero title Render -->
            <div class="hero-header">
                {{slideshowsubTitles}}
            </div>

            <!-- Hero Subtitle Render -->
            <div class="hero-sub-header">
              <span v-html="currentTitle"></span>
            </div>

            <!-- Hero Play button Render -->
            <div class="play">
              <span>&#x25B6;</span> Play
            </div>
          </div>

          <!-- Image Render -->
          <img :src="currentImage" />

      </div>
    </transition-group>

  </div>
</div>
</template>

<script>

import database from '~/static/db.json';

export default {
  name: "hero",

// startRotation and dataMap on mount().
  mounted: function () {
    this.startRotation();
    this.mapData();
  },

  methods: {
    mapData: function() {
        // Map API database in forEAch() in one call
        this.database.pages.forEach(({ featuredImage, title }) => {
          // Update local array
          this.images.push(`https:${featuredImage.sourceUrl}`);
          this.subTitles.push(featuredImage.title);
          this.titles.push(title);
        });
    },

    // Rotation interval set to 7 seconds.
    startRotation: function() {
        this.timer = setInterval(this.next, 8200);
    },

    // Update currentNumber by 1
    next: function() {
        this.currentNumber += 1
    }
  },

  data: () => {
    return {
      database : database, // Set top level array
      images: [], // Set images array to be updated with api.
      titles: [], // Set titles array to be updated with api.
      subTitles: [], // Set subTitles array to be updated with api.
      currentNumber: 0, // Default currentNumber = 0
      timer: 0, // Default timer = 0
      hoverOver: false, // Default hoverOver = false
    }
  },
  
  computed: {
    // Return currentNumber to match up with currentImage.
    currentImage: function() {
      return this.images[Math.abs(this.currentNumber) % this.images.length];
    },

    // Return currentNumber to match up with currentTitle.
    currentTitle: function() {
      return this.titles[Math.abs(this.currentNumber) % this.titles.length];
    },

    // Return currentNumber to match up with slideshowsubTitles.
    slideshowsubTitles: function() {
      return this.subTitles[Math.abs(this.currentNumber) % this.subTitles.length];
    },
  },
}
</script>

<style scoped>
/* Default Hero Styles */
.slider {
    height: 75vh;
    overflow: hidden;
    background: #000;
    position: relative;
    z-index: 10;
}

.slide-leave-to {
  overflow: hidden;
  position: relative;
  transition: transform 3s cubic-bezier(0.76, 0, 0.5, 1);
  transform: translate3d(0, -100%, 0);
  z-index: 30;
  backface-visibility: hidden;
  will-change: transform;
}

.slide-enter-to {
  overflow: hidden;
  position: relative;
  transition: transform 3s cubic-bezier(0.76, 0, 0.5, 1);
  transform: translate3d(0, -100%, 0);
  z-index: 40;
  backface-visibility: hidden;
  will-change: transform;
}

.slide-leave-to .hero-title-wrap {
  transition: top 3s cubic-bezier(0.76, 0, 0.5, 1);
  top: 150%;
  /* z-index: 0; */
}

.slide-enter-to .hero-title-wrap {
  z-index: 40;
}

.hero-center .play {
  opacity: 0;
  transition: opacity .25s ease-in-out 0s;
  font-family: 'lotasemibold';
  text-transform: uppercase;
  font-size: 18px;
  text-shadow: 1px 2px 1px #000;
}

.hero-center.is-hovering .play {
  opacity: 1;
  transition: opacity .25s ease-in-out 0s;
}

.play span {
  margin-right: 10px;
}

.hero-title-wrap {
    position: absolute;
    text-align: left;
    color: #fff;
    top: 350px;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 10;
    min-width: 75%;
}

.slider-parent {
  position: relative;
  backface-visibility: hidden;
  will-change: transform;
  height: 75vh;
}

.hero-header {
  font-size: 42px;
  line-height: 40px;
  font-family: 'lotasemibold';
  transition: top .25s ease-in-out 0s;
  top: 0;
  position: relative;
  text-transform: capitalize;
  text-shadow: 1px 2px 1px #000;
}

.is-hovering .hero-header {
  transition: top .25s ease-in-out 0s;
  top: -7px;
}

.hero-sub-header {
  font-size: 28px;
  transition: top .25s ease 0s;
  top: 0;
  position: relative;
  padding: 22px 0 22px;
  text-transform: capitalize;
  text-shadow: 1px 2px 1px #000;
}

.is-hovering .hero-sub-header {
  transition: top .25s ease 0s;
  top: -7px;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Fill Animations */
@keyframes fill {
  0% {
    width: 0%;
  }
  100% {
    width: 100%;
  }
}

@keyframes dropIn {
  0% {
    transform: translate(-50%, -600px);
  }
  100% {
    transform: translate(-50%, -50%);
  }
}

/* Media Quires for main background image. */
@media(min-width:768px) {
  .hero-title-wrap {
    top: 350px;
  }

   .hero-header {
      font-size: 72px;
      line-height: 69px;
  }
}


@media(min-width:1200px) {
  img {
   transform: none;
   height: 75vh;
  }
}

</style>
