# -Dark-web-threat-actor-de-anonymization

  RESEARCH PAPER
A Privacy-Preserving Framework for Dark Web Threat Actor De-anonymization Using Blockchain and 
Multi-Modal Cyber Intelligence
SIH Problem Statement: SIH26151
Theme: Blockchain & Cybersecurity
Organization: National Technical Research Organisation (NTRO)
Team Leader: Padma Sri S
Team Members: Karthika K N • Manuja K • Parkavi S • Kaviya Sri C
Research Paper Draft — Editable Academic Version
Important: Numerical experimental results are placeholders and must be replaced with measurements from 
the team's implementation and approved datasets.
Abstract
Dark-web ecosystems enable anonymous or pseudonymous communication and transactions, creating 
challenges for cyber-threat intelligence, digital investigation, and threat-actor attribution. A single actor may 
operate through multiple aliases, accounts, wallets, services, and infrastructure components, making isolated 
analysis insufficient for reliable correlation. This paper proposes a framework for dark-web threat actor de
anonymization that combines multi-modal cyber intelligence, entity resolution, behavioural analysis, 
relationship graphs, and blockchain-based evidence integrity. Blockchain is used as an integrity and 
provenance layer rather than as a mechanism for exposing private identities. The architecture includes 
intelligence acquisition, preprocessing, entity extraction, cross-source correlation, confidence estimation, 
evidence hashing, graph construction, and investigator visualization. The framework defines an evaluation 
methodology based on precision, recall, F1-score, false-positive rate, processing time, and evidence
verification success. The approach is intended to support lawful cyber investigations and analyst decision
making while reducing unsupported attribution.
Keywords: Dark Web, Threat Actor Attribution, De-anonymization, Blockchain, Cyber Threat Intelligence, 
Entity Resolution, Digital Forensics, Evidence Integrity
1. Introduction
The dark web consists of services and communities that are not ordinarily indexed by conventional search 
engines and may be accessed through privacy-oriented networks. Although these technologies have legitimate 
uses, dark-web ecosystems are also associated with cybercrime, illicit marketplaces, credential trading, 
malware distribution, fraud, and other security threats. Investigators therefore require methods for discovering 
relationships among apparently unrelated online identities and technical artefacts.
A central challenge is that threat actors can separate activities across pseudonyms, forums, marketplaces, 
cryptocurrency addresses, email identifiers, public keys, domains, servers, and other infrastructure. Individual 
observations may be weak signals; combinations of independent signals can provide stronger evidence for an 
investigative hypothesis. This motivates a multi-modal correlation approach.
This work addresses SIH26151, 'Dark web threat actor de-anonymization', under the Blockchain & 
Cybersecurity theme. The framework treats attribution as a hypothesis-generation and evidence-correlation 
task, not as a single automated claim of real-world identity.
2. Problem Statement
Design a system capable of assisting investigators in correlating fragmented dark-web threat intelligence to 
identify potentially related threat-actor identities, activities, and infrastructure, while maintaining verifiable 
evidence provenance and integrity.
2.1 Research Questions
 RQ1: Can heterogeneous dark-web intelligence be normalized into a common entity and relationship 
representation?
 RQ2: Can multi-modal correlation improve identification of related pseudonymous entities compared with 
isolated-source analysis?
 RQ3: Can blockchain-based hashing and provenance records provide verifiable evidence integrity without 
storing sensitive raw evidence on-chain?
 RQ4: How should uncertainty and false-positive risk be represented to prevent unsupported attribution?
3. Objectives
 Develop a modular pipeline for legally obtained or approved cyber-intelligence data.
 Extract and normalize aliases, identifiers, domains, infrastructure references, public keys and other 
appropriate indicators.
 Correlate entities using explainable relationships and behavioural signals.
 Represent relationships through an intelligence graph for analyst investigation.
 Use cryptographic hashing and blockchain anchoring for tamper-evident evidence provenance.
 Evaluate the framework using approved datasets and reproducible metrics.
 Provide confidence indicators and supporting evidence for human review rather than an automated identity 
