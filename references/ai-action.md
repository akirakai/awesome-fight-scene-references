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
