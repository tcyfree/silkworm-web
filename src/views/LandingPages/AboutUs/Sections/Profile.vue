<script setup>
import { onMounted } from "vue";

//Vue Material Kit 2 components
import MaterialAvatar from "@/components/MaterialAvatar.vue";
import MaterialButton from "@/components/MaterialButton.vue";

// image
import schemeContent from "@/assets/img/scheme-content.png";

// material-input
import setMaterialInput from "@/assets/js/material-input";
onMounted(() => {
  setMaterialInput();
});
</script>
<template>
  <section class="py-sm-7 py-5 position-relative">
    <div class="container">
      <div class="row">
        <div class="col-12 mx-auto">
          <div class="row">
            <div class="col-lg-7 col-md-7 z-index-2 position-relative px-md-2 px-sm-5 mx-auto">
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;成立项目实施小组，主要负责项目实施方案的制定、组织实施、指导、督促、检查等工作，对具体承担项目实施的项目工作人员实行年度目标生产管理制，明确责任，狠抓落实。 同时，项目定期开展总结研讨，按照要求向上级管理部门和单位管理部门报送进展情况，接受监督检查，确保项目建设内容的完全实现。
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
