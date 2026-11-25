# 工具与资源记录（Tools and Resources）

> 对应任务书「三、检索资料与开发工具」实践目标，以及「提交内容」第③项：整理找到的开源项目、插件或开发工具，附上相关链接及选择理由。
> 项目需求：家庭广告生意的「统一报价 + 按项目记账 + 往来欠款追踪 + 年度盈亏汇总」轻量工具。
> 记录日期：2026-11-22

## 一、检索过程：关键词怎么来的

去ai里面问问，网络里面搜了怎么去搜索关键词，然后借助ai的搜索功能搜了一些东西：  



| 项目里的实际需求 | 用的搜索关键词 | 渠道 |
| --- | --- | --- |
| 报价、录入、待办页面要有一套现成控件 | `vue3 组件库` / `vue3 ui component library` | GitHub 搜索、项目官网 |
| 流水、欠款、报价单是高频行编辑表格 | `vue data table component` / `vxe-table` | GitHub、官方文档 |
| 年度报表要画利润趋势和品类占比 | `vue chart library` / `echarts vue3` | GitHub、中文文档站 |
| 报表要导出给会计或报税 | `export excel javascript` / `sheetjs xlsx` | GitHub、npm |
| 报价表单要防漏填、防报错价 | `vue form validation` / `vee-validate` | GitHub、官方文档 |
| 老板和员工多端共享数据、按角色限权 | `cloudbase vue` / `腾讯云开发 Vue` | 腾讯云官方文档 |

**筛选标准：** ① 明确支持 Vue 3 + TypeScript；② 近一年仍有人维护、issue 有人回；③ 中文文档较全或文档结构清晰；④ 开源协议宽松（MIT / Apache-2.0）。

**过程中踩的一个判断坑：** 其实在一开始我把 star 数当第一标准，先找star数多的，但是搜出来许多东西都是很早的东西。后来把顺序改成"先看最近提交时间和 Vue 3 支持说明，再比 star"，筛选就好了不少。另外 `awesome-vue` 这类清单适合按类目补漏，但不能直接照抄，里面的东西可能有的是很久的了，还是得自己点进去看更新时间。

## 二、开源项目（6 个，附 GitHub 链接）

### ① Element Plus（UI 组件库）
- 关键词：`vue3 组件库` / `vue3 ui component library`
- 官网：https://element-plus.org/ ｜ GitHub：https://github.com/element-plus/element-plus
- 解决的问题：报价、录入、待办等页面的表单、弹窗、表格、日期选择等基础控件。
- 选用理由：Vue 3 生态最主流的组件库，中文文档齐全，MIT 协议可商用，技术栈一致。而且是有中文文档，以后在项目开发时候能减少不少的难度。

### ② vxe-table（表格组件）
- 关键词：`vue data table component` / `vxe-table`
- 官网：https://vxeui.com/v4 ｜ GitHub：https://github.com/x-extends/vxe-table
- 解决的问题：流水、欠款、报价单等大量数据的增删改查、排序、筛选、分页与导入导出。
- 选用理由：专为行编辑表格设计，支持虚拟滚动与导入导出打印，MIT 协议。不用自己编辑表格逻辑，很方便。

### ③ Apache ECharts（图表库）
- 关键词：`vue chart library` / `echarts vue3`
- 官网：https://echarts.apache.org/zh/index.html ｜ GitHub：https://github.com/apache/echarts
- 解决的问题：年度报表的利润趋势、各产品种类收入占比等可视化图表。
- 选用理由：国内最主流的开源图表库，图表类型丰富，Apache-2.0 免费商用；官方还有 Vue 封装 vue-echarts（https://github.com/ecomfe/vue-echarts ）， 不用自己包一层。

### ④ SheetJS / xlsx（导出库）
- 关键词：`export excel javascript` / `sheetjs xlsx`
- 官网：https://sheetjs.com/ ｜ GitHub：https://github.com/sheetjs/sheetjs
- 解决的问题：把年度报表、流水导出成 Excel，交给会计或报税使用。
- 选用理由：纯前端即可导出 xlsx / csv，社区版开源，浏览器端直接下载，符合"数据存自家云端、不上传第三方公开接口"的要求。

### ⑤ VeeValidate（表单校验）
- 关键词：`vue form validation` / `vee-validate`
- 官网：https://vee-validate.logaretm.com/v5/ ｜ GitHub：https://github.com/logaretm/vee-validate
- 解决的问题：报价、记账表单的数字格式、必填项、金额范围校验，防止报错价、漏填。
- 选用理由：Vue 生态主流校验库，支持组合式 API 与 schema 校验，与 TypeScript 配合良好。

