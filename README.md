# Clearframe · 数据分析工作台

一个中英双语的数据分析网站，以可视化操作实现常见 pandas 分析流程。所有用户数据在浏览器内处理，无需后端或 Python 环境。

## 本地使用

直接双击 `dist/index.html` 即可使用。也可以安装 Node.js 后，在本目录执行 `npm start`，浏览器打开 `http://localhost:4173`。项目不需要安装依赖。

## 功能与作业要求

- 自由加载数据：支持 CSV、TSV、JSON 对象数组，CSV 支持逗号、分号、制表符；支持 UTF-8 和 GB18030 / GBK。
- 默认数据：500 条模拟学生学习成绩，包含 12 个字段、30 个缺失单元格和 10 条重复记录，便于演示清洗。
- 数据探索：全文搜索、条件筛选、排序、分页、单元格编辑、字段类型与完整度画像。
- 数据清洗：删除缺失行，均值、中位数、众数、自定义值填充，去重、去空格、字段重命名、类型转换、删列、计算列。
- 可撤销流水线：记录数据操作，可撤销最近 20 步。
- 统计分析：描述统计、七种聚合方式、分组对比、透视表、Pearson 相关性热力图。
- 可视化：折线、柱状、散点、直方、环形图，维度配置、日期汇总、悬停数值、SVG 导出。
- 结果导出：原始数据、当前数据、筛选结果支持 CSV / JSON；分析结果支持 CSV。
- 双语：界面、说明、示例字段与类别对应切换，保留同一数据集与结果。
- 响应式：桌面、平板、手机布局；键盘焦点与对话框焦点约束。

## 数据说明

数据仅保存在当前页面内存中。刷新后恢复示例数据，重要结果请先导出。导入替换当前数据并清空历史。建议最多 20 MB、50,000 行、100 列；图表最多显示 30 个分组或 2,000 个散点；透视表每个维度最多 50 组。此项目实现 pandas 风格的常见功能，不是完整 pandas 运行时。

标准差为样本标准差（ddof=1）；分位数使用线性插值；相关系数排除成对缺失值；常量列的相关系数显示为空。示例数据为模拟数据，没有真实业务含义。

## 文件结构

- `dist/`：完整静态网站，无外部运行时依赖。
- `dist/engine.js`：数据解析、统计、清洗与聚合。
- `dist/app.js`：双语界面与页面结构。
- `dist/charts.js`：SVG 图表。
- `dist/events.js`：交互、导入、导出、撤销。
- `server.cjs`：本地静态预览服务。
- `tests/engine.test.cjs`：运行 `npm test` 检查核心数据功能。
- `演示讲解稿.txt`：约 4 分钟的视频讲解流程。

## English

Clearframe is a bilingual, browser-local data analysis studio inspired by pandas. Open `dist/index.html` directly, or run `npm start` and visit `http://localhost:4173`. No dependencies are required. The default sample contains 500 simulated student records, 12 columns, 30 missing cells and 10 duplicate rows. Import CSV, TSV or JSON; explore and clean data; compute columns; create grouped analyses, pivot tables and correlation matrices; configure five chart types and export results. Data stays in memory and resets on reload. Export important results before closing the page.
