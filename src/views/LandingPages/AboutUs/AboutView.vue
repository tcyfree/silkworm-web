<script setup>
import { onMounted, onUnmounted } from "vue";

//example components
import DefaultNavbar from "../../../examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../../examples/footers/FooterDefault.vue";

//image
import bg0 from "@/assets/img/bg4.png";

//dep
import Typed from "typed.js";

//sections
import Information from "./Sections/AboutInformation.vue";
import AboutTeam from "./Sections/AboutTeam.vue";
import Featuring from "./Sections/AboutFeaturing.vue";
import Newsletter from "./Sections/AboutNewsletter.vue";
import Profile from "./Sections/Profile.vue";

const body = document.getElementsByTagName("body")[0];
//hooks
onMounted(() => {
  body.classList.add("about-us");
  // body.classList.add("bg-gray-200");

  if (document.getElementById("typed")) {
    // eslint-disable-next-line no-unused-vars
    var typed = new Typed("#typed", {
      stringsElement: "#typed-strings",
      typeSpeed: 90,
      backSpeed: 90,
      backDelay: 200,
      startDelay: 500,
      loop: true,
    });
  }
});

onUnmounted(() => {
  body.classList.remove("about-us");
  body.classList.remove("bg-gray-200");
});
</script>
<template>
  <DefaultNavbar
    transparent
  />
  <Header>
    <div
      class="page-header min-height-400"
      :style="{ backgroundImage: `url(${bg0})` }"
      loading="lazy"
    >
      <span class="mask bg-gradient-success opacity-3"></span>
    </div>
  </Header>
  <!-- <div class="card card-body blur shadow-blur mx-3 mx-md-4 mt-n6 mb-4">
    <Profile />
  </div> -->
  <div class="card card-body shadow-xl mx-3 mx-md-4 mt-n6">
    <Information />
    <!-- <AboutTeam /> -->
  </div>
  <DefaultFooter />
</template>
