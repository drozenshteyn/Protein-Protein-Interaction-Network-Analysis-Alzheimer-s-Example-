# Protein-Protein-Interaction-Network-Analysis-Alzheimer-s-Example-
This project demonstrates a practical workflow for analyzing protein–protein interaction (PPI) networks using publicly available bioinformatics databases and Python tools.

As a case study, I used Alzheimer’s disease–associated proteins to:

construct a PPI network

identify key hub proteins

detect functional modules using network analysis

visualize biologically meaningful patterns

👉 The goal of this project is to practice and demonstrate bioinformatics and data analysis skills, including working with real biological datasets, rather than to conduct novel Alzheimer’s research.

🚀 Interactive visualization (Tableau) : https://public.tableau.com/app/profile/diana.rozenshteyn/viz/ppi_network_analysis_dashboard/Dashboard1

🧪 Data Sources

UniProt – protein search and annotation

STRING – protein–protein interaction data

🔍 Data Collection Workflow

1️⃣ Selecting seed proteins (UniProt)

To define a biologically relevant starting point:

Searched UniProt using keywords:
“Alzheimer’s disease”

Filtered results:
Organism: Homo sapiens (Human), 
Reviewed entries (Swiss-Prot only)

👉 From these results, I selected well-established Alzheimer’s-associated proteins:

APP

PSEN1

PSEN2

MAPT

APOE

BACE1

GSK3B

CDK5

These proteins represent key biological processes:

amyloid-beta production

tau phosphorylation

neuronal signaling

2️⃣ Expanding the network (STRING)

Using STRING:

Entered the seed proteins

Set parameters:

Organism: Homo sapiens (9606),
Confidence score ≥ 0.7 (high confidence),
Enabled first-shell interactors,
Added ~20 additional proteins

👉 This step expands the network using known and predicted protein interactions.

3️⃣ Exporting data from STRING

Downloaded:

TSV interaction file
Contains:
node1_string_id, node2_string_id, 
combined_score (interaction confidence)

Protein annotation file: 
Maps STRING IDs → gene/protein names


⚙️ Methods

Network Construction,
Built graph using Python (networkx):

Nodes = proteins

Edges = interactions

Edge weight = STRING combined_score

Network Analysis

🔹 Degree centrality (hub detection)

Identified proteins with the most connections

Highlights biologically important regulators

🔹 Community detection (unsupervised clustering)

Used modularity-based clustering

Groups proteins based on interaction density

👉 Important:
This method does not use biological labels—it relies purely on network structure.

🔹 High-confidence interaction filtering

Examined edges with high STRING scores (e.g., > 0.8–0.9)

Focuses on the most reliable interactions

🔹 Shortest path analysis

Explored connections between key proteins (e.g., APP ↔ MAPT)

Helps identify indirect relationships between pathways

📊 Visualization

Node size = degree (importance)

Node color:

Pathway-based (amyloid / tau / other)

OR data-driven clusters (community detection)

Layout = force-directed (spring layout)

🔬 Key Results & Interpretation

1️⃣ Hub proteins

APP identified as the strongest hub

Other hubs include:

GSK3B

MAPT

PSEN1

👉 Interpretation:
These proteins are central regulators in the network and align with known Alzheimer’s biology.

2️⃣ Pathway structure (manual labeling)

The network shows clear biological organization:

🔴 Amyloid processing cluster

APP, BACE1, PSEN1, PSEN2

🔵 Tau-related cluster

MAPT, GSK3B, CDK5

👉 These clusters reflect known disease mechanisms:

amyloid plaque formation

tau phosphorylation

3️⃣ Community detection (data-driven insight)

Unsupervised clustering revealed:

distinct modules corresponding to:

amyloid pathway

tau signaling

additional supporting clusters

👉 Key insight:

The network structure alone is sufficient to recover known biological pathways.

4️⃣ Cross-talk between pathways

Proteins such as APOE appear between clusters:

👉 Interpretation:

may act as connectors between biological processes

suggests interaction between amyloid and tau pathways

5️⃣ High-confidence interactions

Filtering by STRING score highlights:

strongest, most reliable protein interactions

core biological relationships within the network

6️⃣ Shortest path analysis

Paths between key proteins (e.g., APP → MAPT):

👉 Suggest:

indirect regulatory or signaling relationships

potential biological cross-talk

🧠 Key Takeaways
Network analysis can reveal biologically meaningful structure

Hub proteins often correspond to key regulators

Community detection can uncover functional modules without prior knowledge

Public databases enable rapid construction of biologically relevant models

🛠️ Technologies Used

Python

pandas

networkx

matplotlib

STRING database

UniProt database

Tableau
