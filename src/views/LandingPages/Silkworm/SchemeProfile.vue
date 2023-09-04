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
              <div class="d-flex justify-content-center align-items-center mb-2">
                <h3 class="mb-2">主要建设内容及规模</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;如图1所示，项目以建设桑蚕疾病监测与防治智慧服务系统为目标，以达到助力桑蚕养殖大规模工厂化发展的目标。首先通过人工收集标定样本和基于对抗生成网络（Generative Adversarial Nets，GAN）的自动样本生成方法构建大量桑蚕疾病图像训练样本。然后采用深度卷积神经网络CNN模型和基于数据驱动的特征学习方法，<b>结合桑蚕群体/个体差异、自身形态、行为、体色、排泄物等特性和病理性验证信息</b>,优化设计深度神经网络底层过滤器、特征提取器、高层池化操作（Pooling），采用最新的YOLOv5（You Only Look Once）模型实现图像中桑蚕疾病的检测，改进模型输入尺度，使其能够尽可能输入更多的目标特征、设计并改进特征提取网络中Block结构，旨在增加主干网络特征提取能力，减少模型参数、通过融合高级语义信息和底层特征，改进该算法提高在蚕病识别上的准确率以及速率。在算法设计和开发阶段，尽可能地利用更复杂的模型和大量的训练数据提升桑蚕疾病检测和识别精度，使其能满足实际需求。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在检测和识别准确率满足应用需求的基础上，进一步研究深度神经网络压缩技术，如MobileNets深度模型，减少深度神经网络对内存和计算资源的依赖，通过工程优化开发轻便的深度网络模型，实现桑蚕疾病的识别系统在手机端的离线应用。同时，进一步开展基于Web服务的服务器构建研究，通过Web服务向工厂化养蚕生产线提供蚕病在线识别和预警服务。
              </p>
              <div class="p-0 my-3" style="display: flex; align-items:center; justify-content:center">
                <div class="image-container">
                  <img :src="schemeContent" alt="Preview" style="margin: 0 !important;" class="img-fluid border-radius-lg mb-3 uploaded-image"/>
                </div>
              </div>
              <div class="border-radius-lg" style="text-align: center;">
                  <h6 class="mb-3"><p>图1. 桑蚕疾病监测与防治智慧服务系统项目内容</p></h6>
              </div>
            </div>
            <div class="col-lg-7 col-md-7 z-index-2 position-relative px-md-2 px-sm-5 mx-auto">
              <div class="d-flex justify-content-center align-items-center mb-2 mt-4">
                <h3 class="mb-2">相关建设地址</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;系统建设包括两个关键部分：一是收集整理桑蚕疾病的病征和防治措施等专家知识，二是利用人工智能技术动态识别桑蚕疾病并实时预警的软硬件平台。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;桑蚕疾病的病征和防治措施的专家知识的收集整理工作和桑蚕疾病识别与防治服务的实验室中环境测试计划在西南大学家蚕基因组生物国家重点实验室进行；基于人工智能的桑蚕疾病识别与防治系统的软硬件平台搭建工作拟在西南大学计算机与信息科学学院进行。最后，计划将搭建的系统在重庆市蚕业科学技术研究院等地的自动化养蚕生产线上试点使用。
              </p>
            </div>
            <div class="col-lg-7 col-md-7 z-index-2 position-relative px-md-2 px-sm-5 mx-auto">
              <div class="d-flex justify-content-center align-items-center mb-2 mt-4">
                <h3 class="mb-2">研究方案及主要技术指标</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;如图2所示，项目以设计开发桑蚕疾病自动检测并提供防治措施相关建议为目标，针对系统中样本采集、目标检测、分类识别以及手机应用集成等关键问题开展研究，基于深度网络模型研究图像生成、特征编码与特征学习、模式分类，旨在研发高效率、高精度的桑蚕疾病病征图像识别系统。研究Web服务和用户终端的App或者小程序开发，旨在将系统部署到工厂化养蚕生产线和手机中进行应用推广。
                <br>
              </p>
              <div class="p-0 my-3" style="display: flex; align-items:center; justify-content:center">
                <div class="image-container">
                  <img src="/src/assets/img/propose-scheme.png" style="margin: 0 !important;" class="img-fluid border-radius-lg mb-3 uploaded-image"/>
                </div>
              </div>
              <div class="border-radius-lg" style="text-align: center;">
                  <h6 class="mb-3"><p>图2. 桑蚕疾病监测与防治智慧服务系统项目建议方案</p></h6>
              </div>
              <p>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;为了确保项目顺利实施降低项目风险，首先将整个系统分解为四个关键功能模块，通过子任务分解的方法降低系统复杂度，降低项目风险。然后，针对项目实施过程中关键模块功能可能遇到的技术风险，具体<b>研究方案</b>如下：
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（1）桑蚕疾病的图像样本采集模块。充足的训练数据是基于深度卷积神经网络训练的必要条件。一方面，计划从实际生产环境中和实验室环境中收集正常和带病桑蚕基础样本数据；另一方面，计划引入对抗生成网络（GAN）图片生成技术在人工标注的样本上学习，生成更多高质量的训练样本，从而解决样本标注成本高、样本不足的问题。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（2）桑蚕目标检测算法模块。从蚕盘视频监控或者照片作为识别桑蚕疾病的前置步骤，其效率严重影响后期疾病识别的准确性。计划采用基于改进的YOLOv5方法有效减少识别耗时，提高桑蚕个体的扫描检测的识别准确率。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（3）桑蚕疾病分类识别算法模块。基于深度卷积神经网络的图像分类模型由于受到样本质量的影响，在特征学习的过程中，可能呈现出模型难收敛、模型泛化性不高等不足，为了解决该问题，拟采用改进的残差网络ResNet和InceptionNet相融合的模型，根据桑蚕病征特点，优化深度网络结构，减少模型自由参数个数，降低网络的训练难度。同时引入数据增强技术，通过尺度变化增强、旋转增强、颜色空间增强增加样本数量，提升训练过程的稳定性。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（4）系统集成移动终端的APP或者小程序开发模块。基于深度神经网络的桑蚕疾病图像自动识别系统对内存和计算力有较高的要求，手机或监控系统等硬件资源可能不能满足其要求。本项目拟采用两种技术规避此风险。引入深度神经网络压缩技术，精简神经网络结构，降低手机应用程序对计算资源的需求。同时也采用基于Web服务的在线服务的方式提供识别服务，用户将视频数据或者所拍照片上传到服务器即可，识别任务由服务器后台执行。在线提供识别服务的模式完全不依赖用户端的硬件资源。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;通过本项目的实施，构建桑蚕疾病监测与防治智慧服务系统，加快工厂化养蚕生产线技术的推广，进一步促进我市甚至我国蚕桑产业的大规模智能化发展。本项目拟达到的<b>主要技术指标</b>如下：
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（1）收集整理包括血液性脓病和微粒子病在内的2-3种常见的病毒传染性桑蚕疾病样本数据库，带病样本数量达到2000个以上；提出基于改进的YOLOv5的桑蚕疾病检测和分类算法，在图片清晰的条件下，检测精度达到90%以上。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（2）搭建桑蚕疾病监测与防治智慧服务软硬件集成平台1个，支持1-2种常见桑蚕疾病的自动监测和识别，并提供相应防治措施的专家知识；
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（3）运行维护桑蚕疾病监测与防治智慧服务平台1-2年，向社会和个人提供免费的蚕疾病监测与防治服务；
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;（4）受理发明专利 1 项。
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
