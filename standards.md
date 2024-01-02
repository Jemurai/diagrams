# Standards

Understanding security standards is very difficult.  This diagram and the following information is intended to make it easier to follow.

## Diagram

A flow chart for understanding security standards.

```mermaid
flowchart TD
    A[You are thinking about a standard] --> B{For what?};
    B -- Customer is asking --> C{Are you?};
    B -- I just want great security and higher cost is ok --> D{Healthcare?};
    D -- Yes --> E[HITRUST];
    D -- No --> F[NIST 800-53];
    C -- Customer specifies standard --> G{Is it worth it?};
    G -- Yes, revenue justifies --> H[Do the standard];
    G -- No, not worth it --> M[Tell them and do alternative];
    M --> I;
    C -- < 250 people --> I[Consider NIST CSF or 800-53 maybe with securityprogram.io];
    C -- < 1,000 people --> J[Use NIST 800-53 and do SOC 2];
    C -- < 1,000 people with international --> K[ISO 27001];
    C -- > 1,000 --> L[Hire people, Do SOC 2, ISO 27001, +others]
```

### Disclaimer

*You should consult a security expert diretly about any decisions about security standards.*
Check out our securityprogram.io tool if you want simple help.

## Associations

```mermaid
flowchart LR
    Z[SOC 2 Type 2];
    Y[ISO 27001];
    X[FedRAMP];
    W[NIST 800-171];
    V[HITRUST];
    U[NIST CSF];
    R[CMMC Level 1 or 2];
    Q[Everything eg. SOC 2, ISO 27001];
    P[SEC Rules];
    O[Everything Applicable];

    A[Small EdTech];
    B[Small HealthTech];
    C[Small FinTech/LegalTech/InsuranceTech];
    D[Small Manufacturer/DoD Supply Chain];

    E[Mid Sized Tech Company with EU Customers];
    F[Mid Sized Health];
    G[Mid Sized DoD];
    H[Mid Sized Ed, Health, Fin, Legal, Insure Tech];

    L[Public Companies];
    M[Large with Gov Agency Contracts In Hand];
    
    A --> U;
    B --> Z;
    C --> Z;
    D --> R;

    E --> Z;
    E --> Y;

    F --> V;
    F --> Z;
   
    G --> R;
    G --> W;

    H --> Z;
    H --> Y;

    M --> X;
    M --> Q;

    L --> P;
    L --> O;
```

Note:  privacy and other core legal framework (FTC rules,
executive orders, etc.) are not included here because it 
makes the diagram unreadable.

## Explanations

There are some standards that you can leverage that are free
and open that support long term development of a security
program.  These include:

* NIST 800-53
* NIST CSF

There are other specific standards with affinities as
follows:

* CMMC is new and for DoD
* NIST 800-171 is for DoD
* SOC 2 Type 2 is widely used in US
* ISO 27001 is an international standard
* HITRUST is an adaptation of these with a closed community of auditors.  It is widely applied in healthcare, largely because HIPAA is very non-specific.

There is a lot of detail behind any of these choices and
there is probably no "one right" decision for all companies.

## References

These change a lot.