# 前端与 AI 全栈项目驱动学习

## 0. 目标与执行方式

### 总目标

用 24 周完成从“能看懂前端项目”到“能承担 Vue 3 企业业务开发”，再延伸到 React、Next.js 与 AI 应用工程化。第一阶段的通过标准不是背完语法，而是能在 Spring Boot 接口之上独立交付一个真实后台模块。

### 时间假设

- 每周 6 天、每天 2～3 小时；第 7 天只复盘和休息。
- 每天固定节奏：20 分钟知识卡片 → 80～120 分钟项目编码 → 20 分钟记录问题与提交 Git。
- 每周必须有可运行版本；学习内容只为当前迭代服务，遇到问题再补原理。
- 建议建立两个仓库：`smart-park-web`（Vue 前端）和 `smart-park-server`（Spring Boot 后端）。

### 项目主线：智慧园区管理系统

前端：Vue 3、TypeScript、Vite、Vue Router、Pinia、Axios、Element Plus、ECharts。
后端：Spring Boot、MyBatis-Plus、MySQL、Redis、JWT；第 14 周起加入 WebSocket。

模块按顺序交付：登录 → 园区/用户 CRUD → 角色权限 → 设备 → 告警 → Dashboard → 文件/Excel → 实时消息。每个模块都保留接口文档、截图、测试账号和 Git 提交记录。

## 1. 先建立验收基线

开始前用半天完成：安装 Node LTS、pnpm、VS Code、Git；创建 Vite Vue + TS 项目；配置 ESLint/Prettier；写一页学习日志。用 60 分钟完成一个不查资料的“用户列表静态页”。记录不会的点，不先补全课程。

每周评分：功能 40%、代码可读性 20%、接口/异常处理 20%、Git 记录与复盘 20%。低于 70 分，不增加新主题，先修复当前迭代。

## 2. 24 周路线总览

| 周次 | 交付物 | 主要知识 | 阶段验收 |
|---|---|---|---|
| 1 | 登录页静态版 | HTML、CSS、布局、表单 | 能读懂并修改页面 |
| 2 | 用户列表静态版 | JS、数组/对象、模块、DOM | 能处理列表与表单数据 |
| 3 | 用户列表交互版 | Promise、async/await、Fetch、浏览器存储 | 能看懂异步请求 |
| 4 | 类型化用户模块 | TS 类型、泛型、API 类型 | 能给页面和接口补类型 |
| 5 | 园区首页 | Vue 模板、ref/reactive、组件 | 能独立写简单 Vue 页面 |
| 6 | 用户查询页 | computed/watch、组件通信 | 能拆分业务组件 |
| 7 | 新增/编辑表单 | 表单校验、生命周期、slot | 能交付一个表单功能 |
| 8 | 多页面后台壳 | Router、layout、404、守卫基础 | 能完成页面跳转 |
| 9 | 登录态 | Pinia、Token、持久化 | 刷新后登录态正确 |
| 10 | API 层 | Axios 封装、拦截器、错误处理 | 能联调 Spring Boot |
| 11 | 用户 CRUD | Element Plus 表格/表单/弹窗/分页 | 完整 CRUD 可用 |
| 12 | 角色/菜单 | RBAC、动态菜单、按钮权限 | 完成 Level 6 验收 |
| 13 | 设备模块 | 上传、预览、下载、日期处理 | 能交付常见业务页 |
| 14 | 告警模块 | WebSocket、ECharts、Loading/空态 | 有实时数据与图表 |
| 15 | 园区综合模块 | 搜索、筛选、导入导出、复用组件 | 形成可复用页面模板 |
| 16 | 项目 1.0 | 联调、测试、部署、文档 | 达到可参与 Vue 企业项目 |
| 17 | React 基础 | JSX、组件、Props、State、Hooks | 能读写 React CRUD |
| 18 | React 企业实践 | Router、状态、Ant Design、权限 | 迁移一个 Vue 模块 |
| 19 | React 项目 | TypeScript、请求层、部署 | 完成 React 小项目 |
| 20 | Next.js | App Router、Layout、Server/Client | 能搭建 AI 应用壳 |
| 21 | AI UI | 流式输出、SSE、会话、Markdown | 完成聊天前端 |
| 22 | RAG | 文档上传、检索、引用展示 | 完成知识库页面 |
| 23 | Agent | Tool/Function Calling、任务流、MCP | 完成 Agent 操作台 |
| 24 | 全栈发布 | 安全、观测、Docker、复盘 | 发布 AI 全栈作品集 |

## 3. 每周每日执行清单

以下每天均指“学一个最小知识点 + 当天提交代码”，第 6 天为集成与验收。

### 第 1～4 周：基础只学到能写页面

**第 1 周：HTML/CSS 登录页**

