# DeepGEMM SM100 交互可视化

- [FP8 GEMM：布局、数据流与同步](https://zenuszhang.github.io/deepgemm-sm100-visualizer/)：修改 M 查看配置变化；点击方块查看布局，点击箭头查看搬运与同步；搜索参数可高亮依赖关系。固定 N=4224、K=4096。
- [TMEM：Layout D / E / F / G](https://zenuszhang.github.io/deepgemm-sm100-visualizer/tmem.html)：在关系表选择合法 MMA 指令组合，修改 N，点击 W0–W3 分区查看 A/B 与物理 TMEM 的对应关系；点击 A/B 查看 SMEM 地址、swizzle、bank 和 descriptor。另附独立的小 M 对照。

- [TMEM → 寄存器 → SMEM：通用转置教学](https://zenuszhang.github.io/deepgemm-sm100-visualizer/transpose.html)：选择输入 M，对比 `.trans` 与不转置的结果；点击源 ID 联动查看 TMEM、寄存器、BF16 打包、SMEM 逻辑与物理地址，支持分步讲解。

三个页面均为自包含 HTML，可下载后离线打开，无需安装依赖。

| 文件 | 原始产物 |
|---|---|
| `index.html` | `DeepGEMM_SM100_FP8_Layout_Claude.html` |
| `tmem.html` | `DeepGEMM_SM100_TMEM_Layouts_Claude.html` |
| `transpose.html` | `DeepGEMM_SM100_TMEM_REG_SMEM_Transpose.html` |

TMEM 页面主图展示单 CTA、稠密、SS 形式下的合法指令与布局关系；N=64/128/256 是教学示例值。主图只展示第一条 MMA 的 K 片段，小 M 示例独立于主图设置。

页面分析对象为 [DeepGEMM](https://github.com/deepseek-ai/DeepGEMM)，并包含 CUTLASS 源码与 NVIDIA PTX 文档引用。可视化用于解释布局与地址映射，未运行 GPU 性能测试。