<script setup>
import DefaultCounterCard from "../../../examples/cards/counterCards/DefaultCounterCard.vue";
</script>

<template>
  <section class="pt-3 pb-4" id="count-stats">
    <div class="container">
      <div class="row">
        <div class="col-lg-9 z-index-2 border-radius-xl mx-auto py-3">
          <div class="row">
            <div class="col-md-4 position-relative">
              <DefaultCounterCard
                color="success"
                title="原始采集数据"
                description="该数据集共3523张图片。其中摊放合适的图片是3000张，摊放不足的图片是523张。 该数据集记录的是10个批次随时间6~7次变化的10个角度的桑蚕样品。"
                :count="3500"
                suffix="+"
                :duration="3000"
                divider="vertical"
              />
            </div>
            <div class="col-md-4 position-relative">
              <DefaultCounterCard
                color="success"
                title="蚕等级分类数据"
                description="通过中心裁剪, 减低分辨率等数据预处理方法以及对较少样品类进行数据增强, 得到共1885张图片的蚕分类数据集。"
                :count="1800"
                suffix="+"
                :duration="3000"
                divider="vertical"
              />
            </div>
            <div class="col-md-4">
              <DefaultCounterCard
                color="success"
                title="等级"
                description="采集样品共分为4个等级, 分别为一级、二级、三级以及四级。"
                :count="4"
                :duration="6000"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
