# Tasks: AI-Native Textbook on Physical AI & Humanoid Robotics

**Input**: Design documents from `/specs/1-physical-ai-textbook/`
**Prerequisites**: plan.md (required), spec.md (required for user stories)

**Tests**: Tests are included as requested in the feature specification and plan.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Single project**: `book/docs/`, `book/code/`, `book/.github/workflows/`

## Phase 1: Setup & Foundational (Shared Infrastructure)

**Purpose**: Project initialization, Docusaurus setup, and core infrastructure for textbook content.

- [ ] T001 Initialize Docusaurus project structure for the textbook in `book/`
- [ ] T002 Configure Docusaurus `docusaurus.config.js` for 7 chapters/modules in `book/docusaurus.config.js`
- [ ] T003 Create `docs/intro.md` for "Introduction to Physical AI & Embodied Intelligence" in `book/docs/intro.md`
- [ ] T004 Create `docs/hardware-requirements.md` for hardware setup (RTX, Jetson, RealSense, Unitree) in `book/docs/hardware-requirements.md`
- [ ] T005 Create `docs/lab-architecture.md` for On-Prem vs Cloud "Ether Lab" comparison in `book/docs/lab-architecture.md`
- [ ] T006 Define `_category_.json` files for all 4 modules and Capstone in `book/docs/module1-ros2/_category_.json`, `book/docs/module2-digital-twin/_category_.json`, `book/docs/module3-isaac-ai-brain/_category_.json`, `book/docs/module4-vla-robotics/_category_.json`, `book/docs/capstone-project/_category_.json`
- [ ] T007 Establish research-concurrent workflow guidelines in `book/docs/workflow-guidelines.md`
- [ ] T008 Prepare decision logs for architectural choices in `history/adr/`
- [ ] T009 Outline Perception → Planning → Control architecture in `book/docs/robot-architecture.md`
- [ ] T010 Establish APA citation guidelines and tooling setup in `book/docs/citation-guide.md`

---

## Phase 2: User Story 1 - Learning Physical AI Fundamentals (P1) 🎯 MVP

**Goal**: Student understands foundational Physical AI concepts and ROS 2 fundamentals.

**Independent Test**: Can explain core concepts and ROS 2 communication mechanisms.

### Implementation for User Story 1

- [ ] T011 [US1] Draft content for "Physical AI Foundations" in `book/docs/intro.md`
- [ ] T012 [US1] Draft content for "ROS 2 Nodes, Topics, Services, Actions" in `book/docs/module1-ros2/nodes-topics.md`
- [ ] T013 [US1] Draft content for "rclpy for Python-based robotic agents" in `book/docs/module1-ros2/rclpy.md`
- [ ] T014 [US1] Draft content for "Humanoid URDF design" in `book/docs/module1-ros2/urdf-design.md`
- [ ] T029 [US3] Draft content for "Creating control loops, sensor streams, and actuator commands" in `book/docs/module1-ros2/control-loops.md`
- [ ] T015 [P] [US1] Create rclpy example for basic pub/sub in `book/code/ros2_examples/basic_publisher_subscriber.py`
- [ ] T016 [P] [US1] Create sample URDF for a simple humanoid in `book/code/urdf_examples/simple_humanoid.urdf`
- [ ] T017 [US1] Add lab tasks for ROS 2 package creation in `book/docs/module1-ros2/lab-tasks.md`
- [ ] T018 [US1] Test: Verify ROS graph connectivity using `ros2 graph` for `book/code/ros2_examples/basic_publisher_subscriber.py`

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 3: User Story 2 - Simulating Robotic Systems (P1)

**Goal**: Student can set up and run robotic simulations using Gazebo & Unity.

**Independent Test**: Can run a basic humanoid simulation and integrate sensors.

### Implementation for User Story 2

- [ ] T019 [US2] Draft content for "Gazebo physics simulation, collisions, forces" in `book/docs/module2-digital-twin/gazebo-physics.md`
- [ ] T020 [US2] Draft content for "Unity for rendering and human-robot interactions" in `book/docs/module2-digital-twin/unity-hri.md`
- [ ] T021 [US2] Draft content for "Sensor simulation: LiDAR, IMU, RGB-D cameras" in `book/docs/module2-digital-twin/sensor-sim.md`
- [ ] T022 [P] [US2] Create Gazebo model for a humanoid with basic physics in `book/code/gazebo_models/humanoid_physics.sdf`
- [ ] T023 [P] [US2] Create Unity scene for humanoid visualization in `book/code/unity_scenes/humanoid_scene.unity`
- [ ] T024 [P] [US2] Implement basic sensor plugin for Gazebo in `book/code/gazebo_plugins/simple_sensor.cpp`
- [ ] T025 [US2] Add lab tasks for digital twin setup and sensor integration in `book/docs/module2-digital-twin/lab-tasks.md`
- [ ] T026 [US2] Test: Validate URDF loading in Gazebo for `book/code/gazebo_models/humanoid_physics.sdf`
- [ ] T027 [US2] Test: Validate sensor noise models in simulation for `book/code/gazebo_plugins/simple_sensor.cpp`

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 4: User Story 3 - Controlling Humanoid Robots (P2)

