<script setup>
import { onMounted } from "vue";

//Vue Material Kit 2 components
import MaterialAvatar from "@/components/MaterialAvatar.vue";
import MaterialButton from "@/components/MaterialButton.vue";

// image
import profilePic from "@/assets/img/bruce-mars.jpg";
import overviewImg from "@/assets/img/overview.png";

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
                <h3 class="mb-2">项目意义</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我国桑蚕产业已经有了5500年的历史,一直是世界上茧丝出口大国。自从上世纪70年代，我国的蚕茧产量超过日本后，一直是世界上最大的蚕茧出口国。在改革开放后,国际政策的变化桑蚕产业持续发展现已成为某些地域重要的经济支柱，成为了落实脱贫攻坚和乡村振兴举措。近年来，蚕桑丝绸产业在技术进步、结构调整和品牌建设等方面取得了积极进展。根据蚕桑主产省（区、市）生产主管部门对春季蚕桑生产统计及年末对部分主产省的初步调查统计，2020年全国桑园面积1231万亩（含生态桑），发种量1662万张，桑蚕茧产量达到了68.6万吨，蚕茧和生丝产量占全球80%以上<sup>1</sup>。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;然而，蚕病对蚕桑生产影响很大，是导致蚕农养蚕减产减收的最主要的因素之一。发病的种类是以病毒病、微粒子病、真菌病为主，每年因蚕病造成的损失相当于蚕茧总产量的12%～25%<sup>2</sup>。蚕农大幅减收甚至颗粒无收的情况时有发生，严重挫伤蚕农养蚕的积极性，危及产业健康持续发展。因此，正确和及时地诊断蚕病是生产实际中采取针对性防治措施的前提，但传统的人工目测的方法诊断蚕病存在两个问题：（1）蚕农并不能保证根据经验做出的判断完全正确；（2）由于没有专业人士及时现场诊断，可能会使病情延误或加重。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2021年，国家六部委联合发布的《蚕桑丝绸高质量发展行动计划（2021-2025）》和重庆市蚕桑丝绸产业发展“十四五”规划等文件，已经强调了在基础较好的地区适时推广全龄饲料工厂化养蚕模式，推进传统养蚕模式创新变革。提升环境控制、生产管理、饲料生产及投放、<b>病害防治</b>等技术装备水平，进一步提高生产效率和产品品质。因此，随着规模生产模式探索以产业园区(企业)、家庭农场为主体的规模化蚕桑生产模式的发展，以企业化运作代替“一家一户”的手工作坊式生产，集成运用多项规模化生产技术，改变原有的生产规模小、劳动效率低下、对新技术需求不足的桑蚕产业生产现状，从而从根本上促进桑蚕产业向现代化转变。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;需要指出的是，自动化、工厂化和智能化养蚕生产线技术改变了传统养蚕模式，实现蚕桑工厂化饲育，进一步完善了蚕桑配套技术产业链，达到了节省人力并提升中养蚕效率的目标。然而，由于缺乏蚕农和技术专家的实时跟踪和疾病预警，现代化养蚕生产线容易造成病情报告延误和误判的问题，导致不能及时的对桑蚕疾病做出响应和干预，严重影响经济效益。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;另一方面，传统信息技术变革产生新一代计算机技术，其中包括人工智能、云计算、移动物联网和大数据等，都是具有代表性的新兴技术。其中，人工智能作为计算机科学的一个重要分支，通常可以将其简单概括成一种智能化的处理能力，能够和人一样感知、认知、决策、执行的人工程序或系统。随着以数字图像处理、传统机器学习和深度学习为代表的各种图像处理与识别算法的成熟，人工智能在农业方面的应用主要涉及检测、图像处理、模式识别等领域。大数据处理技术充分应用在农业养殖和市场销售领域中，最为核心的功能之一是具有专业知识和决策能力的专家系统，能够对农作物的生产链进行实时的监管控制，保证作物的产出量。
                <br>
              </p>
              <div class="p-0 my-3" style="display: flex; align-items:center; justify-content:center">
                <div class="image-container">
                  <img :src="overviewImg" alt="Preview" style="margin: 0 !important;" class="img-fluid border-radius-lg mb-3 uploaded-image"/>
                </div>
              </div>
              <div class="border-radius-lg" style="text-align: center;">
                  <h6 class="mb-3"><p>图1. 桑蚕疾病监测与防治智慧服务系统建设</p></h6>
                </div>
              <p>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;因此，为了进一步落实国家和重庆市在蚕桑丝绸产业发展指导思想，推进蚕桑丝绸产业高质量发展，满足人民美好生活需要、带动相关产业发展、助推乡村振兴及脱贫攻坚，在规模化的工厂化养蚕背景下，研究如何利用人工智能（机器学习算法）相关信息技术，分析利用桑蚕疾病诊断与防治专家知识的大数据，构建如图1所示的桑蚕疾病监测与防治智慧服务系统，促进蚕桑养殖产业的大规模发展就显得尤为重要。
              </p>
              <ol>
                <li><p>2021年蚕桑产业发展趋势与建议[M]，国家蚕桑产业技术体系, 2021.</p></li>
                <li><p>邓卫. 农村中蚕病发生的原因及防治探讨[J]. 蚕学通讯, 1997(2):3.</p></li>
              </ol>
            </div>
            <div class="col-lg-7 col-md-7 z-index-2 position-relative px-md-2 px-sm-5 mx-auto">
              <div class="d-flex justify-content-center align-items-center mb-2 mt-4">
                <h3 class="mb-2">科研条件</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;西南大学在蚕桑方面的研发能力处于全国领先、国际先进。拥有世界最大规模的蚕学研究队伍，固定研发人员60余名，研究生400余名，是一支以院士、长江学者、国家百千万工程及突出贡献专家为学术带头人的结构合理、老中青搭配、实力雄厚的专业技术团队。近10年，承担完成了包括973、863、948、111、国家重点研发计划、国家科技基础工作专项、公益性行业（农业）科研专项、现代农业产业技术体系建设、国家自然科学基金及国家茧丝绸发展专项、重庆市重大专项等一批高层次研究课题。因此，能够为构建基于人工智能技术的桑蚕疾病监测与防治智慧服务系统提供了专家知识方面的支持。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;另一方面，西南大学在农村农业信息服务领域也取得了一定的应用成果。承担了包括国家科技部支撑计划课题“农村物联网综合信息服务关键技术集成与示范“等课题。并且，项目申请人所在实验室目前具备较为完善的计算机视觉与深度学习运行与计算的支撑平台和较先进的图像处理仪器设备，包括共计 10 台 Inter Core 8 核 CPU、NVIDIA TITAN X 高性能显卡、10TB 硬盘、32GB内存的工作站，提供可并行计算的深度学习计算框架、实现多机多 GPU 的并行训练。因此，能够为构建基于人工智能技术的桑蚕疾病监测与防治智慧服务系统提供了技术手段方面的支持。
              </p>
            </div>
            <div class="col-lg-7 col-md-7 z-index-2 position-relative px-md-2 px-sm-5 mx-auto">
              <div class="d-flex justify-content-center align-items-center mb-2 mt-4">
                <h3 class="mb-2">技术支撑</h3>
              </div>
              <p class="text-lg mb-0">
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;项目组已经熟练掌握了利用农业知识图谱和专家问答系统等技术将农业（比如，柑橘种植和生猪养殖）专家数据转换成农业知识，建立集成的智慧服务系统解决在实际生产中出现的问题，有效地促进了相关农业生产效率。
                <br>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;而且，项目组已经利用大数据技术初步地将桑蚕病害等农业专家知识集成数据库，通过机器学习建立基于图片识别的卷积神经网络CNN(Convolution Neural Network),如Mask-RCNN或YOLO等深度学习模型，从而实现启发式推理的目标，也为后期解决工厂化养蚕中所遇到的桑蚕诊治病害的问题提供了相应的技术和人力资源支撑。
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
