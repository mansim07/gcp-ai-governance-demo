```mermaid
    graph TD
        subgraph Customer
            A[1. Identify Need for Feature/Enhancement] --> B(2. Document Technical Requirements <br/>• Description<br/>• Use Cases<br/>• Specs<br/>• Impact<br/>• Metrics (Opt.));
            B --> C(3. Define Priority & Severity <br/>• P0-P3 / Amex 0-4);
            C --> D[4. Submit Request & Docs];
        end
    
        subgraph Customer Cloud Eng/Platform Eng Team
            style CET fill:#f9f,stroke:#333,stroke-width:2px
            D -- To Cloud Eng Team --> E[Receive & Refine Request];
            E --> F[Submit to GCP];
            M[Receive Status Updates] --> N[Relay Updates to Customer Owner/Contact];
        end
    
        subgraph GCP
            style GCP fill:#ccf,stroke:#333,stroke-width:2px
            F --> G[Receive Feature Request];
            G -- Ownership Assignment --> H(5. Assign GCP Owner);
            H --> I[6. Acknowledge Receipt <br/>(within 1-2 biz days)];
            I --> J[7. File Formal Requirement Internally <br/>(incl. docs, priority)];
            J --> K[Advocate & Align with Internal Processes];
            K --> L{8. Status Verification & Updates <br/>(Frequency based on Priority*)};
        end
    
        subgraph Shared Tracking / Communication
            style ST fill:#eee,stroke:#999,stroke-width:1px
            L -- Updates Logged --> O[Log Update in Central Location <br/>(e.g., Confluent, Shared System)];
            L -- Updates Communicated --> M;
        end
    
        subgraph "(*) Update Frequency Note"
```
           Note["• P0/Amex 0: Weekly<br/>• P1: Monthly / Amex 1: Bi-Weekly<br/>• P2/P3: Quarterly / Amex 2-3: Monthly<br/>• Amex 4: Quarterly"];
           style Note stroke-width:0px,fill:#fff
        end
    
    %% Styling nodes for clarity (Optional)
    classDef customer fill:#D6EAF8,stroke:#5DADE2;
    classDef cet fill:#EBDEF0,stroke:#A569BD;
    classDef gcp fill:#D5F5E3,stroke:#58D68D;
    classDef shared fill:#FEF9E7,stroke:#F4D03F;
    
    class A,B,C,D customer;
    class E,F,M,N cet;
    class G,H,I,J,K,L gcp;
    class O shared;
