Bharat-Guard-Anti-Infiltration-in-Kashmir
Bharat Guard: A tactical AI system on Databricks securing 75 border sectors. It fuses real-time weather, terrain metrics, and NLP-processed OSINT. Features a Deep Learning Autoencoder for anomaly detection, identifying high-risk infiltration and environmental threats in J&K by correlating sensor data with AI-extracted intelligence.

What it does:
Bharat Guard is a tactical intelligence platform that monitors 75 hexagonal border sectors by fusing real-time environmental sensors with AI-processed news alerts. It uses a Deep Learning Autoencoder to detect security and terrain anomalies, providing a unified risk score for border surveillance.

graph LR
    %% THEORETICAL STEPS
    Input[Multimodal Inputs <br/> Terrain + Satellite + Weather]
    Fusion[Geospatial <br/> Feature Fusion]
    Latent[Latent Space <br/> Compression]
    Recon[Reconstruction <br/> Logic]
    Error{Error Delta}
    
    %% OUTCOMES
    Normal[Normal State]
    Anomaly[Tactical Anomaly]

    %% CONNECTORS
    Input --> Fusion
    Fusion --> Latent
    Latent --> Recon
    Recon --> Error
    
    Error -- Low --> Normal
    Error -- High --> Anomaly

    %% Styling
    style Input fill:#fff
    style Latent fill:#e1f5fe,stroke:#01579b
    style Anomaly fill:#ffebee,stroke:#c62828,color:#c62828
%% SERVING LAYER
subgraph Serving_Layer ["📊 Application & Serving Layer"]
    DBSQL[Databricks SQL Endpoints]
    Streamlit[Databricks App: Streamlit UI]
end

Gold_Delta -->|Optimized Queries| DBSQL
DBSQL -->|Feeds Dashboard| Streamlit
Gold_Delta -->|Direct Read| Streamlit

%% Styling
classDef External fill:#fff,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5;
classDef DeltaTable fill:#ffe082,stroke:#333,stroke-width:1px;
classDef AI fill:#90caf9,stroke:#333,stroke-width:2px;
classDef UC_Style fill:#f8f9fa,stroke:#00509e,stroke-width:2px,stroke-dasharray: 2 2;
classDef Serving fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;

class Topo,NASA,Weather External;
class RawTopo,RawNASA,RawWeather,CleanTopo,CleanNASA,CleanWeather,HexGrid,AnomalyScores,TacticalView DeltaTable;
class Autoencoder AI;
class UC UC_Style;
class DBSQL,Streamlit Serving;
For your theoretical architecture, you want to move away from the "coding blocks" and explain the conceptual logic of how Bharat Guard actually works. This is what you would put in a research paper or a high-level project summary.

It’s based on the "Sense-Analyze-Respond" framework, specifically using Unsupervised Learning for anomaly detection.

🛡️ Bharat Guard: Theoretical Architecture I. The Multi-Source Ingestion Layer (The Sensors) The system operates on a Multimodal Data Fusion theory. It assumes that no single data source is sufficient for border security. Instead, it correlates:

Topographical Constant: Elevation and slope data (static) that define natural infiltration corridors.

Satellite Variables: NASA spectral data (dynamic) to detect heat signatures or changes in ground cover.

Meteorological Variables: High-resolution weather data (dynamic) that affects visibility and sensor performance.

II. The Medallion Data Evolution (The Logic) We follow the Medallion Data Theory to transform raw noise into tactical intelligence:

Bronze (Raw): Preservation of historical state (immutable).

Silver (Feature Space): Normalization and Spatial Join. Here, disparate APIs are unified into a single Feature Vector representing one of the 75 tactical hexagons.

Gold (Decision Space): The final output where raw data is converted into a Threat Index (0-1).

III. The Neural Anomaly Detection Theory (The Brain) Instead of using supervised learning (which requires labeled "attack" data that is rare), Bharat Guard uses an Autoencoder Neural Network.

Encoding: The model compresses the 75-hex feature vector into a lower-dimensional Latent Space, capturing the "normal" environmental signature of the border.

Decoding: The model attempts to reconstruct the original input from this compressed state.

The Theory of Reconstruction Error: If the model receives input it has never seen before (e.g., a sudden thermal spike in a high-slope area during a fog event), it will fail to reconstruct it accurately. This High Reconstruction Error is theoretically defined as a Tactical Anomaly.

IV. The Governance & Serving Theory (The Interface) The architecture is wrapped in Unity Catalog, which ensures Data Lineage—meaning every threat score in the Gold layer can be traced back to the exact NASA or Weather packet that triggered it. This provides "Explainable AI" for tactical commanders.

graph LR A[Multimodal Input] --> B{Feature Fusion} B --> C[Autoencoder Bottleneck] C --> D[Reconstruction Logic] D --> E{Error Delta Check} E -- Low Error --> F[Normal Operations] E -- High Error --> G[Tactical Anomaly Alert] G --> H[Streamlit Decision Interface]
    B --> C[Autoencoder Bottleneck]
    C --> D[Reconstruction Logic]
    D --> E{Error Delta Check}
    E -- Low Error --> F[Normal Operations]
    E -- High Error --> G[Tactical Anomaly Alert]
    G --> H[Streamlit Decision Interface]
