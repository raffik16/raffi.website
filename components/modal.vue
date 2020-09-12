<template>
      <transition name="modalFade">
  <div class="modal modal-mask" v-show="value">
    <div class="container">
      <div class="modal__title">Direction</div>
      <p>Get a direction with your favourite apps</p>
      <a href="#" class="btn gmaps">
        <img src="https://img.icons8.com/color/420/google-maps.png" /> Google Maps
      </a>
      <a href="#" class="btn waze">
        <img src="https://img.icons8.com/color/420/waze.png" /> Waze
      </a>
      <button @click.prevent="close" class="mt-3 border-b border-teal font-semibold">Close</button>
    </div>
  </div>
      </transition>
</template>

<script>
export default {
  name: "modal",
  props: {
    value: {
      required: true,
    },
  },
  methods: {
    close() {
        this.$emit("input", !this.value);
        var element = document.getElementById("modalWrap");
        // element.classList.remove("showing-modal");
    },
  },
};
</script>

<style>
.modal {
  background-color: rgba(0, 0, 0, 0.7);
}

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modalFade-enter {
  opacity: 0;
}

.modalFade-leave-active {
  opacity: 0;
}

.modalFade-enter .modalFade-container,
.modalFade-leave-active .modalFade-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>