flowchart TD

Start[Field Distortion Detected] --> Q1{Field-based or Act-based?}

Q1 -->|Field-based| Q2{Destabilizing horizontal stabilizer?}
Q1 -->|Act-based| NoDuty[No duty: Agent responsibility]

Q2 -->|Yes| Q3{Influencer self-correct?}
Q2 -->|No| Monitor[Monitor only]

Q3 -->|No| DutyActive[Duty to Testify Activates]
Q3 -->|Yes| Defer[Defer: monitor correction]

DutyActive --> Mode{Choose testimony mode}

Mode --> M1[Signal to Influencer]
Mode --> M2[Signal to Agent]
Mode --> M3[Signal to Both]
Mode --> M4[Escalate: temporary stabilizer]

M1 --> Reset[Post-testimony reset<br/>Witness decouples]
M2 --> Reset
M3 --> Reset
M4 --> Reset

Reset --> End[Return to tertiary position]