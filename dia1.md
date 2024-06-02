```mermaid
graph TD;
    subgraph Microservices
        A[Service A] -->|reads/writes| DB_A[(Database A)];
        B[Service B] -->|reads/writes| DB_B[(Database B)];
        C[Service C] -->|reads/writes| DB_C[(Database C)];
        A -->|API Calls| B;
        B -->|API Calls| C;
        C -->|API Calls| A;
    end
    subgraph Clients
        UI[User Interface] -->|REST/gRPC| A;
        UI -->|REST/gRPC| B;
        UI -->|REST/gRPC| C;
    end
