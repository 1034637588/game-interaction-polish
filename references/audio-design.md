# 音效清单、prompt 与接入

## 每个音效条目的字段

按场景列出必要声音，不为覆盖表格而强行给所有动作配音。

- `id / 事件`：稳定素材名、业务或表现事件、触发条件。
- `用途 / 听感`：确认、材质、重量、节奏或结果识别；明确声音主次。
- `结构 / 时长`：起音、主体、尾音；是否拆层、一次性或循环。时长为初始目标。
- `同步`：对应的视觉关键帧或状态；可附相对偏移量，不只写“动画开始”。
- `变体`：不同录音或生成版本、可接受的轻微音高/音量变化。旋律和语义音型不能随意变调。
- `并发 / 混音`：同类发声数量、重复间隔、优先级、需要让位的声部、被取消时的收尾。
- `prompt / 检索词`：可独立复制的生成描述，以及素材库检索关键词。
- `格式 / 状态`：建议母版与项目支持的发布格式；已有、占位、待生成、待接入、已接入、已试听分别记录。

音量先通过实际素材试听匹配，不把任意增益或峰值规定成普适标准。确保高频触发时不削波，关键动作仍可辨认。

## prompt 写法

结构建议：单个声音事件 + 材质与动作 + 起音/主体/尾音 + 大致时长 + 听感目标 + 一次性/循环要求 + 排除项。

针对使用的生成器调整语言与格式；没有特定工具时可给英文生成 prompt 和中文用途说明。不要用“史诗、震撼、超级爽”替代声学描述。将多种不同事件分别生成，便于后续混音。生成器不能保证精确时长或循环无缝，需后期试听和编辑。

### 示例：晶体破裂

- ID：`sfx_crystal_break_01`。
- 同步：裂形出现的瞬间；不在手指刚按下、业务尚未接受时提前播放。
- 时长：约 0.25 秒；准备约 3 个自然变体作为起点。
- Prompt：`Single small crystal shatter sound effect. Crisp immediate attack, compact brittle cracking body, a few delicate high-frequency fragments with a fast decay. Light and satisfying rather than harsh. Approximately 0.25 seconds, isolated dry one-shot, no leading silence, no music, no voices, no background ambience, no long reverb.`
- 检索词：`small crystal shatter dry short glass break`。
- 并发：根据操作频率设置同类上限；必要时丢弃装饰碎屑层，保留主体命中确认。变体不能造成强弱意义混乱。

### 示例：机械转轮循环

- ID：`sfx_reel_spin_loop_01`。
- 同步：稳定转动阶段；启动、减速、停止使用独立过渡或声层。
- Prompt：`Steady compact mechanical reel spinning sound. Soft motor body with fine rhythmic ticks, controlled low-mid frequencies, restrained brightness. A consistent two-second texture intended for seamless looping, matching energy at both ends, no acceleration, no deceleration, no start or stop transient, no music, no voices, no ambience.`
- 检索词：`mechanical reel motor ticking seamless loop`。
- 检查：剪辑循环点并实际重复播放，确认接缝、节奏和底噪。不要假定生成结果天然无缝。

## 声音编排

- 按压确认、接触冲击、材质碎屑和结果提示承担不同职责。存在清晰的主体音时，其他层降低存在感或省略。
- 多转轮不机械地叠放多个满音量循环；可共享底层运动声，每列保留独立落位声。
- 计数和收集可按组播放，不按每枚装饰金币触发；视觉结束时，计数循环须停止并衔接收尾。
- 背景或持续声在关键揭晓时可短暂让位，随后自然恢复。未提供背景音乐时不擅自引入音乐系统。
- 静音时关键操作与结果仍应可理解；不要用声音作为唯一成功或错误提示。

## 接入与真实性

浏览器音频遵循用户手势解锁与项目现有音频管理方式；处理静音、加载失败、切后台和恢复，避免恢复时集中补播历史音效。只有在能力支持且符合用户范围时才实际生成或下载素材；检索到的音频需确认使用许可。

无音频工具时交付清单、prompt 和事件接入位置；可用原有素材或明确标记的占位。确需程序合成占位时只用于验证节奏，不将其称为最终声音设计。无法听音时明确注明“未试听”，即使播放调用已经成功。

建议输出表：

| ID | 事件/同步 | 听感/时长 | 变体/并发 | Prompt/检索词 | 文件/接入/试听状态 |
| --- | --- | --- | --- | --- | --- |

Prompt 较长时单独列出，以 ID 关联；不能只写“见音效建议”而缺少可复制内容。
