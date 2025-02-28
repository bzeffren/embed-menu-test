# embed-menu-test

```mermaid
A[Entry Point] --> B[Begin Enrollment]

    B --> C{User Exists?}

    C -->|Yes| D{Missing Account Info & Google Login Enabled?}
    C -->|No| E[Email Form]

    D -->|Yes| F[Complete Account Info]
    D -->|No| J

    E --> G{Email Exists?}

    G -->|Yes| H[Password Form]
    G -->|No| I[Signup Form]

    F --> H

    H --> J{Password OK?}

    J --> K{Already Enrolled?}

    K -->|Yes| L[Already SignedUp View]
    K -->|No| M[Connect Bank]

    I --> M

    M --> N[Bank Accounts Loading]

    N --> O{Bank Account Supported?}

    O -->|No| P[Unsupported Account View]
    O -->|Yes| Q[Terms Loading]

    Q --> R[Terms View]

    R --> S[Success View]

    L --> S

    S --> T[Redirect to Ref URL]

    subgraph "Special Flows"
        U[Edit Bank Account] -.-> M
        V[Relink Bank Account] -.-> M
        W[In-store Signup] -.->|PlaidEmbeddedSearch| M
        X[Regular Signup] -.->|AggregatorWidget| M
    end
```