verdict.
4. Related Work and Research Gap
Cyber-threat intelligence systems commonly use indicators of compromise, entity extraction, graph analysis, 
malware intelligence and reputation data. Digital-forensics systems emphasize evidence preservation and chain 
of custody, while blockchain systems can provide append-only records and cryptographic verification. These 
capabilities are often implemented separately.
The proposed research integrates multi-modal dark-web intelligence correlation with an evidence-integrity 
layer and analyst-oriented relationship graph. It explicitly separates observed facts from inferred relationships.
4.1 Research Gap
 Fragmented evidence is difficult to correlate across heterogeneous sources.
 Naive username or keyword matching can generate false positives.
 Evidence provenance may be separated from the intelligence workflow.
 Black-box attribution can make it difficult to understand why two entities were linked.
 Sensitive raw evidence should not automatically be placed on a public or shared blockchain.
5. Proposed Methodology
The framework follows a staged architecture: data acquisition, preprocessing, entity extraction, normalization, 
correlation, graph construction, confidence estimation, evidence integrity, and analyst visualization.
5.1 Data Acquisition
The prototype should operate only on data the team is authorized to collect, access or use. Controlled, 
synthetic, public research, or institutionally approved datasets can be used for evaluation.
5.2 Preprocessing and Entity Extraction
Records are normalized into structured objects. Candidate entities may include pseudonyms, account 
identifiers, domains, public keys, wallet identifiers, timestamps, infrastructure references, and textual or 
behavioural features.
5.3 Entity Resolution
Candidate entities are compared using multiple features rather than a single identifier. Exact and approximate 
matching, temporal overlap, shared technical indicators, linguistic similarity and infrastructure reuse can be 
represented as weighted relationships. Each relationship retains its supporting evidence and confidence.
5.4 Behavioural Correlation
Behavioural features may include posting intervals, activity windows, vocabulary characteristics, recurring 
operational patterns and cross-platform timing. These are probabilistic signals and should not be interpreted as 
proof of a person's identity.
5.5 Intelligence Graph
Entities are represented as nodes and observed relationships as edges. Each edge can contain source, 
timestamp, evidence reference, relationship type and confidence, enabling analysts to explore clusters and 
bridge entities.
5.6 Blockchain Evidence Layer
Instead of storing raw investigative material on-chain, the framework can calculate a cryptographic hash of an 
evidence package and record a minimal provenance entry. The original evidence remains in controlled storage. 
Later, re-hashing and comparison with the recorded value can detect modification.
5.7 Confidence and Human Review
The system should distinguish observed facts from inferred relationships. A confidence score may summarize 
signal strength, while the interface exposes the individual supporting signals. Analysts can accept, reject or 
annotate relationships.
6. System Architecture
Dark-Web / Approved Intelligence Sources → Data Acquisition → Preprocessing → Entity Extraction 
→ Entity Resolution → Behavioural & Technical Correlation → Intelligence Graph → Confidence & 
Analyst Review → Blockchain Evidence Integrity → Investigator Dashboard
Figure 1. Proposed architecture. Replace this text representation with a polished architecture diagram in the 
final paper.
7. Blockchain Design
Blockchain is positioned as an integrity and provenance mechanism. A permissioned blockchain or controlled 
distributed ledger may be appropriate when investigation records are shared among authorized organizations. 
The design should minimize on-chain data and avoid publishing sensitive raw evidence.
7.1 Evidence Record
 Evidence ID
 Cryptographic hash of the evidence package
 Timestamp
 Source/provenance reference
 Investigation or case identifier
 Verification status
 Authorized analyst or system identifier, where appropriate
7.2 Integrity Verification
At verification time, the stored evidence is hashed using the approved cryptographic function. If the calculated 
hash matches the recorded hash, the system can establish that the referenced artifact has not changed since the 
recorded integrity event. This does not independently establish that the underlying evidence is truthful.
8. Threat Model and Security Considerations
 Adversarial actors may create misleading identities or relationships.
 Public identifiers may be reused by unrelated users, creating false correlations.
 Collected data may be incomplete, stale, manipulated or incorrectly attributed.
 Analyst interfaces may expose sensitive information and require authentication, authorization and audit 
logging.
 Blockchain records are difficult to alter, so incorrect data should not be committed without validation.
 Automated correlation should be treated as an investigative lead unless supported by sufficient 
