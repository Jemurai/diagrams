# Incident Response

This diagram captures a core incident response workflow.

## Diagram

An example flow chart for incident response.

```mermaid
flowchart TD
    Z[Support] --> A;
    Y[Customer] --> A;
    X[Hacker] --> A;
    W[Security Team] --> A;
    V[Law Enforcement] --> A;

    A[A Security Event Is Detected] --> B[Initial Triage];
    B --> C{Is it real};

    C -- No it is not real --> D[Track Event];
    D --> CloseEvent --> Improve;
    
    C -- Yes, further investigation --> E[Response Team - Investigate];
    E -- Investigate, Collect Evidence --> C;
    C -- Yes, understood --> F[Track, Complete Tech Writeup];
    
    F --> G[Management Response];
    G --> H{Impact};
    H -- Legal --> Comms;
    H -- Customer Data --> Comms;
    H -- Internal Data --> Comms;
    Comms -- If Applicable --> I[Cyberinsurance];
    Comms -- If applicable --> J[Law Enforcement];
    Comms -- If applicable --> K[Customer Notifications];
    Comms --> L[Board Communications];
    Comms -- If Applicable --> M[Disclosure and Reporting];

    Writeup[Complete Writeup];
    I --> Writeup;
    J --> Writeup;
    K --> Writeup;
    M --> Writeup;
    % --> CloseIncident;
    H -- None --> Writeup;
    CloseIncident --> Improve;

    Comms[Communications Plan];

    Improve[Improve Processes If Possible]
    CloseIncident[Close as Incident]
    CloseEvent[Close as Event without Incident]
```

### Notes

Ideally, we want as many ways for a potential security event to be reported
as possible.  This could be your security@ email address, it could be a
phone number, it could be a slack channel.  Basically, we want the bar for
having a security incident reported to be as low as possible.

Typically, _Initial Triage_ is done by someone on the security or
operations team.  There is usually a lot of noise.  The noise comes mostly
from tools not people, but because there is noise, we need to triage these
security items before making them a fire drill.

Once we know it may be real, we want to convene a security incident response
team (often called a SIRT).  The SIRT should be tailored to the incident.
That means the tech people pulled should be the ones that can help
investigate.  The business folks should be appropriate to the product and
customers impacted.  Generally, we don't want the information about the
incident to be circulated more widely than necessary.  This is a good place
for the "need to know basis" type of arrangement.  The SIRT may need to be
updated as information about the incident becomes known.

### Communication Plan

We may also have to think about how we communicate
about an incident.  This is an example.  Every company will vary.

```mermaid
flowchart TD
    A[Incident Communications];
    A --> ![Customer] --> B{Customer Impacted};
    B -- Yes --> C[Communications Based On Incident Detail];
    B -- No --> D[Handle Internally];
    C -- Known Impact --> E[Notification with Detail];
    C -- Unknown Impact --> F{Likelihood};
    F -- High --> E;
    F -- Low --> G[Do not notify];
    G --> D;

    A --> L[Law Enforcement];

    A --> Y[Insurance];
    Y --> X{Large Loss} -- Yes --> C;
    X -- No --> B;

    A --> Z[Public];
    Z --> B;

    A --> W[Board];
    W --> U[Yes];
```

### Ransoms

We may also have to ask ourselves whether we will pay a ransom?

```mermaid
flowchart TD
    A[Ransom Requested];
    A --> B{Impact};
    B -- Large --> C[Consider Paying];
    B -- Small to Moderate --> D[Do Not Pay];
    B -- Philosophical / Legal Opposition --> D;
    
    C --> E[Assess Likelihood of Paying Leading To Remediation];
    E --> F[Identify Vehicle];
    F --> G[Pay];
    G --> !;

    D --> !;
    ![Fix Holes Fast]
```

### Disclaimer

*You should consult a security expert directly about any decisions about security response.*
