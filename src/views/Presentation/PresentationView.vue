<script setup>
import { onMounted, onUnmounted } from "vue";

//example components
import NavbarDefault from "../..//examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../examples/footers/FooterDefault.vue";
import Header from "../../examples/Header.vue";
import FilledInfoCard from "../../examples/cards/infoCards/FilledInfoCard.vue";


// sections
import PresentationCounter from "./Sections/PresentationCounter.vue";
import BuiltByDevelopers from "./Components/BuiltByDevelopers.vue";

//images
import vueMkHeader from "@/assets/img/silkworm.jpg";
import previewImg from "@/assets/img/preview.jpg";
import logoBootstrap from "@/assets/img/logos/bootstrap5.jpg";
import logoYolov5 from "@/assets/img/logos/yolov5.png";
import logoTailwind from "@/assets/img/logos/icon-tailwind.jpg";
import logoVue from "@/assets/img/logos/vue.jpg";
import logoAngular from "@/assets/img/logos/angular.jpg";
import logoReact from "@/assets/img/logos/react.jpg";
import logoSketch from "@/assets/img/logos/sketch.jpg";

//Vue Material Kit 2 components
import MaterialInput from "@/components/MaterialInput.vue";
import MaterialTextArea from "@/components/MaterialTextArea.vue";
import MaterialButton from "@/components/MaterialButton.vue";

//hooks
const body = document.getElementsByTagName("body")[0];
onMounted(() => {
  body.classList.add("presentation-page");
  body.classList.add("bg-gray-200");
});
onUnmounted(() => {
  body.classList.remove("presentation-page");
  body.classList.remove("bg-gray-200");
});
</script>

