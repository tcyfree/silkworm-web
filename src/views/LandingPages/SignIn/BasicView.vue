<script setup>
import { onMounted } from "vue";

// example components
import DefaultNavbar from "@/examples/navbars/NavbarDefault.vue";
import Header from "@/examples/Header.vue";

//Vue Material Kit 2 components
import MaterialInput from "@/components/MaterialInput.vue";
import MaterialSwitch from "@/components/MaterialSwitch.vue";
import MaterialButton from "@/components/MaterialButton.vue";
import vueMkHeader from "@/assets/img/silkworm.jpg";

// material-input
import setMaterialInput from "@/assets/js/material-input";
onMounted(() => {
  setMaterialInput();
});
</script>
<template>
  <DefaultNavbar transparent />
  <Header>
    <div
      class="page-header align-items-start min-vh-100"
      :style="`background-image: url(${vueMkHeader})`"
      loading="lazy"
    >
      <div class="container my-auto">
        <div class="row">
          <div class="col-lg-4 col-md-8 col-12 mx-auto">
            <div class="card z-index-0 fadeIn3 fadeInBottom">
              <div
                class="card-header p-0 position-relative mt-n4 mx-3 z-index-2"
              >
                <div
                  class="bg-gradient-success shadow-success border-radius-lg py-3 pe-1"
                >
                  <h4
                    class="text-white font-weight-bolder text-center mt-2 mb-0"
                  >
                    通过第三方账号登录
                  </h4>
                  <div class="row mt-3">
                    <div class="col-2 text-center ms-auto">
                      <a class="btn btn-link px-3" href="javascript:;">
                        <i class="fa fa-facebook text-white text-lg"></i>
                      </a>
                    </div>
                    <div class="col-2 text-center px-1">
                      <a class="btn btn-link px-3" href="javascript:;">
                        <i class="fa fa-github text-white text-lg"></i>
                      </a>
                    </div>
                    <div class="col-2 text-center me-auto">
                      <a class="btn btn-link px-3" href="javascript:;">
                        <i class="fa fa-google text-white text-lg"></i>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
              <div class="card-body">
                <form role="form" class="text-start">
                  <MaterialInput
                    id="email"
                    class="input-group-outline my-3"
                    :label="{ text: '账号', class: 'form-label' }"
                    type="text"
                  />
                  <MaterialInput
                    id="password"
                    class="input-group-outline mb-3"
                    :label="{ text: '密码', class: 'form-label' }"
                    type="password"
                  />
                  <MaterialSwitch
                    class="d-flex align-items-center mb-3"
                    id="rememberMe"
                    labelClass="mb-0 ms-3"
                    checked
                    >记住我</MaterialSwitch
                  >

                  <div class="text-center">
                    <MaterialButton style="font-size: 1.175rem;"
                      class="my-4 mb-2"
                      variant="gradient"
                      color="success"
                      fullWidth
                      >登录</MaterialButton
                    >
                  </div>
                  <p class="mt-4 text-sm text-center">
                    没有账户？
                    <a
                      href="#"
                      class="text-success text-gradient font-weight-bold"
                      >注册</a
                    >
                  </p>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Header>
</template>
