# AI Action References

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
