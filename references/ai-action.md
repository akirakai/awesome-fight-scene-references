# AI Action References

## MagicFight / KungFu-Fiesta — Two-Person Martial Arts Video Generation
- Paper: https://arxiv.org/abs/2601.02107
- Video dataset: https://huggingface.co/datasets/MingfuYAN/KungFu-Fiesta
- Study: a research system and dataset built specifically around two-person martial-arts combat, with paired combat videos and DWPose skeleton sequences.
- Movement design: the reference data separates two fighter identities while preserving coordinated attack/defense motion, footwork and body contact across a shared pose sequence.
- Camera / editing: the dataset is especially useful for inspecting body mechanics without cinematic editing hiding errors; pose videos can be compared directly against rendered combat motion.
- AI-video takeaway: one of the clearest references for why two-person combat needs explicit identity assignment and a shared motion plan. Define Fighter A and Fighter B separately, preserve their sides/roles, and map every attack to a corresponding defensive response.
- Tags: ai-video, martial-arts, two-person-interaction, pose-control, identity-consistency, dwpose
