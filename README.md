# LIBERO 逐秒空间动作标注查看页（v2，strata）

在线页面：https://fallingstar56.github.io/annotation-strata/

LIBERO（LeRobot v2，1693 个 episode，10 fps）每 1 秒一条英文动作指令，共 28096 条，由 Qwen3.8-Flash-Next（ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF，IQ3_S 量化）在 strata 引擎上结合机器人本体状态生成。提示词、输入帧、本体状态提示、输出解析和重试规则与 v1 相同。v1（Qwen3-VL-30B-A3B-Instruct + vLLM）见 [annotation](https://fallingstar56.github.io/annotation/)。生成代码见 [Omnimodel-Language-Annotation](https://github.com/fallingstar56/Omnimodel-Language-Annotation)（`scripts/annotate_libero_strata.py`、`scripts/build_site.py`）。

- `index.html`：按 episode 编号、任务、质检提示筛选。
- `episode.html?ep=N&t=S`：打开第 N 个 episode 的第 S 秒。点击某秒或按 `←`/`→` 跳转并只播放该秒，`空格` 播放本秒，`,`/`.` 逐帧。
- `data/`：每个 episode 的标注 JSON；`videos/`：外部相机 256×256 视频，每秒一个关键帧（与 v1 相同）。

标注是模型草稿，语义准确率尚未经人工验收。橙色标记只是自动质检提示，不是完整的错误清单。页面逻辑与 v1 完全一致，只有首页说明里的模型名改成了 v2 实际使用的模型。