independent evidence and lawful procedures.
9. Experimental Evaluation
This section must be completed using the team's actual implementation and approved evaluation data. 
Numerical claims should not be inserted without measurement.
9.1 Evaluation Metrics
 Precision: correctly resolved relationships divided by all relationships predicted.
 Recall: correctly resolved relationships divided by all relevant relationships in the evaluation ground truth.
 F1-score: harmonic mean of precision and recall.
 False-positive rate: incorrectly generated relationships relative to selected negative cases.
 Processing time: elapsed time for a defined dataset and pipeline configuration.
 Evidence verification success: proportion of unchanged test artifacts correctly verified after integrity 
recording.
9.2 Results Table — To Be Filled
Metric
Baseline
Proposed System
Observation
Precision
[Measure]
[Measure]
[Describe]
Recall
[Measure]
[Measure]
[Describe]
F1-score
[Measure]
[Measure]
[Describe]
False-positive rate
[Measure]
[Measure]
[Describe]
Processing time
[Measure]
[Measure]
[Describe]
Evidence verification
[Measure]
[Measure]
[Describe]
10. Expected Contributions
 Unified multi-modal framework for correlating dark-web threat intelligence.
 Explainable entity-resolution and relationship-graph model.
 Blockchain-backed evidence-integrity mechanism with minimal sensitive on-chain storage.
 Analyst-centric workflow separating observations, inferred relationships and confidence.
 Reproducible evaluation methodology for attribution-support capabilities.
11. Limitations
 Dark-web data can be incomplete, transient, inaccessible or deliberately deceptive.
 Behavioural and linguistic similarity can produce false positives.
 Blockchain integrity does not guarantee the truthfulness of the underlying evidence.
 Automated correlation should not be treated as definitive real-world identity attribution.
 Evaluation quality depends on the availability and quality of ground-truth data.
12. Ethical, Legal and Privacy Considerations
The research should be conducted only within applicable law, institutional authorization and approved 
cybersecurity research procedures. The system should minimize personal data, use controlled access, maintain 
audit logs and avoid unnecessary exposure of sensitive information. Real-world deployment should include 
legal review, human oversight and procedures for correcting erroneous correlations.
13. Future Work
 Evaluate graph-based machine-learning methods for entity resolution.
 Investigate privacy-preserving collaboration between authorized organizations.
 Develop stronger provenance standards and permissioned-ledger integration.
 Add explainable visual analytics for relationship confidence.
 Benchmark against multiple controlled datasets and adversarial test cases.
 Study robustness against identity mimicry, misleading indicators and data poisoning.
14. Conclusion
This paper proposes a research framework for assisting dark-web threat actor de-anonymization through multi
modal cyber intelligence correlation and blockchain-supported evidence integrity. The central principle is that 
de-anonymization should be treated as an evidence-correlation problem with uncertainty rather than as a single 
automated identity decision. Combining entity resolution, behavioural and technical signals, intelligence 
graphs, confidence-aware analysis and tamper-evident provenance can provide investigators with a structured 
basis for reviewing potential relationships. Experimental validation should quantify precision, recall, false
positive behaviour, computational cost and evidence-verification performance using authorized datasets.
References — Initial Reading List
 European Union Agency for Cybersecurity (ENISA), guidance and reports on cyber threat intelligence and 
incident response.
 National Institute of Standards and Technology (NIST), guidance on digital forensics, cybersecurity and 
blockchain-related technologies.
 ISO/IEC 27037, Guidelines for identification, collection, acquisition and preservation of digital evidence.
 ISO/IEC 27042, Guidelines for the analysis and interpretation of digital evidence.
 Tor Project, technical documentation describing the Tor network and onion services.
 Academic literature on entity resolution, authorship attribution, graph-based threat intelligence and cyber 
attribution should be added after a systematic literature search.
Appendix A — Suggested Figures
 Figure 1: End-to-end system architecture.
 Figure 2: Threat-actor intelligence graph.
 Figure 3: Entity-resolution workflow.
 Figure 4: Blockchain evidence-provenance workflow.
 Figure 5: Investigator dashboard.
 Figure 6: Experimental precision/recall comparison.
 Figure 7: Evidence verification test results.
Scan to Open the Research Paper
Use your phone camera or QR scanner
Google Docs link
