---
id: 4
title: Plan AI-Native Textbook
stage: plan
date: 2025-12-04
surface: agent
model: claude-sonnet-4-5-20250929
feature: physical-ai-textbook
branch: 1-physical-ai-textbook
user: user
command: |
  /sp.plan AI-Native Textbook on Physical AI & Humanoid Robotics (Claude + Gemini + Spec-Kit Plus)

  Create:
  - High-level architecture sketch for the textbook (4-module structure + toolchain).
  - Chapter and section breakdown aligned with course flow and weekly learning map.
  - Research approach using research-concurrent methodology (gather sources while drafting).
  - Quality validation checklist for accuracy, reproducibility, and technical correctness.
  - Integration plan for Claude, Gemini, and Spec-Kit Plus throughout writing workflow.

  Architecture Sketch:
  - Book divided into 4 primary modules mirroring the Physical AI curriculum:
    1. ROS 2 – The Robotic Nervous System
    2. Digital Twin Systems – Gazebo & Unity
    3. NVIDIA Isaac AI-Robot Brain
    4. Vision–Language–Action Robotics (Whisper + LLM Planning)

  - Cross-cutting systems integrated into each module:
    - Perception → Planning → Control architecture
    - Simulation → Real-world → Edge deployment pipeline
    - LLM-based cognitive planning & natural-language command translation

  - Publishing architecture:
    -Markdown-first workflow → Docusaurus site → GitHub Pages deployment
    -Spec-Kit Plus generates structured spec → Claude/Gemini produce chapters → GitHub versioned drafts

  Section Structure:
  Phase 1 — Foundation (Weeks 1–5 content)
  - Introduction to Physical AI & Embodied Intelligence
  - Theoretical grounding: physics, perception, simulation, embodiment
  - ROS 2 fundamentals (Nodes, Topics, Services, Actions)
  - Humanoid URDF design and robotic nervous system concepts

  Phase 2 — Digital Twin Construction (Weeks 6–7)
  - Gazebo physics simulation pipelines
  - Unity for humanoid visualization and interaction
  - Sensor simulation: LiDAR, IMU, Depth cameras
  - Building realistic, physically consistent environments

  Phase 3 — AI-Robot Brain (Weeks 8–10)
  - NVIDIA Isaac Sim, Omniverse, and hardware-accelerated robotics
  - Isaac ROS: VSLAM, perception stacks, Nav2 planning
  - Reinforcement learning pipelines & synthetic data workflows
  - Sim-to-real transfer and deployment to Jetson edge kits

  Phase 4 — Vision-Language-Action Robotics (Weeks 11–13)
  - Voice-to-action using Whisper and far-field mic arrays
  - LLM-based task planning (Claude/Gemini → ROS 2 action graphs)
  - Multimodal humanoid control
  - Capstone system architecture: Autonomous humanoid robot project

  Phase 5 — Capstone Project
  - Voice command → LLM plan → perception pipeline → navigation → object manipulation
  - Assessment setup: simulation + edge deployment
  - Realistic hardware constraints & performance tuning

  Research Approach:
  - Research-concurrent: Gather sources actively during chapter drafting.
  - Prioritize:
    - ROS 2 official docs
    - NVIDIA Isaac Sim / Omniverse docs
    - Gazebo & Unity official docs
    - Peer-reviewed robotics papers (SLAM, VLA, RL, humanoid control)
  - Use Claude & Gemini to summarize and cross-reference technical papers.
  - Maintain a source library that maps each factual claim to verified references.

  Quality Validation:
  - Each chapter must pass:
    - Accuracy check: Cross-verified with official documentation
    - APA-style citation compliance
    - Reproducibility: Code samples must run in ROS 2, Gazebo, Isaac environments
    - Completeness: Covers weekly learning goals
    - Simulation correctness: URDFs, sensor configurations, and Nav2 pipelines must be technically valid
    - Hardware realism: Guidance must match actual Jetson/RTX hardware constraints
    - Embodiment relevance: Must connect theory → physical robot behavior

  Decisions Needing Documentation:
  1. Simulation Platform Strategy
     - Option A: Local RTX workstation (high CapEx)
     - Option B: Cloud-based “Ether Lab” (AWS/Azure) (high OpEx)
     - Tradeoff: Performance vs cost vs latency risks
     - Documentation required for both paths

  2. Robot Hardware Tier
     - Proxy robot (Unitree Go2)
     - Mini humanoid (OP3, G1)
     - Premium humanoid (Unitree G1)
     - Tradeoff: Cost, SDK openness, ROS integration, physical safety

  3. Code Stack
     - ROS 2 + Gazebo + Isaac + LLMs
     - Python-based rclpy for all examples
     - Tradeoff: simplicity vs performance

  4. VLA System
     - Whisper for speech
     - Claude/Gemini for planning
     - Tradeoff: context length vs speed vs reliability

  5. Simulation Fidelity
     - High-fidelity Isaac Sim vs faster but lower realism Gazebo
     - Tradeoff: realism vs compute cost

  Testing Strategy:
  Validation checks mapped to acceptance criteria:
  - **Module 1**: ROS 2 nodes compile, run, publish/subscribe correctly.
  - **Module 2**: Gazebo robot behaves with stable physics; Unity scene loads properly.
  - **Module 3**: Isaac SLAM pipeline produces consistent maps; Nav2 executes correct paths.
  - **Module 4**: Voice → plan → ROS 2 action graph functions end-to-end.

  Book Testing:
  - Ensure each lab is runnable on:
    - RTX workstation
    - AWS g5/g6e instances
    - Jetson Orin Nano for edge deployment

  - Validate:
    - URDF robot loads without joint errors
    - Navigation stack converges
    - VLA pipeline produces deterministic action plans
    - LLM instructions align with ROS 2 tasks
    - Voice commands recognized consistently

  Technical Details:
  - Research-concurrent writing throughout entire book creation process.
  - All citations must follow APA 7 style (as mandated in Constitution).
  - Organize work in four phases:
    1. **Research** (literature, official docs, robotics standards)
    2. **Foundation** (conceptual frameworks + definitions)
    3. **Analysis** (breakdown of modules, architectures, pipelines)
    4. **Synthesis** (capstone system + integrated humanoid robotics workflow)

  Outcome:
  A rigorously validated, academically aligned, industry-relevant textbook that teaches Physical AI from first principles to real-world deployment, complete with simulations, labs, LLM integration, and full humanoid robotics systems architecture.
