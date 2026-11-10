# AI Action References

## Added 2026-11-10 — 2 new references

### MiniMax H3 武打导演 — 9 组 AI 对抗动作预设 / ComfyUI
- Watch: https://www.bilibili.com/video/BV1oFJ16BEH5/
- Related/creator/source: https://github.com/AI-KSK/aiksk-minimax-h3-local-prompt
- Action design: 重点检查攻击者 A 的每个动作能否在 B 身上产生对应反应、角色与刀剑是否发生无接触重叠；不要将预设宣传当作客观模型能力评测。
- Camera/editing: 先固定镜头观察身体与武器的接触点，再加入一个横向跟随镜头验证连续性；不同预设不要混在同一次生成中。
- AI takeaways: 适合搭建 MiniMax H3 与 Seedance 等模型的相同动作 Prompt 对照，记录命中率、动作完整度、身份漂移。
- Full motion prompt: [2026-11-10 daily run](runs/2026-11-10.md)
- Tags: MiniMax-H3,ComfyUI,workflow,AI-fight,contact-consistency,prompt-presets

### Moonlit Rooftop Staff vs Sword Duel — Zephyra Leigh / Seedance 2.5
- Watch: https://vflow.live/prompts/seedance-2-5/anime/moonlit-rooftop-staff-vs-sword-duel-676/
- Related/creator/source: https://x.com/ZephyraLeigh/status/2089748509843152982
- Action design: 完整 Prompt 含多阶段动作；建议只提取其中 3–5 秒「持棍防守→刀剑接触→侧移→解除交锋」，而非试图一个镜头照搬所有特效与腾空。
- Camera/editing: 由宽景建立屋顶与通风箱位置，动作中用低机位跟随；避免环绕镜头与急速人体旋转同时改变空间轴线。
- AI takeaways: 保留棍长、刀形、角色衣着与初始站位不变，分别对比固定全景版与动态镜头版，诊断武器接触是否真实。
- Full motion prompt: [2026-11-10 daily run](runs/2026-11-10.md)
- Tags: Seedance-2.5,original-prompt,staff-vs-sword,rooftop,weapon-consistency


## MagicFight / KungFu-Fiesta — Two-Person Martial Arts Video Generation
- Paper: https://arxiv.org/abs/2601.02107
- Video dataset: https://huggingface.co/datasets/MingfuYAN/KungFu-Fiesta
- Study: a research system and dataset built specifically around two-person martial-arts combat, with paired combat videos and DWPose skeleton sequences.
- Movement design: the reference data separates two fighter identities while preserving coordinated attack/defense motion, footwork and body contact across a shared pose sequence.
- Camera / editing: the dataset is especially useful for inspecting body mechanics without cinematic editing hiding errors; pose videos can be compared directly against rendered combat motion.
- AI-video takeaway: one of the clearest references for why two-person combat needs explicit identity assignment and a shared motion plan. Define Fighter A and Fighter B separately, preserve their sides/roles, and map every attack to a corresponding defensive response.
- Tags: ai-video, martial-arts, two-person-interaction, pose-control, identity-consistency, dwpose

## Text2Interact — High-Fidelity Two-Person Interaction Generation (ICLR 2026)
- Project / video: https://people.csail.mit.edu/frankzydou/projects/Text2Interact/
- Code: https://github.com/Qingxuan-Wu/Text2Interact
- Study: a 2026 two-person motion-generation system focused on fine-grained spatiotemporal coordination instead of treating two people as independent motion tracks.
- Movement design: the framework explicitly models initiation, response, contact ordering and relevant joint-pair relationships, which maps closely to the failure modes seen in AI fight videos.
- Camera / editing: the project demonstrations are intentionally simple, making interaction timing and contact quality easier to inspect than in cinematic examples.
- AI-video takeaway: write combat prompts as paired verbs, not solo actions: A initiates → B reacts → contact occurs → both recover. Preserve ordering words such as “before,” “as,” and “immediately after” because interaction quality depends on temporal coupling.
- Tags: ai-video, two-person-interaction, motion-generation, temporal-coupling, reaction, contact-order, iclr-2026

## UMF — Unified Number-Free Text-to-Motion Generation (CVPR 2026)
- Project / videos: https://githubhgh.github.io/umf/
- Paper: https://openaccess.thecvf.com/content/CVPR2026/html/Huang_Unified_Number-Free_Text-to-Motion_Generation_Via_Flow_Matching_CVPR_2026_paper.html
- Study: a 2026 multi-person motion system whose public demos include martial-arts exchanges, sparring and larger multi-agent interactions.
- Movement design: the same model can represent different numbers of participants, which makes the examples useful for studying how relative position and role assignment scale from a duel to a small group.
- Camera / editing: clean visualization removes cinematic noise and exposes whether timing, spacing and attack-response ordering remain coherent.
- AI-video takeaway: before adding cinematic style, describe the interaction topology: who is paired with whom, who initiates, who evades, and which participant stays passive. Multi-person action improves when relationships are explicit instead of implied by a generic “group fight.”
- Tags: ai-video, multi-person-motion, martial-arts, sparring, role-assignment, cvpr-2026

