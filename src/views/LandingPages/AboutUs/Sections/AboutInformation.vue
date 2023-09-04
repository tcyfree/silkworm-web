<script setup>
// example components
import DefaultInfoCard from "../../../../examples/cards/infoCards/DefaultInfoCard.vue";
import CenteredBlogCard from "../../../../examples/cards/blogCards/CenteredBlogCard.vue";
</script>
<template>
  <section class="py-7">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6">
          <div class="row justify-content-start">
            <DefaultInfoCard
              color="info"
              icon="people"
              title="专家团队"
              description="拥有桑蚕养殖经验和疾病防治知识的农业专家，负责提供农业实践方面的指导和建议。"
            />
            <DefaultInfoCard
              color="info"
              icon="apps"
              title="数据团队"
              description="负责数据收集、分析和建模，以开发疾病监测模型和预测工具。"
            />
          </div>
          <div class="row justify-content-start mt-4">
            <DefaultInfoCard
              color="info"
              icon="developer_mode"
              title="开发团队"
              description="负责系统的服务器端逻辑、数据库集成和移动应用程序开发人，使农民能够通过手机访问系统并报告疾病情况。"
            />
            <DefaultInfoCard
              color="info"
              icon="3p"
              title="合作伙伴和社区"
              description="与大学和研究机构合作，开展科学研究和数据验证，并与当地农民合作社建立合作关系，协助数据收集和传播疾病防治信息"
            />
          </div>
        </div>
        <div class="col-lg-4 ms-auto mt-lg-0 mt-6" style="display:flex; align-items:center; justify-content:center">
          <CenteredBlogCard
            image="/src/assets/img/team.png"
            description="成立项目实施小组，主要负责项目实施方案的制定、组织实施、指导、督促、检查等工作，对具体承担项目实施的项目工作人员实行年度目标生产管理制，明确责任，狠抓落实。 同时，项目定期开展总结研讨，按照要求向上级管理部门和单位管理部门报送进展情况，接受监督检查，确保项目建设内容的完全实现。"
          />
        </div>
      </div>
    </div>
  </section>
</template>
