# Multimodal Vision Agent Decision System

本项目是一个面向实时交互场景的多模态 Agent 决策系统，目标是在自研或授权的私有测试环境中，验证 AI Agent 在动态 3D 场景下的自主感知、状态理解、任务规划与闭环控制能力。

系统以 YOLO 目标检测模型作为视觉感知核心，从实时画面中识别关键对象、空间位置、交互节点和风险因素，并将非结构化视觉信息转化为可供 Agent 推理的结构化状态。上层 Agent 基于这些状态信息完成任务优先级判断、路径选择、风险规避和动作规划，最终输出标准化动作指令，并通过视觉反馈持续修正行为。

## Core Workflow

```mermaid
flowchart TD
    A[Real-Time Visual Input] --> B[YOLO Object Detection]
    B --> C[Detection Results]
    C --> D[State Modeling Module]
    D --> E[Shared State Memory]

    E --> F[Vision Agent]
    E --> G[Planning Agent]
    E --> H[Decision Agent]
    E --> I[Recovery Agent]

    F --> J[Environment Understanding]
    G --> K[Task Planning]
    H --> L[Action Selection]
    I --> M[Exception Handling]

    J --> N[Action Executor]
    K --> N
    L --> N
    M --> N

    N --> O[Standardized Control Command]
    O --> P[Private Test Environment]
    P --> A