## WanToFight — Real-Time Generative Two-Player Combat Engine (2026)
- Project / videos: https://humanaigc.github.io/wantofight/
- Paper: https://arxiv.org/abs/2607.12592
- Study: a July 2026 generative game engine that synthesizes real-time two-player KOF ’97-style combat directly from keyboard controls.
- Movement design: its Player Association mechanism is especially relevant to AI fight generation because control signals must stay bound to the correct fighter while both characters attack, defend and cross positions.
- Camera / editing: the fixed fighting-game camera is ideal for diagnosing identity swaps, timing errors and contact incoherence without shot changes hiding mistakes.
- AI-video takeaway: for two-character reference-driven generation, treat identity binding as a first-class constraint: Fighter A keeps one costume/side/control role, Fighter B keeps the other, and crossing positions must never swap identities.
- Tags: ai-video, generative-game-engine, two-player, identity-binding, real-time, combat, 2026

## ReMoGen — Real-Time Human Interaction-to-Reaction Generation (CVPR 2026)
- Project / videos: https://4dvlab.github.io/project_page/remogen/
- Paper / code: https://github.com/4DVLab/ReMoGen
- Study: ReMoGen focuses on generating a person's reaction from another person's observed motion and supports human-human as well as human-scene interaction settings.
- Movement design: its reaction-generation formulation is highly relevant to combat because the responder should move from the attacker's latest action and contact context instead of following an unrelated independent motion track.
- Camera / editing: clean research visualizations make temporal causality and interaction errors visible without cinematic cutting masking them.
- AI-video takeaway: author fights in short reactive windows: Fighter A commits → Fighter B reacts → contact/spacing state changes → the next micro-segment follows from the new state. This is a better control model than generating both fighters independently for 15 seconds.
- Tags: ai-action, reaction-generation, two-person-interaction, temporal-causality, short-segments, cvpr-2026

## DynaVid — Highly Dynamic Video Generation with Synthetic Motion Data
- Project / videos: https://jinwonjoon.github.io/DynaVid/
- Paper: https://openaccess.thecvf.com/content/CVPR2026/html/Jin_Learning_to_Generate_Highly_Dynamic_Videos_using_Synthetic_Motion_Data_CVPR_2026_paper.html
- Study: a CVPR 2026 system specifically targeting vigorous human motion and extreme camera movement, including highly dynamic camera control.
- Motion design: the method separates a motion generator that predicts motion/optical flow from a motion-guided RGB video generator, decoupling trajectory planning from appearance rendering.
- Camera / editing: the public examples include extreme camera motion, making the project useful for thinking about camera trajectory as an independent control signal rather than a by-product of the visual prompt.
- AI-video takeaway: design fight generation in two layers: first lock body displacement, contact timing and camera path; then render identity, costume, lighting and style. This reduces the temptation to solve motion and appearance simultaneously in one vague prompt.
- Tags: ai-video, dynamic-motion, optical-flow, camera-control, motion-planning, cvpr-2026

## HumanX — Reactive Fighting Learned from Human Videos
- Project / demos: https://wyhuai.github.io/human-x/
- Paper: https://arxiv.org/abs/2602.02473
- Study: a 2026 framework that compiles human video into physically plausible, generalizable humanoid interaction skills and explicitly evaluates reactive fighting among its interaction domains.
- Movement design: HumanX separates data synthesis from interaction-skill learning, which makes it useful for thinking about a fight as an initiator trajectory plus a physically conditioned response rather than two independent motions.
- Camera / editing: the research demos remove cinematic cutting, exposing whether timing, balance, spacing and reaction are physically coherent before any visual style is added.
- AI-video takeaway: author combat in paired causal windows—A commits → B reacts to the observed trajectory → contact/avoidance changes body state → both recover from the new state. Solve interaction physics first, then add camera and cinematic appearance.
- Tags: humanx, ai-action, reactive-fighting, human-video, physical-interaction, causal-response, 2026

## 2026-11-09 — 2 new verified-source references

### Shadow Strike — AI Assassin Scene (Seedance 2.0)
- Original watch: https://vimeo.com/1180872388
- Study: 比追求招式数量更重要的是追踪同一角色跨镜头的一致性；这是原作者自己声明的测试目标。
- Movement: 把潜行动作设计为暂停观察→移动→一次短促反应→稳定收势；可从中学习连续身份、装备与运动速度约束。
- Camera / editing: 将镜头运动和角色运动作为独立控制变量；优先使用中景横向跟随，减少一镜内同时急推、急旋及瞬移。
- AI-video takeaway: 适合设定“单角色参考图+跨镜头行动一致性”的可复用实验。以下提示词为本轮原创，非创作者原文。
- Tags: AI,Seedance-2.0,YouArt,single-reference,identity-consistency,stealth
- Full independent motion prompt and provenance: [2026-11-09 curated batch](runs/2026-11-09.md)

### LOCALS — Sergei Afonin's AI Action Short (Seedance 2.5 workflow)
- Original watch: https://vimeo.com/1234337183
- Study: 更接近有故事动机的 AI 动作短片：同一角色在咖啡馆、列车、医院等不同地点往返，适合研究跨空间人物与叙事状态继承。创作者称其为 action short；无证据证明每一场都是打斗。
- Movement: 场景转换时固定角色衣着、身体朝向及携带物；需要生成冲突时先设定单次攻防，避免自动将每个动作场景推断为拳脚打斗。
- Camera / editing: 以地点建立镜头→人物动作中景→情绪反应为基本节奏，跨场景利用视觉母题或动作匹配剪辑。
- AI-video takeaway: 适合多镜头制作流：角色图、场景图、时间码 Prompt、音效和最终剪辑分别控制；不将影片中未经核实的具体打斗动作当成事实。
- Tags: AI,Seedance-2.5,Higgsfield,character-consistency,action-storytelling,2026
- Full independent motion prompt and provenance: [2026-11-09 curated batch](runs/2026-11-09.md)

