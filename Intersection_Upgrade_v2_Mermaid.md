# Mermaid Diagrams — Intersection Upgrade v2.0

## 1) Flowchart — Intersection Zone 2.0 Pipeline
```mermaid
flowchart TD
  A[Intent: main_KPI + guardrails] --> B[Decompose: 8 segments Hook->Setup->Tension->MicroPayoff->Build2->PayoffTwist->CTA->Anchor]

  subgraph Triggers_Unconscious
    A1[Curiosity_2_0]
    A2[Primal_Hooks fear_joy_urgency]
    A3[Mirror_Neuron_PP]
    A4[Identity_and_Cultural_Resonance]
    A5[Habit_Loop_and_Cliffhanger]
  end

  subgraph Algo_Signals
    B1[Velocity_of_Engagement]
    B2[WatchTime_and_CompletionSkip]
    B3[Retention_Gradient_5s]
    B4[Comment_Depth_DM_Share]
    B5[CrossPlatform_Echo]
  end

  B --> C{Intersection_Zone_2_0}
  A1 & A2 & A3 & A4 & A5 --> C
  B1 & B2 & B3 & B4 & B5 --> C
  C --> D[Measure: hold rewatch vol_up comment_per_min share_rate CTR_profile]
  D --> E[Recompose: keep_top_segments remove_noise AB_test hook music cut voiceover]
  E --> F[Ship_and_Log]
  F -->|sentinel_metrics| G{Targets_reached}
  G -->|No| B
  G -->|Yes| H[Scale: series + cross_video_anchoring]
```

---

## 2) Sequence — Trigger → Behavior Signal → Algorithm Boost
```mermaid
sequenceDiagram
  autonumber
  actor Viewer
  participant Video
  participant Platform as Algo_Feed
  participant Metrics as Metrics_Store

  Viewer->>Video: 0-3s Hook Curiosity_2_0
  Video-->>Viewer: POV + immersive_audio Mirror_Neuron_PP
  Viewer->>Platform: pause_3s rewatch_segment
  Platform->>Metrics: log velocity hold rewatch vol_up
  Platform-->>Viewer: feed_boost_to_similar_cohorts

  Viewer->>Video: continue Tension -> MicroPayoff
  Video-->>Viewer: identity_cue + cultural_cue
  Viewer->>Platform: comment_10plus_words DM_share
  Platform->>Metrics: update retention_gradient
  Platform-->>Viewer: wider_distribution Intersection_Zone_met
```

---

## 3) Gantt — Timeline of 8 Functional Segments + KPI Windows
```mermaid
gantt
  title 8 Segment Timeline with KPI Windows
  dateFormat  ss
  axisFormat  %Ss

  section Segments
  Hook_0_3s            :done,    s0, 0, 3
  Setup_3_7s           :active,  s1, 3, 4
  Tension_7_to_X       :         s2, 7, 6
  MicroPayoff          :milestone, s3, 13, 1
  Build2               :         s4, 14, 6
  Payoff_Twist         :crit,    s5, 20, 4
  CTA_Soft             :         s6, 24, 3
  Anchor_Motif         :         s7, 27, 3

  section KPI_Windows
  Velocity_0_30s       :          k0, 0, 30
  Retention_Gradient   :          k1, 0, 30
  Comment_Depth_10p    :          k2, 10, 20
  DM_Share_Window      :          k3, 12, 25
```

---

## 4) State — Attention States & Transitions
```mermaid
stateDiagram-v2
  [*] --> Idle
  Idle --> Hooked: Curiosity_2_0 or Primal
  Hooked --> Engaged: POV and sensorimotor cues
  Engaged --> Anticipation: tension_build
  Anticipation --> MicroPayoff: mini_release
  MicroPayoff --> ReEngage: novelty_bump
  ReEngage --> Payoff: twist_or_resolution
  Payoff --> CTA: social_cue
  CTA --> Recall: anchor_motif
  Recall --> [*]

  note right of Anticipation
    Signals monitored:
    - velocity
    - hold and rewatch
    - retention_gradient
    - comment_depth and DM_share
  end note
```

---

## 5) Class — Component Interfaces
```mermaid
classDiagram
  class Trigger {
    +type: Curiosity|Primal|Mirror|Identity|Habit|Cultural
    +intensity: number
    +emit(): Signal[]
  }
  class Signal {
    +name: Velocity|WatchTime|Retention|CommentDepth|DMShare|Echo
    +value: number
  }
  class Segment {
    +name: Hook|Setup|Tension|MicroPayoff|Build2|Payoff|CTA|Anchor
    +triggers: Trigger[]
    +targets: Signal[]
  }
  class Experiment {
    +kpi_primary: string
    +kpi_guardrail: string[]
    +variants: Segment[][]
    +run(): Result
    +counterfactual(): Result
  }
  Trigger --> Signal : emits
  Segment "8" o-- "many" Trigger
  Segment "8" o-- "many" Signal
  Experiment "1" --> "many" Segment
```
