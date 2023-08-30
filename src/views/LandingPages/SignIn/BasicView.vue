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
                <form role="form" class="text-start" @submit.prevent="LogIn">
                  <div class="guest-account">账号: test &nbsp; 密码: 123456</div>
                  <div class="input-group input-group-outline my-3">
                    <label style="font-size: 1rem;" class="form-label">账号</label>
                    <input id="username" type="text" class="form-control"/>
                  </div>
                  <!-- <div class="input-group input-group-outline mb-3">
                    <label style="font-size: 1rem;" class="form-label">密码</label>
                    <input type="password" class="form-control" v-model="password"/>
                  </div> -->
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
<script>
import axios from 'axios';
import { useToast } from 'vue-toastification';

export default {
  data() {
    return {
      // server_url: "http://127.0.0.1:5003",
      server_url: "http://cxy.ssdlab.cn",
      username: '',
      password: '',
    };
  },
  methods: {
    LogIn() {
      const toast = useToast();
      let password = document.getElementById("password").value;
      let username = document.getElementById("username").value;
      console.log(username, password)
      if (!username || !password) {
        toast.warning("请填写账号或密码", {
          position: "top-right",
          timeout: 3000,
        });
        return
      }
      const data = {
        username: username,
        password: password
      };
      axios.post(this.server_url + "/api/passport/login", data)
        .then((response) => {
          if (response.data.success === true) {
            toast.success(response.data.msg, {
              position: "top-right",
              timeout: 3000,
            });
            localStorage.setItem('LoggedIn', true)
            window.location.href = '/';
          } else {
            toast.error(response.data.msg, {
              position: "top-right",
              timeout: 3000,
            });
          }
        })
        .catch(error => {
          console.log(error)
          toast.error('Login error', {
              position: "top-right",
              timeout: 3000,
          });
        });
    },
  },
};
</script>
<style scoped>
.guest-account {
    text-align: center;
    color: #9abcda!important;
    font-size: 1rem;
}
</style>