- D1：语义标签、表单控件；写登录页结构。
- D2：选择器、盒模型、字体与颜色；完成视觉样式。
- D3：Flex、Grid、定位；完成响应式布局。
- D4：伪类、溢出、z-index；处理错误提示和空态。
- D5：拆出 Header、Form、Footer；适配移动宽度。
- D6：按截图重做登录页；验收：不看教程能修改间距、布局、表单控件。

**第 2 周：JavaScript 用户列表**

- D1：变量、函数、对象、数组、解构、展开；构造用户数据。
- D2：`map/filter/find/sort/reduce`；实现搜索、统计、排序。
- D3：模块 `import/export`、事件；拆分数据与渲染代码。
- D4：表单校验、DOM 常见操作；实现新增和删除。
- D5：防抖基础；让搜索输入减少重复计算。
- D6：完成无框架用户列表；验收：能解释每个数组方法为何使用。

**第 3 周：异步与浏览器能力**

- D1：Promise、`async/await`、try/catch；封装请求函数。
- D2：Fetch、JSON、URLSearchParams；接入一个 mock API。
- D3：`Promise.all/allSettled`；并发加载统计和列表。
- D4：localStorage、Cookie、URL；保存筛选条件和假 Token。
- D5：Loading、错误、空数据状态；补全异常分支。
- D6：将用户列表改为异步版；验收：断网时页面仍给出可理解提示。

**第 4 周：TypeScript 类型化**

- D1：基础类型、interface/type、可选属性；定义 `User`。
- D2：联合类型、枚举基础、函数类型；定义状态和操作类型。
- D3：泛型 `ApiResponse<T>`、`PageResult<T>`；定义分页接口。
- D4：`ref`/数组/对象类型；改造列表和表单。
- D5：类型断言、类型收窄；处理 API 的 null 与错误响应。
- D6：全量 `tsc` 无错误；验收：能把 Java DTO 翻译成 TS interface。

### 第 5～8 周：Vue 页面开发

**第 5 周：Vue 核心与组件**

- D1：Vite、SFC、模板指令；搭建园区首页。
- D2：`ref/reactive`；实现卡片和编辑表单。
- D3：`v-if/v-for/v-model`；实现列表筛选。
- D4：Props/emit；拆出搜索栏和表格工具栏。
- D5：computed 与生命周期；完成统计卡片。
- D6：组件目录整理；验收：能从空目录写出一个可交互页面。

**第 6 周：响应式与通信**

- D1：`watch` 监听查询条件；同步 URL 参数。
- D2：`watchEffect` 用于副作用；处理首次加载。
- D3：slot；制作通用 PageToolbar 和 EmptyState。
- D4：动态组件、`defineExpose` 基础；复用弹窗。
- D5：composable 基础；抽出 `usePagination`。
- D6：用户查询页；验收：父子组件边界清楚、无重复逻辑。

**第 7 周：表单与校验**

- D1：Element Plus Form/Input/Select；新增用户表单。
- D2：规则校验、提交状态；补必填、格式、重复提交保护。
- D3：编辑回填、详情只读；同一组件支持三种模式。
- D4：Dialog/Drawer/MessageBox；完成删除确认。
- D5：上传控件基础；接入头像预览。
- D6：表单异常测试；验收：刷新、取消、重复提交、服务端错误均可恢复。

**第 8 周：Router 与后台壳**

- D1：路由表、Layout、嵌套路由；搭建后台框架。
- D2：query/params、动态路由；完成用户详情。
- D3：导航菜单、面包屑、404。
- D4：路由守卫基础；未登录跳转登录。
- D5：路由懒加载、页面标题；补刷新行为。
- D6：验收：登录→列表→详情→返回链路完整，直接访问不存在地址有 404。

### 第 9～12 周：企业后台核心能力

**第 9 周：Pinia 登录态**

- D1：Store、state/getters/actions；建立 userStore。
- D2：登录接口模拟、Token 持久化；刷新恢复状态。
- D3：用户信息与菜单加载；统一初始化流程。
- D4：退出、过期、401 状态；清理本地数据。
- D5：权限判断 composable；实现 `hasPermission`。
- D6：验收：登录、刷新、退出、过期四条链路通过。

**第 10 周：Axios 与 Spring Boot 联调**

- D1：request 实例、baseURL、环境变量。
- D2：GET/POST/PUT/DELETE 与 params/data；对接用户 API。
- D3：请求/响应拦截器；自动加 Token、统一解包。
- D4：401、业务错误、网络错误；统一 Message 提示。
- D5：API 文件按领域拆分，定义 DTO 和返回类型。
- D6：用 Swagger/接口文档逐项核对；验收：浏览器 Network 与后端日志一致。

**第 11 周：标准 CRUD**

