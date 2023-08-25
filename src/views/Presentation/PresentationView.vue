<script setup>
import { onMounted, onUnmounted } from "vue";

//example components
import NavbarDefault from "../..//examples/navbars/NavbarDefault.vue";
import DefaultFooter from "../../examples/footers/FooterDefault.vue";
import Header from "../../examples/Header.vue";
import FilledInfoCardNoLink from "../../examples/cards/infoCards/FilledInfoCardNoLink.vue";


// sections
import PresentationCounter from "./Sections/PresentationCounter.vue";
import BuiltByDevelopers from "./Components/BuiltByDevelopers.vue";

//images
import vueMkHeader from "@/assets/img/silkworm.jpg";
import previewImg from "@/assets/img/preview.jpg";
import previewCompressImg from "@/assets/img/preview-compress.png";
import logoBootstrap from "@/assets/img/logos/bootstrap5.jpg";
import logoYolov5 from "@/assets/img/logos/yolov5.png";
import logoFlask from "@/assets/img/logos/flaks-logo.png";
import logoVue from "@/assets/img/logos/vue.jpg";
import logoDocker from "@/assets/img/logos/docker.png";
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
                  <div class="card-body p-0 my-3">
                    <div class="p-0 my-3" style="display: flex;">
                      <div class="image-container">
                        <img :src="previewImage" alt="Preview" style="margin: 0 !important;" class="img-fluid border-radius-lg mb-3 uploaded-image"  data-bs-toggle="modal" data-bs-target="#previewModal"/>
                      </div>
                    </div>
                    <div class="p-0 my-3">
                      <input type="file" @change="selectImage" style="margin-top: 16px;" ref="fileInput"/>
                    </div>
                    <div style="display: flex; align-items: center;">
                      <label style="height: 26px; margin: 0; width: 132px;font-size:1rem;">请选择蚕龄：</label>
                      <select v-model="selectedAge" class="form-select" style="background-position:95% center; padding-left: 10px; font-size: 1rem;">
                        <option style="font-size: 2rem;" value=0 selected>三龄</option>
                        <option value=1>四龄</option>
                        <option value=2>五龄</option>
                      </select>
                    </div>
                    <div>
                      <MaterialInput style="margin-top: 15px;" class="input-group-static mb-4" type="text" label="地址"/>
                    </div>
                    <div class="form-group mb-0 mt-md-0 mt-4">
                      <MaterialTextArea id="message" class="input-group-static mb-4" :rows="1" >补充信息</MaterialTextArea>
                    </div>
                    <div class="row">
                      <div class="col-md-12 text-center">
                        <MaterialButton style="font-size: 1.375rem; width: 12rem !important; margin-bottom: 0px;" variant="gradient" color="info" class="w-auto me-2" v-on:click="uploadImage">AI 检测  </MaterialButton>
                      </div>
                    </div>
                    <!-- loading overlay-->
                    <div v-if="loading" class="loading-overlay">
                      <div class="spinner"></div>
                    </div>
                  </div>
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
                      <div class="card-body p-0 my-3" style="display: flex;">
                        <div class="image-container">
                          <img :src="detectImage" style="margin: 0 !important;" class="img-fluid border-radius-lg mb-3 uploaded-image" data-bs-toggle="modal" data-bs-target="#detectModal"/>
                        </div>
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
                                  <tr v-for="(row, index) in detectInfo" :key="index">
                                    <td style="vertical-align: middle;">{{ row[2] }}{{ row[0] }}</td>
                                    <!-- white-space: pre-line; 样式可以让 <td> 元素内的内容保留换行 -->
                                    <td style="white-space: pre-line; text-align: left; padding-left: 25px;">{{ row[1] }}</td>
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

    <div class="container" style="margin-top: 20px;">
      <div class="row">
        <div class="col-lg-4">
          <FilledInfoCardNoLink
            class="p-4"
            :color="{ text: 'white', background: 'bg-gradient-success' }"
            :icon="{ component: 'add_a_photo', color: 'white' }"
            title="桑蚕疾病的图像样本采集模块"
            description="数据采集来自实际生产和实验室环境的正常和患病桑蚕样本。并且我们也运用对抗生成网络（GAN）图像生成技术，在人工标记的样本上进行学习，生成更多高质量的训练样本。这有助于解决高成本的样本标注和样本不足的问题，更准确地捕捉不同疾病情况，从而在实际应用中取得更好的效果。"
            :action="{
              route:'',
              label: { text: '更多', color: 'white' }
            }"
          />
        </div>
        <div class="col-lg-4">
          <FilledInfoCardNoLink
            class="px-lg-1 mt-lg-0 mt-4 p-4"
            :color="{ text: 'white', background: 'bg-gradient-success' }"
            :icon="{ component: 'gps_fixed', color: 'white' }"
            title="桑蚕目标检测算法模块"
            description="从蚕盘视频监控或者照片作为识别桑蚕疾病的前置步骤，其效率严重影响后期疾病识别的准确性。通过采用基于改进的YOLOv5方法，可以有效地降低识别所需的时间成本，从而显著提升对桑蚕个体进行扫描检测时的识别准确率。这种方法不仅可以更快速地发现潜在的疾病迹象，还能够在更广泛的环境中实现更准确的检测结果。"
            :action="{
              route:'',
              label: { text: '更多', color: 'white' }
            }"
          />
        </div>
        <div class="col-lg-4">
          <FilledInfoCardNoLink
            class="px-lg-1 mt-lg-0 mt-4 p-4"
            :color="{ text: 'white', background: 'bg-gradient-success' }"
            :icon="{ component: 'grid_view', color: 'white' }"
            title="桑蚕疾病分类识别算法模块"
            description="基于深度卷积神经网络的图像分类模型由于受到样本质量的影响，在特征学习的过程中，可能呈现出模型难收敛、模型泛化性不高等不足，为了解决该问题，拟采用改进的残差网络ResNet和InceptionNet相融合的模型，根据桑蚕病征特点，优化深度网络结构，减少模型自由参数个数，降低网络的训练难度。"
            :action="{
              route:
                'https://www.creative-tim.com/learning-lab/vue/utilities/material-kit/',
              label: { text: '更多', color: 'white' }
            }"
          />
        </div>
      </div>
    </div>

    <div class="container">
      <div class="row">
        <div class="d-flex flex-column w-100 text-center p-5 mb-8">
          <h3>技术支撑</h3>
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
              class="opacity-9 ms-3"
              href="https://flask.palletsprojects.com/en/2.3.x/"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Flask is a micro web framework written in Python."
            >
              <img
                :src="logoFlask"
                alt="title"
                loading="lazy"
                :style="{ height: '60px' }"
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
              class="opacity-9"
              href="https://docs.docker.com/get-started/overview/"
              data-bs-toggle="tooltip"
              data-bs-placement="bottom"
              title="Docker is an open platform for developing, shipping, and running applications."
            >
              <img
                :src="logoDocker"
                alt="title"
                loading="lazy"
                :style="{ height: '75px' }"
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
  <!-- The Modal -->
  <div class="modal" id="detectModal">
    <!-- 设定为视口高度的 80%  -->
    <div class="modal-dialog" style="max-width: 40%;"> 
      <div class="modal-content">
        <!-- Modal body -->
        <div class="modal-body">
          <img :src="detectImage" class="img-fluid border-radius-lg mb-3">
        </div>
        <!-- Modal footer -->
        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">Close</button>
        </div>
      </div>
    </div>
  </div>
  <div class="modal" id="previewModal">
    <!-- 设定为视口高度的 80%  -->
    <div class="modal-dialog" style="max-width: 40%;"> 
      <div class="modal-content">
        <!-- Modal body -->
        <div class="modal-body">
          <img :src="previewImage" class="img-fluid border-radius-lg mb-3">
        </div>
        <!-- Modal footer -->
        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import { useToast } from 'vue-toastification';