### ⑥ 腾讯云开发 CloudBase（云服务）
- 关键词：`cloudbase vue` / `腾讯云开发 Vue`
- 官网文档：https://cloud.tencent.com/document/product/876 ｜ GitHub：https://github.com/TencentCloudBase/cloudbase-framework
- 解决的问题：云数据库、登录鉴权、静态托管一体化，支撑老板与员工多端协作和角色权限分级。
- 选用理由：和方案的"云管理"路线一致，自带身份认证和权限控制，免自建服务器，官方提供 Vue（Vite）快速开始文档。

**资源合集：** awesome-vue（https://github.com/vuejs/awesome-vue）按类目整理大量 Vue 组件，作为后续扩展的选件清单。

## 三、AI Agent 扩展（Skill / MCP）



| 资源 | 链接 | 能解决什么问题 | 对本项目的意义 | 状态 |
| --- | --- | --- | --- | --- |
| GitHub MCP Server | https://github.com/github/github-mcp-server | 让 Agent 直接读仓库、查 issue、提 PR | 后续整理两个提交仓库的变更记录时可能用得上 | 了解，未接入 |
| Context7 | https://github.com/upstash/context7 | 给模型喂最新版本的库文档，减少按旧版 API 写代码 | 查 Vue 3 / Element Plus 用法时避免过时回答 | 了解，未接入 |
| Playwright MCP | https://github.com/microsoft/playwright-mcp | 让 Agent 操作浏览器做端到端测试 | 原型跑起来后自动验证"员工报价 → 生成报价单 → 老板查看"整条流程 | 计划试用 |

Skill 方面，本阶段用的是现成 Agent 自带的几类能力（文档处理、资料检索、文件生成）。实际体会：特别方便呀。不用一直调教ai，而且很省token（兜里没钱了）另外搞清楚了 Skill 是**按需加载**的——不是装了就一直生效，得在任务里说清"用于哪个文件、要达到什么效果"才会被正确调用，这个触发条件一开始我还误解过。

## 四、开发工具（官方文档 / 插件市场 / 技术社区）

挑了和当前开发直接相关的：

| 工具 | 链接 | 用途 | 选用理由 |
| --- | --- | --- | --- |
| Chrome DevTools | https://developer.chrome.com/docs/devtools/ | 浏览器调试：看元素、样式、网络请求 | 报价页要同时适配手机和电脑，Elements / Network 面板排查最直接 |
| Apifox | https://apifox.com/ | 接口调试与文档（备选 Postman：https://www.postman.com/） | CloudBase 云函数要先跑通请求再写页面；中文文档和团队共享是选它的理由 |
| Vite | https://vite.dev/ ｜ GitHub：https://github.com/vitejs/vite | 构建工具与开发服务器 | 热更新快，和 Vue 3 官方模板配套 |
| GitHub Desktop | https://desktop.github.com/ | Git 图形化客户端 | 刚学 Git 时先用图形界面看清 commit / branch 到底发生了什么，再回命令行 |
| python-docx | https://github.com/python-openxml/python-docx | 用脚本批量处理 Word 文档 | 写计划书时真实用上了，见下面试用记录 |

## 五、试用记录（实际遇到的两个问题）

**试用：用 python-docx 整理计划书文档。** 目标是把四部分内容排成带自动目录的 Word，并做封面填写线。

1. **封面填写线会变长。** 一开始用一串下划线 `______` 当填写线，在 WPS 里打字时线被字符顶着越拉越长。改成用表格单元格的下边框（bottom border）画线，线固定在单元格底部，输入多少个字都不动。
2. **自动目录页码显示 0、新增标题不进目录。** 插入 TOC 域后结构是对的，但域结果没重新计算。在 WPS 里右键"更新域"后才刷新正常。

**效果与教训：** 目录最终能自动生成，封面填写线稳定。最大的体会是"自动生成"不等于"立刻正确"——域类内容一定要手动刷新一次再检查，不然交上去格式会很糟糕。

**下一步计划试用：** 用 Element Plus 的 `el-select` + `el-input-number` 搭一个按种类报价的最小表单，验证"选品类 → 自动带出计价单位 → 填数量 → 出价"这条链能否跑通；验收点是低于成本底线时能否锁定提交。


## 六、待办

- [ ] 实际接入一个 MCP 服务并记录效果
- [ ] Element Plus 报价表单 demo，验证成本底线锁定
- [ ] 本文件与 Git 学习记录、AI Agent 学习记录一起提交到笔记仓库
