<template>
  <section>
    <Title title="项目经历" icon="icon-Blog" />
    <div v-for="(projectItem, projectIndex) in projectList" class="px-2 pb-1">
      <p class="flex justify-between">
        <strong class="text-base">{{ projectItem.projectName }}</strong>
        <strong>{{ projectItem.cycle }}</strong>
      </p>
      <div>
        <strong>项目描述：</strong>
        <span>{{ projectItem.projectBackground }}</span>
      </div>
      <div>
        <strong>技术栈：</strong>
        <span>{{ projectItem.technologyStack.join('、') }}</span>
      </div>
      <ul class="mx-3">
        <li v-for="dutyItem in projectItem.duty">
          {{ dutyItem }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
import { defineComponent, getCurrentInstance, reactive } from 'vue'
export default defineComponent({
  name: 'SoftwareExperience',
})
</script>

<script setup>
const proxy = getCurrentInstance()?.proxy

const projectList = reactive([
  {
    projectName: '工时管理系统开发',
    cycle: '2026.04 - 至今',
    technologyStack: [
      'Vue3',
      'TypeScript',
      'Vite',
      'Pinia',
      'Naive UI',
      'NestJS',
      'TypeORM',
      'MySQL',
      'JWT',
      'LangGraph',
      'OpenAI',
      'SSE',
    ],
    projectBackground:
      '面向企业内部项目团队的项目流程与工时管理平台，建立组织、项目、需求、工时与统计分析的业务闭环。',
    duty: [
      '独立负责前后端开发，完成认证授权、用户角色、组织管理、项目管理、需求管理和工时管理等核心模块；',
      '基于 JWT、Refresh Token 轮换、HttpOnly Cookie、RBAC 及项目成员关系实现认证安全和项目级数据权限；',
      '实现项目生命周期、需求状态流转、需求验收和项目结项校验，维护项目、需求与工时之间的业务约束；',
      '通过事务和 FOR UPDATE 悲观锁实现每日工时上限校验，并自动汇总需求实际工时；',
      '基于 LangGraph、OpenAI 和 SSE 实现只读智能问数能力，支持自然语言查询业务数据并流式返回结果；',
    ],
  },
  {
    projectName: 'ITSM Agent 相关逻辑开发',
    cycle: '2026.04 - 2026.05',
    technologyStack: [
      'Node.js',
      'TypeScript',
      '中文分词',
      'TF-IDF',
      '向量数据库',
      'Embedding',
      'RAG',
      'Dify',
      '蓝鲸 GSE/Job/OpenAPI',
    ],
    projectBackground:
      '面向 ITSM 工单场景配置智能检索与 Agent 能力，结合历史工单知识库辅助故障分析和运维问题处理。',
    duty: [
      '参与 ITSM Agent 相关逻辑开发，完成历史工单清洗、中文分词、文本切分和知识库数据整理；',
      '参与 Embedding 模型及向量数据库配置，建立工单知识的向量化存储和相似内容召回流程；',
      '参与 RAG 检索增强生成流程配置，将历史工单、处理过程和解决方案作为上下文辅助 Agent 生成回答；',
      '基于 TF-IDF、余弦相似度和层次聚类分析历史工单，为问题分类、相似工单发现和知识库建设提供支持；',
      '对接 Dify 知识库及蓝鲸 GSE、Job、OpenAPI 等能力，推动知识检索与自动化运维任务联动；',
    ],
  },
  {
    projectName: 'FDC 系统开发',
    cycle: '2025.08 - 至今',
    technologyStack: [
      'React',
      'TypeScript',
      'Vite',
      'Ant Design',
      'MobX',
      'React Query',
      'ECharts',
      'AntV',
      'WebSocket',
      'SpringBoot',
      'Spring Cloud Alibaba',
      'Dubbo',
      'Nacos',
      'Kafka',
      'MySQL',
      'ClickHouse',
    ],
    projectBackground:
      '面向制造设备及工艺过程的 FDC 故障检测与分类平台，覆盖数据采集、实时监控、检测建模、告警分析和生产履历追溯。',
    duty: [
      '独立负责前后端整体开发，完成用户权限、设备采集、数据分析、检测建模、告警管理和系统配置等核心模块；',
      '基于 React、Ant Design、ECharts 和 AntV 实现实时曲线、历史趋势、告警统计、设备看板及模型配置页面；',
      '基于 SpringBoot、Dubbo 和 Nacos 构建用户、配置、数据、告警等服务，完成 RESTful API、RPC 服务和权限控制；',
      '基于 Kafka 处理 Trace、Event、Summary、Resume、告警及配置更新消息，结合 WebSocket 实现实时数据推送和断线重连；',
      '采用 MySQL 与 ClickHouse 双存储架构，完成检测模型、阈值规则、告警追溯、异常分析和大规模过程数据查询；',
    ],
  },
  {
    projectName: '智能应用平台定制化改造',
    cycle: 'TCL-中环材料 / 2025.02 - 至今',
    technologyStack: ['Nest.js', 'React', 'TypeScript', 'Docker'],
    projectBackground:
      '基于某开源智能应用平台，结合公司内部业务需求进行界面风格调整与功能改造，提升平台适用性与易用性。',
    duty: [
      '调整系统配色与交互样式，统一视觉体验；',
      '优化部分功能逻辑，增强权限控制粒度；',
      '对接后端服务，满足定制化配置与部署需求；',
    ],
  },
  {
    projectName: '炉炉互联系统',
    cycle: 'TCL-中环材料 / 2024.08 - 至今',
    technologyStack: ['Vue2', 'Webpack', 'Element UI', 'Vue-CLI', 'Java', 'SpringBoot'],
    projectBackground:
      '该系统聚焦异常工艺过程监控，通过异常数据预警、红线报警、自动推送等功能，实现炉台运行状态全面监控。同时引入炉台好坏自驱学习模型，助力降本增效。',
    duty: [
      '负责系统前端架构设计与页面开发，实现关键功能可视化呈现；',
      '推动前后端联调与数据交互设计，确保数据流转高效稳定；',
      '负责项目进度管理、需求拆解与跨部门沟通，确保开发节奏与业务目标一致；',
    ],
  },
  {
    projectName: '视觉模型系统',
    cycle: 'TCL-中环材料 / 2024.08 - 2025.04',
    technologyStack: [
      'TypeScript',
      'AutoImport',
      'UnoCSS',
      'Vite4',
      'Java',
      'SpringBoot',
    ],
    projectBackground:
      '用于展示视觉模型图片与识别结果，提升模型数据可视化与交互效率。',
    duty: [
      '实现模型图片与识别数据的展示与交互功能；',
      '支持模型数据实时更新与历史数据回溯浏览；',
      '使用 ECharts 实现多图表可视化展示；',
      '优化页面性能，提升系统稳定性与加载速度；',
    ],
  },
  {
    projectName: '工艺 SOP 参数监控系统',
    cycle: 'TCL-中环材料 / 2024.08 - 2025.03',
    technologyStack: [
      'Vue3',
      'TypeScript',
      'AutoImport',
      'UnoCSS',
      'Vite4',
      'ECharts',
    ],
    projectBackground:
      '实现工艺参数的实时监控、预警与可视化，辅助工艺人员进行过程管控。',
    duty: [
      '使用 ECharts 实现多图表可视化展示；',
      '集成实时推送功能，确保数据时效性与准确性；',
    ],
  },
  // {
  //   projectName: 'FDC 系统前端设计开发',
  //   cycle: 'TCL-中环材料 / 2024.06 - 2024.11',
  //   technologyStack: ['Vue3', 'TypeScript', 'AutoImport', 'UnoCSS', 'Vite4'],
  //   projectBackground:
  //     '面向参数采集与过程控制的前端系统，聚焦数据可视化与性能优化。',
  //   duty: [
  //     '主导系统前端架构设计与技术栈升级；',
  //     '推行组件化开发、路由懒加载与代码分割；',
  //     '开发参数配置、监控展示等核心模块；',
  //   ],
  // },
  {
    projectName: 'PMS 系统前端设计开发',
    cycle: 'TCL-中环材料 / 2024.01 - 至今',
    technologyStack: ['Vue2', 'Webpack', 'UnoCSS', 'Vue3', 'Vant UI', 'Uniapp'],
    projectBackground: '涵盖 PC + PDA 双端系统，提升生产执行流程管理效率。',
    duty: [
      '负责 PC 与 PDA 端前端开发，设计统一交互体验；',
      '开发串口监听组件，实现设备数据采集；',
      '优化前后端联调机制，提升系统响应与同步速度；',
    ],
  },
  {
    projectName: '环晔 MES 系统',
    cycle: 'TCL-中环材料 / 2023.08 - 2024.01',
    technologyStack: ['Vue2', 'Element UI'],
    projectBackground:
      '推动清洗工序、料签打印等产线业务线上化，提升产线透明度与管理效率。',
    duty: [
      '负责 PC 端界面整体设计与实现，提升用户操作体验；',
      '与后端联调接口，确保数据交互准确高效；',
      '现场对接业务需求，测试系统',
      '实现 56 项功能模块，包括打签、破碎、封托等工序环节；',
    ],
  },
  // 以下为你上一家公司（信永中和）项目 ↓↓↓
  {
    projectName: '智能合并报表及附注审核工具',
    cycle: '信永中和 / 2023.03 - 2023.08',
    technologyStack: ['Vue3', 'Vite4', 'D3', 'TypeScript', 'Pinia', 'VueUse'],
    projectBackground:
      '自动化处理合并报表及附注，降低人工投入并提升数据质量，实现工具产品化。',
    duty: [
      '基于 D3 绘制流程图，提升流程可视化表达；',
      '开发用户指引与页内 tab 组件（keep-alive 实现）；',
      '负责模块划分、路由设计、产品对接与 code review；',
    ],
  },
  {
    projectName: 'SW-GPT 内网智能问答服务',
    cycle: '信永中和 / 2023.05 - 2023.06',
    technologyStack: ['Vue3', 'Ping++', 'ChatGPT'],
    projectBackground:
      '基于 ChatGPT API 构建的内网定制化问答系统，提升内部知识获取效率。',
    duty: [
      '调研并二次开发 chatgpt-web-share 项目；',
      '集成内网登录系统，实现用户权限管理；',
      '接入 Ping++ 实现计费功能模块；',
    ],
  },
  {
    projectName: '银行贷款分析系统',
    cycle: '信永中和 / 2023.02 - 2023.03',
    technologyStack: ['Vue3', 'Element Plus', 'Socket.io', 'Nest.js'],
    projectBackground: '提供多银行年度数据上传与分析，输出分析报告与图表展示。',
    duty: [
      '实现大文件切片上传与实时进度推送（Socket.io）；',
      '使用 Nest.js 编写中间件服务并对接第三方分析平台；',
      '负责模块划分、接口联调与业务对接；',
    ],
  },
  {
    projectName: 'H-GZ-F 数据分析平台',
    cycle: '信永中和 / 2022.08 - 2022.12',
    technologyStack: ['React', 'ECharts', 'em'],
    projectBackground:
      '基于第三方分析产品二次开发的数据展示平台，支持大屏适配与图表展示。',
    duty: [
      '实现 em 单位的大屏适配方案；',
      '重构侧边栏与图表组件；',
      '负责任务分配、进度把控与业务联动；',
    ],
  },
  // {
  //   projectName: '流程挖掘系统',
  //   cycle: '信永中和 / 2020.12 - 2021.02',
  //   technologyStack: ['Vue2', 'Element', 'ECharts', 'D3', 'Vue CLI'],
  //   projectBackground:
  //     '用于流程分析与图表呈现的数据挖掘工具，支持自定义图表配置展示。',
  //   duty: [
  //     '负责项目搭建、路由设计与拖拽上传模块开发；',
  //     '封装基于 vue-grid-layout 的自适应画布；',
  //     '设计并实现图表配置交互方案，实现图表类型动态切换与数据绑定；',
  //   ],
  // },
])
</script>
