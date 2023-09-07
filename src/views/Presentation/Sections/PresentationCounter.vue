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
                description="通过采用一系列数据预处理方法，如中心裁剪、分辨率降低等，以及对样本较少的类别进行数据增强，我们成功创建了一个包含1885张图像的蚕分类数据集。"
                :count="1800"
                suffix="+"
                :duration="3000"
                divider="vertical"
              />
            </div>
            <div class="col-md-4">
              <DefaultCounterCard
                color="success"
                title="监测龄级段"
                description="三龄、四龄和五龄幼虫是3个关键时期，因为桑蚕的健康状况对于丝绸产量和质量具有直接影响及早发现并采取措施来应对潜在的疾病问题对于养蚕业非常重要。"
                :count="3"
                :duration="6000"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
