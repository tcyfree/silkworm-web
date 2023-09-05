<script setup>
import logoDark from "@/assets/img/icon.png";
defineProps({
  brand: {
    type: Object,
    name: String,
    logo: String,
    route: "",
    default: () => ({
      name: "桑蚕疾病监测可视化展示平台",
      logo: logoDark,
      route: "/"
    })
  },
  socials: {
    type: Array,
    icon: String,
    link: String,
    default: () => [
      {
        icon: '<i class="fab fa-facebook text-lg opacity-8"></i>',
        // link: "https://www.facebook.com/CreativeTim/"
      },
      {
        icon: '<i class="fab fa-twitter text-lg opacity-8"></i>',
        // link: "https://twitter.com/creativetim"
      },
      {
        icon: '<i class="fab fa-dribbble text-lg opacity-8"></i>',
        // link: "https://dribbble.com/creativetim"
      },
      {
        icon: '<i class="fab fa-github text-lg opacity-8"></i>',
        // link: "https://github.com/creativetimofficial"
      },
      {
        icon: '<i class="fab fa-youtube text-lg opacity-8"></i>',
        // link: "https://www.youtube.com/channel/UCVyTG4sCw-rOvB9oHkzZD1w"
      }
    ]
  },
  menus: {
    type: Array,
    name: String,
    items: {
      type: Array,
      name: String,
      href: String
    },
    default: () => [
      {
        name: "公司",
        items: [
          {
            name: "关于我们",
            href: "/pages/landing-pages/about-us"
          },
          { name: "博客", 
          // href: "https://www.creative-tim.com/blog" 
        }
        ]
      },
      {
        name: "资源",
        items: [
          { 
            name: "数据集", 
            // href: "https://iradesign.io/" 
          },
          {
            name: "相关项目",
            // href: "https://www.creative-tim.com/affiliates/new"
          }
        ]
      },
      {
        name: "帮助与支持",
        items: [
          {
            name: "联系我们",
            href: "/pages/landing-pages/contact-us"
          },
          {
            name: "帮助中心",
            href: "/pages/landing-pages/contact-us"
          },
          {
            name: "定制开发",
            href: "/pages/landing-pages/contact-us"
          },
        ]
      },
      {
        name: "法律",
        items: [
          {
            name: "条款和条件",
            // href: "https://www.creative-tim.com/terms"
          },
          {
            name: "隐私政策",
            // href: "https://www.creative-tim.com/privacy"
          },
          {
            name: "许可证",
            // href: "https://www.creative-tim.com/license"
          }
        ]
      }
    ]
  }
});
</script>
<template>
  <footer class="footer pt-5 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-md-3 mb-4 ms-auto">
          <div>
            <a :href="brand.route">
              <img :src="brand.logo" class="mb-3 footer-logo" alt="main_logo" />
            </a>
            <h6 class="font-weight-bolder mb-4">{{ brand.name }}</h6>
          </div>
          <div>
            <ul class="d-flex flex-row ms-n3 nav">
              <li
                class="nav-item"
                v-for="{ icon, link } of socials"
                :key="link"
              >
                <a
                  class="nav-link pe-1"
                  :href="link"
                  target="_blank"
                  v-html="icon"
                >
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div
          class="col-md-2 col-sm-6 col-6 mb-4"
          v-for="{ name, items } of menus"
          :key="name"
        >
          <h6 class="text-sm">{{ name }}</h6>
          <ul class="flex-column ms-n3 nav">
            <li class="nav-item" v-for="item of items" :key="item.name">
              <a class="nav-link" :href="item.href" target="_blank">
                {{ item.name }}
              </a>
            </li>
          </ul>
        </div>

        <div class="col-12">
          <div class="text-center">
            <p class="text-dark my-4 text-sm font-weight-normal">
              All rights reserved. Copyright ©
              {{ new Date().getFullYear() }}
              ssdlab.cn
            </p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
