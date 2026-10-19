# Tiny VLA — AI Builders Lab

Two complementary Google Colab projects show how **vision + language becomes robot action**.

## 1. Tiny VLA From Scratch (improved)

[![Open From-Scratch VLA in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dujing82-blip/tiny-VLA/blob/main/Tiny_VLA_Colab.ipynb)

**File:** [Tiny_VLA_Colab.ipynb](Tiny_VLA_Colab.ipynb)

- TensorFlow; CPU-friendly; no external dataset.
- Three colored blocks and a 2D gripper.
- Six instructions: `touch/pick the red/blue/green block`.
- Synthetic expert **trajectories**, near-target and recovery states.
- Image-based color localization (engineered perception) + learned language-conditioned neural action policy.
- Explicit stopping/grasping guard, toggleable to compare with raw model behavior.
- Train, save/reload, animate, and evaluate task completion.

**Important:** The new version is a **hybrid**: engineered pixel-based color detection and an optional arrival guard help a learned action policy. It is not a large pretrained VLA. The teacher generates training labels only.

## 2. Pretrained SmolVLA + LIBERO

[![Open Pretrained VLA in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dujing82-blip/tiny-VLA/blob/main/Pretrained_SmolVLA_LIBERO_Colab.ipynb)

**File:** [Pretrained_SmolVLA_LIBERO_Colab.ipynb](Pretrained_SmolVLA_LIBERO_Colab.ipynb)

- **Real pretrained VLA** checkpoint: [lerobot/smolvla_libero](https://huggingface.co/lerobot/smolvla_libero).
- **Real robotics simulator**: LIBERO/robosuite (MuJoCo).
- Two camera views + robot state + benchmark language task → 7D robot action.
- Uses the **official LeRobot evaluation command** to load the checkpoint and execute it in simulation.
- Select task suite and task ID; inspect videos and success metrics.
- Requires Colab GPU, internet, larger downloads and potentially complex native dependencies.

**Important:** This pretrained notebook is a documented integration recipe, **not yet verified end-to-end in Colab**. Upstream package compatibility may require adjustments. LIBERO task instructions are selected by task index, not arbitrary user-entered text. The checkpoint is specifically trained for LIBERO; it is not a general-purpose language-controlled simulator.

## Learning objectives

| Question | From Scratch | Pretrained SmolVLA |
|---|---|---|
| How are language instructions encoded? | Visible word embedding code | Pretrained language backbone |
| Where do actions come from? | Trained behavior cloning policy | Pretrained VLA inference |
| What is the environment? | Simple 2D kinematic simulation | MuJoCo robotic manipulation |
| What hardware? | CPU | GPU strongly recommended |
| Can we type arbitrary text? | No: 6 supported templates | No: benchmark-defined tasks |

## Sources

- [LeRobot](https://github.com/huggingface/lerobot)
- [LIBERO evaluation guide](https://github.com/huggingface/lerobot/blob/main/docs/source/libero.mdx)
- [SmolVLA docs](https://huggingface.co/docs/lerobot/en/smolvla)
- [SmolVLA LIBERO checkpoint](https://huggingface.co/lerobot/smolvla_libero)