<template>
  <div class="container z-index-sticky top-0">
    <div class="row">
      <div class="col-12">
        <NavbarDefault :sticky="true" />
      </div>
    </div>
  </div>
  <Header>
    <div
      class="page-header min-vh-75"
      :style="`background-image: url(${vueMkHeader})`"
      loading="lazy"
    >
      <div class="container">
        <div class="row">
          <div class="col-lg-7 text-center mx-auto position-relative">
            <h1
              class="text-white pt-3 mt-n5 me-2"
              :style="{ display: 'inline-block ' }"
            >
              桑蚕疾病监测
            </h1>
            <p class="lead text-white px-5 mt-3" :style="{ fontWeight: '500' }">
              基于人工智能的工厂化养蚕生产线蚕病检测与防控服务系统
            </p>
          </div>
        </div>
      </div>
    </div>
  </Header>

  <div class="card card-body blur shadow-blur mx-3 mx-md-4 mt-n6">
    <PresentationCounter />

  <section>
      <div class="container">
        <div class="row" style="justify-content: center;">
          <div class="col-xl-5 col-lg-6 col-md-7">
              <div class="card d-flex blur justify-content-center shadow-lg my-sm-0 my-sm-6 mt-8 mb-5">
                <div class="card-header p-0 position-relative mt-n4 mx-3 z-index-2 bg-transparent" style="margin-bottom: -0.8rem;">
                  <div class="bg-gradient-success shadow-success border-radius-lg p-3" style="text-align: center;">
                    <h3 class="text-white text-success mb-0">原始图像</h3>
                  </div>
                </div>
                <div class="card-body">
                  <form id="contact-form" method="post" autocomplete="off">
                    <div class="card-body p-0 my-3">
                      <div class="p-0 my-3">
                        <img :src="previewImage" alt="Preview" style="max-width: 100%;" class="img-fluid border-radius-lg mb-3"  v-if="previewImage" />
                        <input type="file" @change="handleFileChange" />
                      </div>
                      <div style="display: flex; align-items: center;">
                        <label style="height: 26px; margin: 0; width: 132px;font-size:1rem;">请选择蚕龄：</label>
                        <select class="form-select" style="background-position:95% center; padding-left: 10px; font-size: 1rem;" id="selectInput">
                          <option style="font-size: 2rem;" value=0 selected>三龄</option>
                          <option value=1>四龄</option>
                          <option value=2>五龄</option>
                        </select>
                      </div>
                      <div>
                        <MaterialInput style="margin-top: 15px;"
                          class="input-group-static mb-4"
                          type="text"
                          label="地址"
                        />
                      </div>
                      <div class="form-group mb-0 mt-md-0 mt-4">
                        <MaterialTextArea
                          id="message"
                          class="input-group-static mb-4"
                          :rows="2"
                          placeholder="Describe your problem in at least 250 characters"
                          >补充信息</MaterialTextArea
                        >
                      </div>
                      <div class="row">
                        <div class="col-md-12 text-center">
                          <MaterialButton style="font-size: 1.375rem; width: 12rem !important; margin-bottom: 0px;" variant="gradient" color="info" class="w-auto me-2">AI 检测</MaterialButton>
                        </div>
                      </div>
                    </div>
                  </form>
                </div>
              </div>
            </div>
            <div class="col-xl-5 col-lg-6 col-md-7">
              <div class="card d-flex blur justify-content-center shadow-lg my-sm-0 my-sm-6 mt-8 mb-5">
                <div class="card-header p-0 position-relative mt-n4 mx-3 z-index-2 bg-transparent" style="margin-bottom: -0.8rem;">
                  <div class="bg-gradient-success shadow-success border-radius-lg p-3" style="text-align: center;">
                    <h3 class="text-white text-success mb-0">检测结果</h3>
                  </div>
                </div>
                <div class="card-body">
                  <form id="contact-form" method="post" autocomplete="off">
                    <div class="card-body p-0 my-3">
                      <div class="card-body p-0 my-3" style="text-align: center;">
                        <img src="https://cxy.ssdlab.cn/tmp/comp/IMG_20220428_210700.jpg" style="max-width: 100%;" class="img-fluid border-radius-lg" />
                      </div>
                      <!-- add table -->
                      <div class="row">
                          <div class="col-md-12 text-center">
                            <div>
                              <table class="table">
                                <thead>
                                  <tr>
                                    <th>类别</th>
                                    <th>措施</th>
                                  </tr>
                                </thead>
                                <tbody>
                                  <tr v-for="(user) in users" :key="user">
                                    <td style="vertical-align: middle;">{{ user.class }}</td>
                                    <!-- white-space: pre-line; 样式可以让 <td> 元素内的内容保留换行 -->
                                    <td style="white-space: pre-line; text-align: left; padding-left: 25px;">{{ user.measure }}</td>
                                  </tr>
                                </tbody>
                              </table>
                            </div>
                          </div>
                      </div>
                    </div>
                  </form>
                </div>
              </div>
            </div>
        </div>
      </div>
    </section>

    <BuiltByDevelopers />

    <div class="container">
      <div class="row">
        <div class="col-lg-4">
          <FilledInfoCard
            class="p-4"
            :color="{ text: 'white', background: 'bg-gradient-success' }"
            :icon="{ component: 'flag', color: 'white' }"
            title="Getting Started"
            description="Check the possible ways of working with our product and the necessary files for building your own project."
            :action="{
              route:
                'https://www.creative-tim.com/learning-lab/vue/overview/material-kit/',
              label: { text: 'Let\'s start', color: 'white' }
            }"
          />
        </div>
        <div class="col-lg-4">
          <FilledInfoCard
            class="px-lg-1 mt-lg-0 mt-4 p-4"
            height="h-100"
            :icon="{ component: 'precision_manufacturing', color: 'success' }"
            title="Plugins"
            description="Get inspiration and have an overview about the plugins that we
                used to create the Material Kit."
            :action="{
              route:
                'https://www.creative-tim.com/learning-lab/vue/input/material-kit/',
              label: { text: 'Read more' }
            }"
          />
        </div>
        <div class="col-lg-4">
          <FilledInfoCard
            class="px-lg-1 mt-lg-0 mt-4 p-4"
            :icon="{ component: 'receipt_long', color: 'success' }"
            title="Utility Classes"
            description="Material Kit is giving you a lot of pre-made elements. For those
                who want flexibility, we included many utility classes."
            :action="{
              route:
                'https://www.creative-tim.com/learning-lab/vue/utilities/material-kit/',
              label: { text: 'Read more' }
            }"
          />
        </div>
      </div>
    </div>

    <div class="container">
      <div class="row">
        <div class="d-flex flex-column w-100 text-center p-5 mb-8">
          <h3>Available on these technologies</h3>
          <div class="d-flex justify-content-center mt-3 flex-wrap" style="align-items: center;">
            <a
              href="https://github.com/ultralytics/yolov5"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="YOLOv5 🚀 is the world's most loved vision AI"
            >
              <img
                :src="logoYolov5"
                alt="title"
                loading="lazy"
                :style="{ height: '50px' }"
                style="margin-right: 30px;"
              />
            </a>
            <a
              href="https://www.creative-tim.com/product/material-kit"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Bootstrap 5 - Most popular front-end component library"
            >
              <img
                :src="logoBootstrap"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
            <a
              class="opacity-5 ms-3"
              href="#"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Coming Soon"
            >
              <img
                :src="logoTailwind"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
            <a
              href="https://www.creative-tim.com/product/vue-material-kit-pro"
              class="mx-3"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Vue.js - Is a Progressive JavaScript Framework"
            >
              <img
                :src="logoVue"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
            <a
              class="opacity-5"
              href="#"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Coming Soon"
            >
              <img
                :src="logoAngular"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
            <a
              href="https://www.creative-tim.com/product/material-kit-react-pro"
              class="mx-3"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="React – A JavaScript library for building user interfaces"
            >
              <img
                :src="logoReact"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
            <a
              class="opacity-5"
              href="#"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Coming Soon"
            >
              <img
                :src="logoSketch"
                alt="title"
                loading="lazy"
                :style="{ height: '90px' }"
              />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
  <DefaultFooter />
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      users: [
        { class: "100%疑似为血液性脓病", measure: "1.全部淘汰，进行无害化处理。\n 2.对蚕室蚕具和养蚕环境进行彻底消毒。\n 3.查明病原来源，避免再次感染。\n4.重新饲养下一批蚕。\n" },
      ],
      selectedFile: null,
      previewImage: previewImg,
      uploadedImageUrl: null,
      showbutton: true,
      selectedAge: 0
    };
  },
  methods: {
    handleFileChange(event) {
      this.selectedFile = event.target.files[0];
      this.previewImage = URL.createObjectURL(this.selectedFile);
    },
    triggerFileInput() {
      this.$refs.fileInput.click();
    },
    uploadImage() {
      if (!this.selectedFile) {
        return;
      }
      const formData = new FormData();
      formData.append('image', this.selectedFile);

      axios
        .post('http://cxy.ssdlab.cn/', formData, {
          headers: {
            'Content-Type': 'multipart/form-data',
          },
        })
        .then(response => {
          this.uploadedImageUrl = response.data.imageUrl;
        })
        .catch(error => {
          console.error('Error uploading image:', error);
        });
    },
  },
};
</script>