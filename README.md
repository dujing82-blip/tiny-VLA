# Tiny VLA — Vision + Language → Robot Action

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dujing82-blip/tiny-VLA/blob/main/Tiny_VLA_Colab.ipynb)

A simple **AI Builders Lab** Google Colab experiment showing how a small neural network can convert **camera images and natural-language commands** into 2D robot gripper movements.

## [▶ Open the Colab Notebook](https://colab.research.google.com/github/dujing82-blip/tiny-VLA/blob/main/Tiny_VLA_Colab.ipynb)

Choose **Runtime → Run all**. No external dataset required. CPU is sufficient.

### What students will see

- Three randomly placed colored blocks on a simulated tabletop.
- Language commands: `touch the red block`, `pick the blue block`, etc.
- An image CNN + word embedding + fusion network trained on synthetic demonstrations.
- A **saved and reloaded** `tiny_vla.keras` policy checkpoint.
- A 2D animated robot gripper taking neural-network-predicted actions.
- Training loss plots and basic success-rate evaluations.

### Important educational scope

This is a small, **trained-from-scratch** multimodal *imitation-learning* robot action model, not an externally pretrained frontier robotics VLA. Its 2D simulator is kinematic (no physics-based contact or joint-level robot arm). The expert controller supplies labels during training only. During evaluation the neural network supplies the actions. Six fixed instruction templates are supported; arbitrary natural-language instructions are not.

The point is to expose the essential VLA mapping: **vision + language → robot actions**, while keeping the code short enough for students to understand and modify.