- D1：列表、搜索、分页；完成 UserList。
- D2：新增、编辑、详情；完成 UserForm/UserDetail。
- D3：删除、状态修改、批量操作。
- D4：Loading、空态、错误态、权限按钮。
- D5：抽出通用分页与弹窗逻辑；优化目录。
- D6：从零录屏完成 CRUD；验收：新同事按 README 可启动并使用。

**第 12 周：RBAC**

- D1：理解用户→角色→权限→菜单映射，定义 TS 模型。
- D2：后端返回菜单转路由；动态注册路由。
- D3：菜单显隐、路由守卫、刷新恢复。
- D4：按钮权限指令/组件；隐藏和禁用策略统一。
- D5：角色管理、权限分配页面。
- D6：权限矩阵测试；验收：不同账号只能看到和操作授权内容。

### 第 13～16 周：可交付企业模块

**第 13 周：设备模块**：图片/文件上传、预览、下载、日期处理；交付设备列表、表单、详情。

**第 14 周：告警与 Dashboard**：ECharts 柱线饼图、WebSocket 连接/重连/关闭、告警确认；交付实时告警面板。

**第 15 周：园区综合模块**：Excel 导入导出、复杂筛选、防抖节流、可复用表格；交付园区、人员、车辆三个列表。

**第 16 周：项目 1.0 发布**：补单元/接口冒烟测试、权限回归、Docker 构建、Nginx 部署、README、接口示例、演示视频；验收：新机器按文档 30 分钟内启动，能够独立讲清目录、请求链路和权限链路。

## 4. 第 17～24 周：在 Vue 交付能力之上扩展

每周仍按 D1～D5 学习、D6 集成：

- **17～19 周 React**：用 TypeScript 重写用户 CRUD；学习 JSX、函数组件、Props、`useState/useEffect/useMemo/useRef`、React Router、Context、Ant Design。验收：能读写一个带登录和分页的 React 模块。
- **第 20 周 Next.js**：App Router、Layout、Server/Client Component、Route Handler、Middleware、基础鉴权；交付 AI 应用壳。
- **第 21 周 AI 对话前端**：会话列表、Markdown、SSE 流式输出、取消请求、错误重试；对接任意 LLM API 的后端代理。
- **第 22 周 RAG**：文档上传、切分/检索状态、引用片段、权限隔离；交付知识库页面。
- **第 23 周 Agent**：工具调用、任务步骤、人工确认、运行日志、MCP 工具状态；交付 Agent 操作台。
- **第 24 周全栈发布**：Docker Compose、环境变量、日志与耗时、限流/鉴权、作品集文档；验收：可公开演示一个“知识库问答 + 园区数据查询 Agent”。

## 5. 每个知识点的统一学习卡

遇到任何新 API，都只写一张不超过一页的卡片：

1. **是什么**：一句话定义。
2. **为什么用**：对应当前项目的痛点。
3. **最小代码**：5～20 行可运行示例。
4. **项目位置**：落到哪个组件、store 或 API 文件。
5. **后端迁移提醒**：例如 `computed` 是派生值，不是数据库查询；`watch` 是副作用，不是所有计算的替代品。
6. **进入项目标准**：能独立完成一个小任务即可，不追求源码级理解。
7. **立即练习**：一个 30～60 分钟内完成的改动。

## 6. Level 1～12 验收清单

- **L1～L3**：能读懂目录、修改样式、按截图完成页面。
- **L4**：能定义接口类型、封装 Axios、处理 Loading/错误。
- **L5**：能完成一个真实 CRUD（搜索、分页、新增、编辑、删除、详情）。
- **L6**：能完成 Router、Pinia、Token、动态菜单和按钮权限。
- **L7～L8**：能独立交付设备/告警等模块，包含上传、图表或实时消息。
- **L9**：能同时修改 Spring Boot 接口和 Vue 页面并完成联调。
- **L10**：能迁移一个 Vue 模块到 React。
- **L11**：能完成带流式输出的 AI 应用。
- **L12**：能交付带 RAG、Agent、MCP、部署和文档的 AI 全栈作品。

## 7. 明确暂缓的内容

前 16 周不投入 Vue 响应式源码、Virtual DOM/Diff、React Fiber、浏览器渲染底层、复杂 TS 类型体操、Webpack/Vite 内部实现。只有当项目遇到性能、类型或构建问题时，才按问题补课。

## 8. 每周复盘模板

```text
本周交付：
可运行地址/截图：
我真正掌握的 3 个能力：
最常见的 3 个错误及原因：
前后端联调遇到的问题：
下周要删除/保留的学习内容：
Git 提交数：
```

最终作品集至少包含：项目架构图、登录与 RBAC 说明、一个完整 CRUD、一次 WebSocket 或 SSE、一次文件/Excel 能力、部署地址或演示视频，以及“Java 后端概念如何迁移到前端”的技术说明。
