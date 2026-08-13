<template>
  <section>
    <Title title="工作经历" icon="icon-shishizhongxin" />
    <div v-for="(companyItem, companyIndex) in companyList" class="pb-1">
      <p class="flex justify-between">
        <strong class="text-base">{{ companyItem.companyName }}</strong>
        <strong>{{ companyItem.cycle }}</strong>
      </p>
      <div class="px-2">
        <p>
          <span class="font-medium">部门：</span>
          <span>{{ companyItem.branch }}</span>
        </p>
        <p>
          <span class="font-medium">职称：</span>
          <span>{{ companyItem.title }}</span>
        </p>
        <ul class="mx-3">
          <li v-for="routineWorkItem in companyItem.routineWork">
            {{ routineWorkItem }}
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
import { defineComponent, getCurrentInstance, reactive } from 'vue'
export default defineComponent({
  name: 'WorkExperience',
})
</script>

<script setup>
const proxy = getCurrentInstance()?.proxy

const companyList = reactive([
  {
    companyName: 'TCL格创东智内蒙古分公司（内部迁转）',
    cycle: '2025年9月1日-至今',
    branch: '系统服务部',
    title: '研发工程师',
    routineWork: [
      '负责企业级业务系统前后端开发，参与需求分析、技术方案设计、接口定义、功能实现、联调测试与上线交付；',
      '负责前端技术迭代与新技术落地，推进 Vue、React、TypeScript 等技术栈及工程化方案在业务项目中的应用；',
      '参与 FDC、工时管理等系统建设，负责实时数据、权限管理、项目流程、统计分析及智能化功能等模块开发；',
      '制定并推动前后端开发规范、接口规范、数据交互规范和代码质量规范，提升团队协作效率与系统可维护性；',
      '参与通用组件、项目脚手架及公共能力建设，推动模块复用和技术方案标准化；',
      '负责系统部署、环境配置和问题排查，协同业务、测试及运维团队保障项目稳定交付；',
    ],
  },
  {
    companyName: 'TCL-中环材料',
    cycle: '2023年8月-2025年8月',
    branch: '流程与IT部',
    title: '研发工程师',
    routineWork: [
      '主导前端规范制定与组件标准化建设，推动通用模块在多个项目中复用落地；',
      '参与多个复杂 B 端系统开发，业务涵盖流程审批、权限控制、数据可视化等场景；',
      '主导前后端数据交互方案设计，制定统一的接口通信、数据结构及异常处理机制，提高系统健壮性与开发效率；',
      '负责系统部署上线及环境运维，构建自动化部署流程，保障服务稳定运行；',
      '深入参与 H5 与 PDA 项目开发，针对设备性能差异进行适配优化与交互增强；',
      '基于 SoybeanAdmin 进行二次开发，制定 Vue3 + TypeScript 项目脚手架，提升项目初始化效率并统一团队技术栈；',
      '持续调研新技术，推动前端架构优化与新技术在业务项目中的落地应用；',
    ],
  },
  {
    companyName: '信永中和',
    cycle: '2018年7月-2023年8月',
    branch: '大数据技术部',
    title: '项目经理',
    routineWork: [
      '牵头制定前端架构与开发规范，推动组件复用与代码风格统一；',
      '负责项目从需求对接、技术方案制定到开发排期与进度管理的全流程执行；',
      '主导系统架构设计与技术选型，推动工程化方案如模块拆分、自动化构建等落地；',
      '开发脚手架工具链，构建 VSCode 插件与模板体系，规范开发流程、提升协作效率；',
      '开展 code-review 与技术分享，保障项目质量并提升团队整体技术水平；',
      '协助新人融入团队，推动技术传承与流程规范落地；',
    ],
  },
  // {
  //   companyName: '信永中和',
  //   cycle: '2018年7月-2019年7月',
  //   branch: '大数据技术部',
  //   title: '前端开发实习生',
  //   routineWork: [
  //     '项目日常开发，组件封装；',
  //     '大数据官网维护；',
  //   ],
  // },
])
</script>