**Goal**: Student can apply humanoid locomotion, manipulation, and kinematics.

**Independent Test**: Can program basic humanoid movements and understand kinematics.

### Implementation for User Story 3

- [ ] T028 [US3] Draft content for "Humanoid locomotion, manipulation, kinematics" in `book/docs/module3-isaac-ai-brain/locomotion-kinematics.md`
- [ ] T030 [P] [US3] Create ROS 2 control example for basic humanoid walk in `book/code/ros2_examples/humanoid_walk_controller.py`
- [ ] T031 [P] [US3] Implement forward kinematics solver for humanoid arm in `book/code/kinematics_examples/forward_kinematics.py`
- [ ] T032 [US3] Add lab tasks for humanoid control and kinematics in `book/docs/module3-isaac-ai-brain/lab-tasks-humanoid-control.md`
- [ ] T033 [US3] Test: Verify basic locomotion commands on simulated humanoid using `book/code/ros2_examples/humanoid_walk_controller.py`

**Checkpoint**: At this point, User Stories 1, 2, AND 3 should all work independently

---

## Phase 5: User Story 4 - Implementing Vision-Language-Action Systems (P2)

**Goal**: Student can develop and integrate Vision-Language-Action (VLA) systems for humanoid robots.

**Independent Test**: Can demonstrate a voice-to-action pipeline.

### Implementation for User Story 4

- [ ] T034 [US4] Draft content for "OpenAI Whisper for voice → command" in `book/docs/module4-vla-robotics/whisper-llm.md`
- [ ] T035 [US4] Draft content for "LLM cognitive planning (LLM → ROS 2 plan)" in `book/docs/module4-vla-robotics/llm-planning.md`
- [ ] T036 [US4] Draft content for "Multi-modal perception + action loops" in `book/docs/module4-vla-robotics/multimodal-control.md`
- [ ] T037 [P] [US4] Implement Whisper integration to capture voice commands in `book/code/vla_examples/voice_capture.py`
- [ ] T038 [P] [US4] Develop basic LLM prompt for converting natural language to ROS 2 actions in `book/code/vla_examples/llm_planner.py`
- [ ] T039 [US4] Create ROS 2 action server to execute LLM plans in `book/code/vla_examples/ros_action_server.py`
- [ ] T040 [US4] Add lab tasks for VLA pipeline construction in `book/docs/module4-vla-robotics/lab-tasks.md`
- [ ] T041 [US4] Test: Validate speech recognition accuracy for `book/code/vla_examples/voice_capture.py`
- [ ] T042 [US4] Test: Validate LLM plan determinism for `book/code/vla_examples/llm_planner.py`

**Checkpoint**: At this point, User Stories 1, 2, 3, AND 4 should all work independently

---

## Phase 6: User Story 5 - Building an Autonomous Humanoid System (P1) 🎯 Capstone

**Goal**: Student can integrate all learned concepts to build a capstone autonomous humanoid robot system.

**Independent Test**: Can deploy an autonomous humanoid system demonstrating integrated perception, planning, and action.

### Implementation for User Story 5

- [ ] T043 [US5] Draft content for "Capstone Autonomous Humanoid Robot System" in `book/docs/capstone-project/autonomous-humanoid.md`
- [ ] T044 [US5] Integrate Whisper, LLM Planner, and ROS 2 Action Server into unified system in `book/code/capstone/autonomous_humanoid_system.py`
- [ ] T045 [US5] Implement basic perception pipeline (object detection/tracking) for the capstone in `book/code/capstone/perception_pipeline.py`
- [ ] T046 [US5] Integrate Nav2 planning for bipedal humanoid locomotion within capstone in `book/code/capstone/navigation_integration.py`
- [ ] T047 [US5] Develop manipulation interface for object interaction in `book/code/capstone/manipulation_interface.py`
- [ ] T048 [US5] Document sim-to-real deployment tasks to Jetson in `book/docs/capstone-project/sim-to-real.md`
- [ ] T049 [US5] Add assessment setup and project rubric to `book/docs/capstone-project/assessment.md`
- [ ] T050 [US5] Test: End-to-end voice → plan → navigation → object interaction loop in simulation for `book/code/capstone/autonomous_humanoid_system.py`
- [ ] T051 [US5] Test: Validate performance on RTX workstation and Jetson Orin for capstone in `book/code/capstone/performance_validation.py`

