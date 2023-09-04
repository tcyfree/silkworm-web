<script setup>
// example components
import DefaultNavbar from "../../../examples/navbars/NavbarDefault.vue";
import Header from "../../../examples/Header.vue";
import DefaultFooter from "../../../examples/footers/FooterDefault.vue";

// sections
import Footer from "../Author/Sections/AuthorFooter.vue";
import Profile from "./PurportProfile.vue";
import Posts from "../Author/Sections/AuthorPosts.vue";
import Contact from "../Author/Sections/AuthorContact.vue";

// image
import image from "@/assets/img/city-profile.jpg";
import silkworm from "@/assets/img/silkworm.png";
import vueMkHeader from "@/assets/img/bg6.png";

</script>
<template>
  <DefaultNavbar transparent />
  <Header>
    <div
      class="page-header min-height-400"
      :style="{ backgroundImage: `url(${vueMkHeader})` }"
      loading="lazy"
    >
    </div>
  </Header>
  <div class="card card-body blur shadow-blur mx-3 mx-md-4 mt-n6 mb-4">
    <Profile />
  </div>
  <DefaultFooter />
</template>