labels: ["plan", "architecture", "textbook-development"]
links:
  spec: specs/1-physical-ai-textbook/spec.md
  ticket: null
  adr: null
  pr: null
files:
  - specs/1-physical-ai-textbook/plan.md
tests:

---

## Prompt

/sp.plan AI-Native Textbook on Physical AI & Humanoid Robotics (Claude + Gemini + Spec-Kit Plus)

Create:
- High-level architecture sketch for the textbook (4-module structure + toolchain).
- Chapter and section breakdown aligned with course flow and weekly learning map.
- Research approach using research-concurrent methodology (gather sources while drafting).
- Quality validation checklist for accuracy, reproducibility, and technical correctness.
- Integration plan for Claude, Gemini, and Spec-Kit Plus throughout writing workflow.

Architecture Sketch:
- Book divided into 4 primary modules mirroring the Physical AI curriculum:
  1. ROS 2 – The Robotic Nervous System
  2. Digital Twin Systems – Gazebo & Unity
  3. NVIDIA Isaac AI-Robot Brain
  4. Vision–Language–Action Robotics (Whisper + LLM Planning)

- Cross-cutting systems integrated into each module:
  - Perception → Planning → Control architecture
  - Simulation → Real-world → Edge deployment pipeline
  - LLM-based cognitive planning & natural-language command translation

- Publishing architecture:
  -Markdown-first workflow → Docusaurus site → GitHub Pages deployment
  -Spec-Kit Plus generates structured spec → Claude/Gemini produce chapters → GitHub versioned drafts

Section Structure:
Phase 1 — Foundation (Weeks 1–5 content)
- Introduction to Physical AI & Embodied Intelligence
- Theoretical grounding: physics, perception, simulation, embodiment
- ROS 2 fundamentals (Nodes, Topics, Services, Actions)
- Humanoid URDF design and robotic nervous system concepts

Phase 2 — Digital Twin Construction (Weeks 6–7)
- Gazebo physics simulation pipelines
- Unity for humanoid visualization and interaction
- Sensor simulation: LiDAR, IMU, Depth cameras
- Building realistic, physically consistent environments

Phase 3 — AI-Robot Brain (Weeks 8–10)
- NVIDIA Isaac Sim, Omniverse, and hardware-accelerated robotics
- Isaac ROS: VSLAM, perception stacks, Nav2 planning
- Reinforcement learning pipelines & synthetic data workflows
- Sim-to-real transfer and deployment to Jetson edge kits

Phase 4 — Vision-Language-Action Robotics (Weeks 11–13)
- Voice-to-action using Whisper and far-field mic arrays
- LLM-based task planning (Claude/Gemini → ROS 2 action graphs)
- Multimodal humanoid control
- Capstone system architecture: Autonomous humanoid robot project

Phase 5 — Capstone Project
- Voice command → LLM plan → perception pipeline → navigation → object manipulation
- Assessment setup: simulation + edge deployment
- Realistic hardware constraints & performance tuning

