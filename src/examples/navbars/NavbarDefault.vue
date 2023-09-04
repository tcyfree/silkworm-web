<script setup>
import { RouterLink } from "vue-router";
import { ref, watch } from "vue";
import { useWindowsWidth } from "../../assets/js/useWindowsWidth";

// images
import ArrDark from "@/assets/img/down-arrow-dark.svg";
import downArrow from "@/assets/img/down-arrow.svg";
import DownArrWhite from "@/assets/img/down-arrow-white.svg";
import iconAvator from "@/assets/img/icon.png";
import defaultAvator from "@/assets/img/default-avator.png";

const props = defineProps({
  action: {
    type: Object,
    route: String,
    color: String,
    label: String,
    default: () => ({
      route: "https://www.creative-tim.com/product/vue-material-kit",
      color: "bg-gradient-success",
      label: "Free Download"
    })
  },
  transparent: {
    type: Boolean,
    default: false
  },
  light: {
    type: Boolean,
    default: false
  },
  dark: {
    type: Boolean,
    default: false
  },
  sticky: {
    type: Boolean,
    default: false
  },
  darkText: {
    type: Boolean,
    default: false
  }
});

// set arrow  color
function getArrowColor() {
  if (props.transparent && textDark.value) {
    return ArrDark;
  } else if (props.transparent) {
    return DownArrWhite;
  } else {
    return ArrDark;
  }
}

// set text color
const getTextColor = () => {
  let color;
  if (props.transparent && textDark.value) {
    color = "text-dark";
  } else if (props.transparent) {
    color = "text-white";
  } else {
    color = "text-dark";
  }

  return color;
};

// set nav color on mobile && desktop

let textDark = ref(props.darkText);
const { type } = useWindowsWidth();

if (type.value === "mobile") {
  textDark.value = true;
} else if (type.value === "desktop" && textDark.value == false) {
  textDark.value = false;
}

