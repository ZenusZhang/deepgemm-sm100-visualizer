# DeepGEMM SM100 FP8 GEMM 交互图

在线使用：https://ZenusZhang.github.io/deepgemm-sm100-visualizer/

修改 M 查看配置变化；点击方块查看数据布局，点击箭头查看搬运与同步；搜索参数可高亮依赖关系。

固定 N=4224、K=4096。页面包括 SMEM/TMEM 布局、persistent 调度、barrier 与参数依赖，以及对应的源码片段。

本仓库发布原始 `DeepGEMM_SM100_FP8_Layout_Claude.html`，文件名调整为 `index.html`，无需安装依赖。

页面分析对象为 [DeepGEMM](https://github.com/deepseek-ai/DeepGEMM)，并包含 CUTLASS 相关源码引用。页面中的构建信息记录了所引用源码的哈希前缀。
