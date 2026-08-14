<template>
  <section>
    <!-- class="sm:flex justify-between flex-row-reverse" -->
    <div >
      <!-- <img class="float-none lg:float-right
      w-24 h-24 
      sm:w-28 sm:h-28
      md:w-32 md:h-32
      lg:w-36 lg:h-36
      
      m-auto mb-10
      lg:m-6 lg:mb-0

      rounded-full " :src="avatar" alt="avatar" /> -->
      <div>
        <h3 class="sm:text-left ">赵雅国</h3>
        <ul>
          <li v-for="userInfoItem in userInfo" class="flex items-center mb-1">
            <IconFont :icon="userInfoItem.icon" class="text-lg "/>
            <span class="block ml-2">{{ userInfoItem.text }}</span>
          </li>
        </ul>
      </div>
    </div>

  </section>
</template>

<script setup>
import { reactive } from 'vue';

 
// import avatar from '/avatar.pic.jpg'
const userInfo = reactive([
  {
    icon: 'icon-shengri--',
    text: '1996 / 男'
  },
  {
    icon: 'icon--xuexiao',
    text: '本科统招 / 内蒙古科技大学 / 软件工程（2015-2019）'
  },
  {
    icon: 'icon-blog1',
    text: '技术博客：https://ggupzhh.github.io/blog'
  },
  {
    icon: 'icon-browser',
    text: '在线简历：https://ggupzhh.github.io/resume/'
  },
  {
    icon: 'icon-WEBqianduan',
    text: '期望职位：研发工程师'
  },
  {
    icon: 'icon-shouji3',
    text: '手机：15849493152'
  },
  {
    icon: 'icon-weixin1',
    text: '微信：GGupzHH'
  },
  {
    icon: 'icon-youxiang',
    text: '邮箱：ggupzhh@gmail.com'
  },
])
</script>
