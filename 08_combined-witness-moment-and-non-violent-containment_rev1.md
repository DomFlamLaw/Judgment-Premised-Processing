# Combined Witness Moment + Non‑Violent Containment Overlay

> This chart overlays the Non‑Violent Containment doctrine onto the Witness Moment flow **after Duty to Testify activates** and **before selecting testimony modes**. The irrational path is a **mode constraint** that governs *how* testimony proceeds and then returns the witness to tertiary position.

```mermaid
flowchart TD

  %% --- FIELD & ENTRY ---
  Field[Horizontal Field\nStable or Distorted] --> Entry{Agent crosses\nthe horizontal plane}

  %% --- WITNESS MOMENT ---
  Entry --> WitnessMoment[Witness Moment:\nVertical axis breach detected]
  WitnessMoment --> Q1{Is the breach\nmorally load-bearing?}

  %% --- IF NOT LOAD-BEARING ---
  Q1 -->|No| Silence[Duty of Silence:\nWitness remains tertiary]
  Silence --> Return1[Return to tertiary\nposition]

  %% --- IF LOAD-BEARING ---
  Q1 -->|Yes| Q2{Is the agent capable\nof self-correction?}

  %% --- SELF-CORRECTION YES ---
  Q2 -->|Yes| Hold[Hold Position:\nMonitor for correction]
  Hold --> Return2[Return to tertiary\nposition]

  %% --- SELF-CORRECTION NO -> DUTY TO TESTIFY ---
  Q2 -->|No| Testimony[Duty to Testify\nactivates]

  %% --- MODE SELECTOR (NEW) ---
  Testimony --> ModeSel{Context mode?}
  ModeSel -->|Rational| Mode[Select Testimony Mode]
  ModeSel -->|Irrational| NV[Non‑Violent Containment\n(mode constraint)]

  %% --- STANDARD TESTIMONY MODES (UNCHANGED) ---
  Mode --> M1[Signal to Agent]
  Mode --> M2[Signal to Influencer]
  Mode --> M3[Signal to Both]
  Mode --> M4[Escalate:\nTemporary stabilizer]

  %% --- NON‑VIOLENT CONTAINMENT SUB‑FLOW ---
  NV --> NV1[Rule 1 — Terrain Refusal:\nDo not enter irrational frame]
  NV1 --> NV2[Rule 2 — Boundary Supremacy:\nState once, enforce procedurally]
  NV2 --> NV3[Rule 3 — Audience Removal:\nReduce channels; prefer written cadence]
  NV3 --> NV4[Rule 4 — Exit Preservation:\nKeep non‑humiliating off‑ramps visible]
  NV4 --> NV5[Rule 5 — Time Compression:\nShorten loops; create decision gates]

  %% --- RESET / DECOUPLE ---
  M1 --> Reset[Post‑testimony reset:\nWitness decouples]
  M2 --> Reset
  M3 --> Reset
  M4 --> Reset
  NV5 --> Reset
  Reset --> Return3[Return to tertiary\nposition]

  %% --- STYLE (OPTIONAL) ---
  classDef dim fill:#f6f6f6,stroke:#bbb,color:#333,stroke-width:1px;
  class Silence,Hold,Return1,Return2,Return3,Reset dim;

  %% --- GROUPING (OPTIONAL SUBGRAPHS FOR READABILITY) ---
  subgraph S1 [Witness Gatekeeping]
    direction TB
    Entry --> WitnessMoment --> Q1 --> Q2
  end

  subgraph S2 [Testimony Paths]
    direction TB
    Testimony --> ModeSel
    subgraph S2A [Rational Context]
      direction TB
      ModeSel -->|Rational| Mode --> M1 & M2 & M3 & M4
    end
    subgraph S2B [Irrational Context]
      direction TB
      ModeSel -->|Irrational| NV --> NV1 --> NV2 --> NV3 --> NV4 --> NV5
    end
  end