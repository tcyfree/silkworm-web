<script setup>
import { onMounted } from "vue";

//example components
import DefaultNavbar from "@/examples/navbars/NavbarDefault.vue";
import DefaultFooter from "@/examples/footers/FooterDefault.vue";

//image
import image from "@/assets/img/illustrations/illustration-signin.jpg";
//image
import bg0 from "@/assets/img/bg9.jpg";

//material components
import MaterialInput from "@/components/MaterialInput.vue";
import MaterialTextArea from "@/components/MaterialTextArea.vue";
import MaterialButton from "@/components/MaterialButton.vue";

// material-input
import setMaterialInput from "@/assets/js/material-input";
onMounted(() => {
  setMaterialInput();
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
  
  <div class="card card-body shadow-xl mx-3 mx-md-4 mt-n6">
    <section>
    <div class="page-header">
      <div class="container">
        <div class="row">
          <div
            class="mt-6 col-xl-5 col-lg-6 col-md-7 d-flex flex-column ms-auto me-auto ms-lg-auto"
          >
            <div
              class="card d-flex blur justify-content-center shadow-lg my-sm-0 my-sm-6 mt-8 mb-5"
            >
              <div
                class="card-header p-0 position-relative mt-n4 mx-3 z-index-2 bg-transparent"
              >
                <div
                  class="bg-gradient-success shadow-success border-radius-lg p-3"
                >
                  <h3 class="text-white text-success mb-0">联系我们</h3>
                </div>
              </div>
              <div class="card-body">
                <p class="pb-3">
                  有关进一步的问题，包括合作机会，请发送电子邮件至liaotoad@gmail.com。
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  </div>
  <DefaultFooter />
</template>