**Checkpoint**: All user stories should now be independently functional

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Final review, consistency checks, and deployment preparation.

- [ ] T052 [P] Review `book/docs/` for overall structural consistency across all modules.
- [ ] T053 [P] Conduct comprehensive APA citation compliance check across all `book/docs/`.
- [ ] T054 [P] Create a glossary of key robotics and AI terms in `book/docs/glossary.md`.
- [ ] T055 [P] Verify all text-based diagrams are correctly described and formatted in `book/docs/`.
- [ ] T056 [P] Conduct a final editorial audit for clarity, grammar, and reading level across all `book/docs/`.
- [ ] T057 [P] Test Docusaurus site build locally in `book/`
- [ ] T058 [P] Prepare GitHub Actions workflow for GitHub Pages deployment in `book/.github/workflows/deploy.yml`
- [ ] T059 [P] Validate APA citation compliance for all `book/docs/` content.
- [ ] T060 [P] Verify hardware realism alignment in `book/docs/` for Jetson/RTX/Unitree guidelines.

---

## Dependencies & Execution Order

### Phase Dependencies

-   **Setup & Foundational (Phase 1)**: No dependencies - can start immediately.
-   **User Stories (Phase 2-6)**: All depend on Setup & Foundational phase completion.
    -   User Stories (Phase 2-6) can proceed in priority order (P1 → P2).
-   **Polish & Cross-Cutting Concerns (Phase 7)**: Depends on all desired user stories being complete.

### User Story Dependencies

-   User Story 1 (P1): Can start after Foundational. No dependencies on other stories.
-   User Story 2 (P1): Can start after Foundational. No dependencies on other stories.
-   User Story 3 (P2): Can start after Foundational. May integrate with US1/US2 concepts but should be independently testable.
-   User Story 4 (P2): Can start after Foundational. May integrate with US1/US2/US3 concepts but should be independently testable.
-   User Story 5 (P1): Can start after Foundational. Integrates all previous modules; highly dependent on US1-US4 for concepts and examples.

### Within Each User Story

-   Code examples should be drafted before integration tests.
-   Lab tasks should be added after content drafting.
-   Tests MUST be written and FAIL before implementation of the content/code they validate.

### Parallel Opportunities

-   All Setup & Foundational tasks can be run in parallel where independent (e.g., creating multiple `_category_.json` files).
-   Code example creation within each user story can be parallelized.
-   Different user stories (especially P1) can be worked on in parallel by different team members once foundational setup is complete.
-   Review and audit tasks in the Polish phase can be largely parallelized.

---

## Implementation Strategy

### MVP First (User Story 1 & 2 Only)

1.  Complete Phase 1: Setup & Foundational.
2.  Complete Phase 2: User Story 1 (Physical AI Fundamentals & ROS 2).
3.  Complete Phase 3: User Story 2 (Digital Twin Simulation).
4.  **STOP and VALIDATE**: Test User Stories 1 and 2 independently.
5.  Deploy/demo if ready (e.g., first few chapters of the Docusaurus site).

### Incremental Delivery

1.  Complete Setup & Foundational → Foundation ready.
2.  Add User Story 1 → Test independently → Deploy/Demo.
3.  Add User Story 2 → Test independently → Deploy/Demo.
4.  Add User Story 3 → Test independently → Deploy/Demo.
5.  Add User Story 4 → Test independently → Deploy/Demo.
6.  Add User Story 5 (Capstone) → Test independently → Deploy/Demo (full textbook).
7.  Each story adds value without breaking previous stories.

### Parallel Team Strategy

With multiple developers:

1.  Team completes Setup & Foundational together.
2.  Once Foundational is done:
    -   Developer A: User Story 1 & 2 (P1 focus)
    -   Developer B: User Story 3 & 4 (P2 focus)
    -   Developer C: User Story 5 (Capstone integration)
3.  Stories complete and integrate independently.

---

## Notes

-   [P] tasks = different files, no dependencies.
-   [Story] label maps task to specific user story for traceability.
-   Each user story should be independently completable and testable.
-   Verify tests fail before implementing.
-   Commit after each task or logical group.
-   Stop at any checkpoint to validate story independently.
-   Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence.