watch(
  () => type.value,
  (newValue) => {
    if (newValue === "mobile") {
      textDark.value = true;
    } else {
      textDark.value = false;
    }
  }
);
</script>
<template>
  <nav
    class="navbar navbar-expand-lg top-0"
    :class="{
      'z-index-3 w-100 shadow-none navbar-transparent position-absolute my-3':
        props.transparent,
      'my-3 blur border-radius-lg z-index-3 py-2 shadow py-2 start-0 end-0 mx-4 position-absolute mt-4':
        props.sticky,
      'navbar-light bg-white py-3': props.light,
      ' navbar-dark bg-gradient-dark z-index-3 py-3': props.dark
    }"
  >
    <div
      :class="
        props.transparent || props.light || props.dark
          ? 'container'
          : 'container-fluid px-0'
      "
    >
      <RouterLink
        class="navbar-brand d-none d-md-block"
        :class="[
          (props.transparent && textDark.value) || !props.transparent
            ? 'text-dark font-weight-bolder ms-sm-3'
            : 'text-white font-weight-bolder ms-sm-3'
        ]"
        :to="{ name: 'presentation' }"
        rel="tooltip"
        title="Designed and Coded by Creative Tim"
        data-placement="bottom"
      >
        
      </RouterLink>
      <a Placeholder ></a>
      <button
        class="navbar-toggler shadow-none ms-2"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navigation"
        aria-controls="navigation"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon mt-2">
          <span class="navbar-toggler-bar bar1"></span>
          <span class="navbar-toggler-bar bar2"></span>
          <span class="navbar-toggler-bar bar3"></span>
        </span>
      </button>
      <div
        class="collapse navbar-collapse w-100 pt-3 pb-2 py-lg-0"
        id="navigation"
      >
        <ul class="navbar-nav navbar-nav-hover ms-auto">
          <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
            >
              <i class="material-icons opacity-6 me-2 text-md" :class="getTextColor()">home</i>
              <router-link :class="getTextColor()" to="/">首页</router-link>
            </a>
          </li>
          <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
            >
              <i class="material-icons opacity-6 me-2 text-md" :class="getTextColor()">biotech</i>
              <router-link :class="getTextColor()" to="/pages/landing-pages/purport">项目基础情况</router-link>
            </a>
          </li>
          <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
            >
              <i class="material-icons opacity-6 me-2 text-md" :class="getTextColor()">grid_view</i>
              <router-link :class="getTextColor()" to="/pages/landing-pages/scheme">项目规模</router-link>
            </a>
          </li>
          <li class="nav-item dropdown dropdown-hover mx-2">
            <a
              role="button"
              class="nav-link ps-2 d-flex cursor-pointer align-items-center"
              :class="getTextColor()"
              id="dropdownMenuPages"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              <i
                class="material-icons opacity-6 me-2 text-md"
                :class="getTextColor()"
                >people_alt</i
              >
              关于我们
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-2 d-lg-block d-none"
              />
              <img
                :src="getArrowColor()"
                alt="down-arrow"
                class="arrow ms-1 d-lg-none d-block ms-auto"
              />
            </a>
            <div
              class="dropdown-menu dropdown-menu-animation ms-n3 dropdown-md p-3 border-radius-xl mt-0 mt-lg-3"
              aria-labelledby="dropdownMenuPages"
            >
              <div class="row d-none d-lg-block">
                <div class="col-12 px-4 py-2">
                  <div class="row">
                    <div class="position-relative">
                      <div
                        class="dropdown-header text-dark font-weight-bolder d-flex align-items-center px-1"
                      >
                      </div>
                      <RouterLink
                        :to="{ name: 'about' }"
                        class="dropdown-item border-radius-md"
                      >
                        <span>关于我们</span>
                      </RouterLink>
                      <RouterLink
                        :to="{ name: 'contactus' }"
                        class="dropdown-item border-radius-md"
                      >
                        <span>联系我们</span>
                      </RouterLink>
                    </div>
                  </div>
                </div>
              </div>
              <div class="d-lg-none">
                <div
                  class="dropdown-header text-dark font-weight-bolder d-flex align-items-center px-0"
                >
                </div>
                <RouterLink
                  :to="{ name: 'about' }"
                  class="dropdown-item border-radius-md"
                >
                  <span>About Us</span>
                </RouterLink>
                <RouterLink
                  :to="{ name: 'contactus' }"
                  class="dropdown-item border-radius-md"
                >
                  <span>Contact Us</span>
                </RouterLink>
                <RouterLink
                  :to="{ name: 'author' }"
                  class="dropdown-item border-radius-md"
                >
                  <span>Author</span>
                </RouterLink>
              </div>
            </div>
          </li>
          <li class="nav-item dropdown dropdown-hover mx-2">
            <div v-if="LoggedIn" class="nav-link d-flex cursor-pointer align-items-center">
                <img :src="iconAvator" loading="lazy" :style="{ height: '25px'}" data-bs-toggle="modal" data-bs-target="#LogOut"/>
            </div>
            <div v-else class="nav-link d-flex cursor-pointer align-items-center">
              <RouterLink :to="{ name: 'signin-basic' }" title="未登录">
                <img :src="defaultAvator" loading="lazy" :style="{ height: '25px'}"/>
              </RouterLink>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <!-- End Navbar -->
  <!-- The Modal -->
  <div class="modal" id="LogOut">
    <!-- 设定为视口高度的 80%  -->
    <div class="modal-dialog modal-dialog-centered" style="max-width: 30%;"> 
      <div class="modal-content">
        <!-- Modal body -->
        <div class="modal-body" style="display: flex;justify-content: center;align-items: center;height: 9rem;">
          <button type="button" class="btn btn-danger" @click="LogOut" style="font-size: 1.375rem; margin-bottom: 0;">退出登录</button>
        </div>
        <!-- Modal footer -->
        <div class="modal-footer">
          <button type="button" class="btn btn-success" data-bs-dismiss="modal" style="margin-bottom: 0;">关闭</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { useToast } from 'vue-toastification';
import axios from 'axios';

export default {
  data() {
    return {
      // server_url: "http://127.0.0.1:5003",
      server_url: "http://cxy.ssdlab.cn/",
      LoggedIn: localStorage.getItem('LoggedIn')
    };
  },
  methods: {
    LogOut() {
      const toast = useToast();
      axios.post(this.server_url + "/api/passport/logout")
        .then((response) => {
          if (response.data.success === true) {
            toast.success(response.data.msg, {
              position: "top-right",
              timeout: 3000,
            });
            localStorage.setItem('LoggedIn', '')
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
    }
  }
}
</script>