// import 'vue-toastification/dist/index.css';

export default {
  data() {
    return {
      // server_url: "http://172.27.112.1:5003/",
      server_url: "http://cxy.ssdlab.cn/",
      previewImage: previewImg,
      detectImage: previewCompressImg,
      selectedAge: 0,
      selectedImg: null,
      detectInfo: [["疑似为血液性脓病", "1.全部淘汰，进行无害化处理。\n 2.对蚕室蚕具和养蚕环境进行彻底消毒。\n 3.查明病原来源，避免再次感染。\n4.重新饲养下一批蚕。\n", "100%"]],
      loading: false
    };
  },
  methods: {
    // Select image
    selectImage(event) {
      this.selectedImg = event.target.files[0];
      if (typeof this.selectedImg !== 'object') {
        return
      }
      //get suffix
      const toast = useToast();
      var ext = this.selectedImg.name.substr(this.selectedImg.name.lastIndexOf(".")+1);
      if(!(['png', 'jpg', 'jpeg'].indexOf(ext.toLowerCase()) !== -1)) {
        // alert("只能上传jpg,jpeg,png格式的图片！");
        toast.error("只能上传jpg,jpeg,png格式的图片！", {
          position: "top-right",
          timeout: 3000,
        })
        // Not display value
        this.$refs.fileInput.value = null
        // Empty select value
        this.selectedImg = null
        // location.reload()
        return;
      }
      this.previewImage = URL.createObjectURL(this.selectedImg);
    },
    // Upload image
    uploadImage() {
      let uploadImg = this.selectedImg;
      const toast = useToast();
      // if cancel submit, the process is not processed
      if (uploadImg === null) {
        toast.warning("请上传图片！", {
          position: "top-right",
          timeout: 3000,
        });
        return
      }
      this.loading = true;
      let param = new FormData(); //创建form对象
      param.append("file", uploadImg, uploadImg.name); //通过append向form对象添加数据
      let config = {
        headers: { "Content-Type": "multipart/form-data" },
      }; //添加请求头
      axios.post(this.server_url + "/upload?age=" + this.selectedAge, param, config)
        .then((response) => {
          this.loading = false;
          toast.success("检测成功！", {
            position: "top-right",
            timeout: 3000,
          });
          if (response.status != 200) {
            alert("请重新上传，图片格式错误或服务器内部错误！");
          }
          if (response.data.status != 1) {
            alert(response.data.msg);
          }
          console.log(response)
          let imgInfo = Object.keys(response.data.image_info);
          // clear initial data
          this.detectInfo = [] 
          for (var i = 0; i < imgInfo.length; i++) {
            response.data.image_info[imgInfo[i]][2] = imgInfo[i];
            this.detectInfo.push(response.data.image_info[imgInfo[i]]);
          }
          this.detectImage = response.data.draw_url
      });
    },
  },
};
</script>
<style>
.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.spinner {
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-left-color: #000;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

/* fixed image width and height */
.image-container {
  width: 550px; /* set container height */
  height: 250px; /* set container width */
  /* border: 1px solid #ccc; */
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.uploaded-image {
  max-height: 100%;
}
</style>