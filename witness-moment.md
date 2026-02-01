flowchart TD

%% --- FIELD & ENTRY ---
Field[Horizontal Field<br/>Stable or Distorted] --> Entry{Agent crosses<br/>the horizontal plane}

%% --- WITNESS MOMENT ---
Entry --> WitnessMoment[Witness Moment:<br/>Vertical axis breach detected]

WitnessMoment --> Q1{Is the breach<br/>morally load-bearing?}

%% --- IF NOT LOAD-BEARING ---
Q1 -->|No| Silence[Duty of Silence:<br/>Witness remains tertiary]
Silence --> Return1[Return to tertiary<br/>position]

%% --- IF LOAD-BEARING ---
Q1 -->|Yes| Q2{Is the agent capable<br/>of self-correction?}
Q2 -->|Yes| Hold[Hold Position:<br/>Monitor for correction]
Hold --> Return2[Return to tertiary<br/>position]
Q2 -->|No| Testimony[Duty to Testify<br/>activates]

%% --- TESTIMONY MODES ---
Testimony --> Mode{Testimony Mode}
Mode --> M1[Signal to Agent]
Mode --> M2[Signal to Influencer]
Mode --> M3[Signal to Both]
Mode --> M4[Escalate:<br/>temporary stabilizer]

M1 --> Reset[Post-testimony reset:<br/>Witness decouples]
M2 --> Reset
M3 --> Reset
M4 --> Reset

Reset --> Return3[Return to tertiary<br/>position]