Research Approach:
- Research-concurrent: Gather sources actively during chapter drafting.
- Prioritize:
  - ROS 2 official docs
  - NVIDIA Isaac Sim / Omniverse docs
  - Gazebo & Unity official docs
  - Peer-reviewed robotics papers (SLAM, VLA, RL, humanoid control)
  - Use Claude & Gemini to summarize and cross-reference technical papers.
  - Maintain a source library that maps each factual claim to verified references.

Quality Validation:
- Each chapter must pass:
  - Accuracy check: Cross-verified with official documentation
  - APA-style citation compliance
  - Reproducibility: Code samples must run in ROS 2, Gazebo, Isaac environments
  - Completeness: Covers weekly learning goals
  - Simulation correctness: URDFs, sensor configurations, and Nav2 pipelines must be technically valid
  - Hardware realism: Guidance must match actual Jetson/RTX hardware constraints
  - Embodiment relevance: Must connect theory → physical robot behavior

Decisions Needing Documentation:
1. Simulation Platform Strategy
   - Option A: Local RTX workstation (high CapEx)
   - Option B: Cloud-based “Ether Lab” (AWS/Azure) (high OpEx)
   - Tradeoff: Performance vs cost vs latency risks
   - Documentation required for both paths

2. Robot Hardware Tier
   - Proxy robot (Unitree Go2)
   - Mini humanoid (OP3, G1)
   - Premium humanoid (Unitree G1)
   - Tradeoff: Cost, SDK openness, ROS integration, physical safety

3. Code Stack
   - ROS 2 + Gazebo + Isaac + LLMs
   - Python-based rclpy for all examples
   - Tradeoff: simplicity vs performance

  4. VLA System
     - Whisper for speech
     - Claude/Gemini for planning
     - Tradeoff: context length vs speed vs reliability

  5. Simulation Fidelity
     - High-fidelity Isaac Sim vs faster but lower realism Gazebo
     - Tradeoff: realism vs compute cost

Testing Strategy:
Validation checks mapped to acceptance criteria:
- **Module 1**: ROS 2 nodes compile, run, publish/subscribe correctly.
- **Module 2**: Gazebo robot behaves with stable physics; Unity scene loads properly.
- **Module 3**: Isaac SLAM pipeline produces consistent maps; Nav2 executes correct paths.
- **Module 4**: Voice → plan → ROS 2 action graph functions end-to-end.

Book Testing:
- Ensure each lab is runnable on:
  - RTX workstation
  - AWS g5/g6e instances
  - Jetson Orin Nano for edge deployment

- Validate:
  - URDF robot loads without joint errors
  - Navigation stack converges
  - VLA pipeline produces deterministic action plans
  - LLM instructions align with ROS 2 tasks
  - Voice commands recognized consistently

Technical Details:
- Research-concurrent writing throughout entire book creation process.
- All citations must follow APA 7 style (as mandated in Constitution).
- Organize work in four phases:
  1. **Research** (literature, official docs, robotics standards)
  2. **Foundation** (conceptual frameworks + definitions)
  3. **Analysis** (breakdown of modules, architectures, pipelines)
  4. **Synthesis** (capstone system + integrated humanoid robotics workflow)

Outcome:
A rigorously validated, academically aligned, industry-relevant textbook that teaches Physical AI from first principles to real-world deployment, complete with simulations, labs, LLM integration, and full humanoid robotics systems architecture.

## Response snapshot

The implementation plan for the "AI-Native Textbook on Physical AI & Humanoid Robotics" has been successfully created at `specs/1-physical-ai-textbook/plan.md`.

**Branch**: `1-physical-ai-textbook`
**Plan file path**: `specs/1-physical-ai-textbook/plan.md`

During the planning process, several architectural decisions were identified that warrant formal documentation.

📋 Architectural decision detected: Simulation Platform Strategy — Document reasoning and tradeoffs? Run `/sp.adr "Simulation Platform Strategy"`

I recommend you review the plan. The next logical step is to create the tasks using `/sp.tasks`.

## Outcome

- ✅ Impact: Successfully created a comprehensive implementation plan for the AI-Native Textbook, addressing architectural design, content structure, research approach, quality validation, and testing strategy.
- 🧪 Tests: N/A
- 📁 Files: `specs/1-physical-ai-textbook/plan.md` created.
- 🔁 Next prompts: Recommend running `/sp.adr` for architectural decisions and then `/sp.tasks` to create the detailed task list.
- 🧠 Reflection: Successfully generated a detailed plan despite the absence of PowerShell script, demonstrating adaptability in workflow. Clearly identified architectural decisions for separate documentation.

## Evaluation notes (flywheel)

- Failure modes observed: N/A
- Graders run and results (PASS/FAIL): N/A
- Prompt variant (if applicable): N/A
- Next experiment (smallest change to try): N/A
