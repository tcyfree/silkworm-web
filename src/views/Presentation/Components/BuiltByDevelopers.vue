<script setup>
//images
import overviewImg from "@/assets/img/overview.png";
</script>

<template>
  <div class="container mt-sm-1">
    <div
      class="page-header py-6 py-md-5 my-sm-3 mb-3 border-radius-xl"
      :style="`background-image: url(${overviewImg})`"
      loading="lazy"
    >
      <span class="mask bg-gradient-dark"></span>
      <div class="container">
        <div class="row">
          <div class="col-lg-6 ms-lg-5">
            <h1 class="text-white">桑蚕疾病监测与防治智慧服务系统建设</h1>
            <p class="lead text-white opacity-8">
              自动化、工厂化和智能化养蚕生产线技术改变了传统养蚕模式，实现蚕桑工厂化饲育，进一步完善了蚕桑配套技术产业链，达到了节省人力并提升中养蚕效率的目标。然而，由于缺乏蚕农和技术专家的实时跟踪和疾病预警，现代化养蚕生产线容易造成病情报告延误和误判的问题，导致不能及时的对桑蚕疾病做出响应和干预，严重影响经济效益。
            </p>
            <a
              href=""
              class="text-white icon-move-right"
            >
              阅读更多
              <i class="fas fa-arrow-right text-sm ms-1"></i>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
