# 来源与适用范围

以下是专业原则的参考资料，包含经典课程与实证研究；不是最新技术 API 文档。研究整理日期：2026-11-23。课程依据公开介绍与作者资料；新增论文阅读范围分别注明，未声称完整观看全部课程。

| 来源 | 支持的原则 | 使用边界 |
| --- | --- | --- |
| [Martin Jonasson & Petri Purho：Juice It or Lose It](https://gdcvault.com/play/1016789/Juice-It-or-Lose)；[作者演示源码](https://github.com/grapefrukt/juicy-breakout) | 在相同玩法上通过多层反馈改善交互表现，可逐层比较 | 原演示不是 PixiJS 实现，也不证明效果越多越好 |
| [Mariel Cartwright：Fluid and Powerful Animation within Frame Restrictions](https://gdcvault.com/play/1020575/Animation-Bootcamp-Fluid-and-Powerful) | 关键姿态、预备动作和时序，与响应性共同考虑 | 不能从课程简介推导所有小游戏的固定停顿或时长 |
| [Nicolae Berbece：Game Feel: Why Your Death Animation Sucks](https://www.gdcvault.com/play/1022759/Game-Feel-Why-Your-Death) | 从动作、声音到粒子、镜头和构图共同构建手感 | 不应将动作游戏死亡演出照搬到高频按钮 |
| [Riot Games：Visual Effects](https://www.riotgames.com/en/artedu/visual-effects) | 满足感、信息准确、清晰度与主题一致需要共同平衡 | 不将 Riot 的具体美术风格规定为通用标准 |
| [Riot Games：Clarity in League](https://www.leagueoflegends.com/en-us/news/dev/clarity-in-league/) | 各表现通道共享注意力空间，维持视觉层级与可识别性 | 原文针对竞技游戏，迁移时按单场景目标调整 |
| [Microsoft：Accessibility Feature Tags](https://learn.microsoft.com/en-us/gaming/accessibility/accessibility-feature-tags) | 镜头运动与视觉效果可关闭或调节的可验证性 | 本 skill 不据此宣称产品通过认证或无障碍合规 |
| [Sugiyama & Inoue，2026：Standalone and Combined Effects of Screen Shake](https://www.jstage.jst.go.jp/article/digrajprocsummer/2026/0/2026_11/_article/-char/en) | 短时组合可以优于单独效果，持续时间会改变组合收益 | 阅读摘要与正文方法、结果；24 人、特定 3D 攻击场景，不能把其时长直接当作所有游戏标准 |
| [Kao，2020：The effects of juiciness in an action RPG](https://experts.illinois.edu/en/publications/the-effects-of-juiciness-in-an-action-rpg/) | 特定实验中中/高反馈优于无/极端反馈，支持实际寻找有效区间 | 阅读机构收录摘要，未核验完整参数；不能推导统一效果数量或所有品类的曲线 |
| [Kao 等，CHI 2024：How does Juicy Game Feedback Motivate?](https://people.csail.mit.edu/dkao/pdf/3613904.3642656.pdf) | 需要保留动作与结果的可归因性；遮蔽成功反馈可能抵消增强 | 阅读摘要、讨论和局限；遮蔽/控制感是作者对现象的解释，未通过独立中介操纵确证 |
| [Lin 等，2022：What Features Influence Impact Feel?](https://arxiv.org/html/2208.06155v3) | 以停顿、声音一致性、镜头等维度组织打击反馈审视 | 阅读摘要、框架与相关正文；评论排名及游戏分析属于观察研究，不是因果实验 |

具体声音 prompt、事件配方、调参方式和验收流程是本 skill 针对项目目标的设计建议。实施时根据真实素材、频率、设备与玩家反馈调整。需要引用资料时链接支持该原则的原始页面；需要当前库行为时核对已安装版本与对应官方文档。

实证研究的简要解释与转化后的调优流程见 [有效叠加与强度调优](impact-stacking.md)；后者是本 skill 的工作方法，不是文献验证过的普适算法。
