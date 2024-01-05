# Vendor Management

This diagram captures a basic vendor management process.

## Diagram

An example flow chart for vendor management.

```mermaid
flowchart TD
    A[New Vendor Request];
    Z[Finance] --> A;
    Y[Internal User] --> A;
    X[Periodic Review of Payments] --> A;
    W[Legal] --> A;

    A --> B{Data Tier};
    B -- Tier 3 --> C[Track and Approve - Low Impact];
    B -- Tier 1,2 --> D[Track and Review];
    D --> E{Strong Audit};
    E -- No --> F[Objections Identified];
    E -- Yes --> G{Sells / Shares Data};
    G -- Yes --> F;
    G -- No --> H{Strong Questionnaire};
    H -- No --> F;
    H -- Yes --> I{SubProcessor};
    I -- No --> $[Approved];
    I -- Yes --> J{Strong Pentest};
    J -- No --> F;
    J -- Yes --> $;
    E -- No but hungry --> !;
    ![Put Them On A Program];
    ! -- In 3 months --> A;
    F -- In 3 months --> A;
```

### Disclaimer

*You should consult a security expert directly about any decisions about vendor management program.*
