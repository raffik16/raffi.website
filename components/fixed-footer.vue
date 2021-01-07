<template>
    <!-- Toggle class based on mouseenter/mouseleave/click -->
    <div class="footer-liner" :class="{'ig-hovering' : hoverOverIg, 'contact-hovering' : hoverOverContact }">
        <a href="https://instagram.com/ranchedruffles"
              target="_blank"
              class="ig-a"
              @click="hoverOverIg = true"
              @mouseenter="hoverOverIg = true"
              @mouseleave="hoverOverIg = false">
            Instagram
        </a>
        <a class="contact-a"
              href="mailto:raffi.website@gmail.com"
              @click="hoverOverContact = true"
              @mouseenter="hoverOverContact = true"
              @mouseleave="hoverOverContact = false">
            Contact
        </a>
    </div>
</template>

<script>
export default {
    name: "hero-footer",
    data: () => {
    return {
      hoverOverIg: false, // Default hoverOverIg = false
      hoverOverContact: false
    }
  },
}
</script>

<style scoped>
.footer-liner {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 90%;
  color: #fff;
  text-shadow: 1px 1px 1px #000;
  position: fixed;
  left: 50%;
  margin-left: -45%;
  right: 0;
  bottom: 4%;
}

a {
    font-family: 'lotasemibold';
    text-transform: uppercase;
    font-size: 14px;
    position: relative;
}

.ig-hovering .ig-a::after,
.contact-hovering .contact-a::after {
    background-color: #fff;
    transition: all 1s ease 0s;
    width: 100%;
    box-shadow: 1px 1px 1px #000;
}

a::after {
    content: "";
    width: 0;
    height: 1px;
    left: 0;
    bottom: 0;
    position: absolute;
    transition: all 1s ease 0s;
}
</style>