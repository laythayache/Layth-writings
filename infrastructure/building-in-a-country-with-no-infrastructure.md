



I’m sure we’re all familiar with the phrase “lack of infrastructure” in Lebanon. We repeat it casually — about electricity, about the internet, about public systems — until it becomes background noise.

But what does that actually mean when you try to build something technical inside that environment?

Growing up in Lebanon, you get used to the chaos: the stable instability. It’s part of what makes Lebanese people resilient. But I was seriously taken off guard by something I didn’t expect: the lack of unification of sign language in Lebanon — multiple schools teaching different lexicons to people who already suffer enough when it comes to communication.

The reason for this can be traced to multiple factors: the Lebanese Civil War (1975–1990), the ongoing tension between ArSL (Standard Arabic Sign Language) and Lebanese Sign Language (LSL), and the way institutions in Lebanon remain fragmented and inconsistent.

Fragmentation is Structural
The fragmentation of language is not an isolated issue. It mirrors a broader national pattern.

Lebanon’s electricity sector has collapsed into a low-hours-per-day service since 2021, with documented periods where state electricity dropped to roughly 1–3 hours per day, and even a nationwide blackout in August 2024 when Electricité du Liban ran out of fuel.

Its fiber-optic rollout, launched in 2018 and intended to finish by 2022, reportedly reached only around 25% completion by mid-2023 before being relaunched again.

Lebanon ranks 180th globally in the Open Data Inventory 2024/2025, with a score of 33/100.

Even the official Digital Transformation Strategy acknowledges fragmented governance, siloed institutions, and inconsistent digital assurance.

In other words: fragmentation is structural.

We Thought the Hard Part Was Accuracy
When we started exploring the idea of building a sign language interpreter, we assumed the main challenge would be model accuracy.

It wasn’t.

The first problem was definition.

Although initiatives existed — documentation efforts in 2006 supported by UNESCO and academic work by figures like Professor Roumanos and Dr. Hussein Ismail — there was still no unified, machine-readable digital corpus for Lebanese Sign Language.

The language existed socially.

But not digitally.

And if something doesn’t exist digitally, it doesn’t exist to AI.

Stable Ecosystems Start With Data. We Didn’t Have That.
In stable ecosystems, you start with data:

you benchmark against existing corpora

you fine-tune pretrained models

you optimize

In Lebanon, we had to start with:

collection

annotation

structuring

defining boundaries

deciding what “standard” even meant in a fragmented environment

Before we could train a model, we had to construct the ground it would stand on.

Infrastructure Becomes an Engineering Variable
And the dataset problem was only the first layer.

Building in Lebanon forces you to treat infrastructure as an engineering variable.

You cannot assume stable electricity. Since 2021, households have reported median state electricity availability of around two hours per day. That means data collection sessions get interrupted. Upload pipelines fail. Annotation workflows pause mid-label.

You cannot assume reliable connectivity. Telecom rollouts stall. Coverage is uneven. Cloud dependency becomes a liability, not an optimization.

You cannot assume institutional continuity. Lebanon’s digital government history shows repeated strategy cycles since 1997 — ICT committees, e-government frameworks, digital transformation plans — but recurring implementation breakdowns linked to isolated governance and reform fatigue.

“Real-time” stops being a benchmark number and becomes an operational question:

What happens when the internet drops?

What happens when power cuts mid-session?

So the architecture itself had to reflect that reality.

Cloud-heavy inference made little sense in an environment where connectivity is fragile. Centralized video collection raises privacy concerns in a country where cybersecurity capacity ranks relatively low internationally.

We needed something that could function locally, independently, and predictably.

That meant:

on-device inference

minimizing latency not just for performance, but for resilience

designing for failure as a default condition, not an edge case


OmniSign
That’s how OmniSign started — what began as a final-year project became an MVP built under infrastructural constraint.

My teammates and I spent four months traveling across the country, working with different schools and communities, trying to identify common, agreed-upon signs to create what did not exist before: a structured Lebanese Sign Language dataset.

We weren’t just building a model.

We were building missing infrastructure.

What “Infrastructure” Means Here
In this context, infrastructure means:

A dataset (open to community use — contact us to contribute or access)

A labeling governance framework (contact us for training / standardization guidance)

A signer-consent protocol

A distribution pipeline

Next: a dialect reconciliation methodology
(If you’re a community admin, scholar, or teacher in this domain — please reach out.)

Results
Target latency

Under 100ms end-to-end latency using edge computing.

Dataset size

50,000+ raw signs collected through nationwide campaigns

80,000+ processed samples after cleaning and augmentation

Coverage: full Arabic alphabet + 30+ daily words and expressions

Number of signers

Learn about Medium’s values
117 unique signers, from the age range of 6–73 years old (mixed gender representation) collected across multiple communities through:

Aaramoun Orphanage Center

Sin El Fil Church

SignWithNaila community

Rafik Hariri University campus events

Model class

LSTM-based temporal model

MediaPipe-style landmark pipeline (gesture landmarks feeding the temporal classifier)

Latency tradeoffs (not “compression”)

On-device inference prioritized

Model optimized for low-latency responsiveness over scale

Accuracy metrics

98% accuracy under internal evaluation (controlled conditions)

Real-world performance varies depending on lighting, signer variation, and environmental conditions

Evaluation method

Data split: 80/20 train–test split at the sequence level
Signer-aware split: Test samples included sequences from signers not seen during training where possible
Classes evaluated: Full Arabic alphabet + 30+ daily expressions
Metric: Top-1 classification accuracy

For more information about the project:
https://laythayache.com/projects/omnisign
For contact Info reach out to:
laythayache5@gmail.com

References:
1. Human Rights Watch (2024)—Nationwide Electricity Blackout
https://www.hrw.org/news/2024/08/29/lebanon-nationwide-electricity-blackout

Documents the August 17, 2024 nationwide power outage after Electricité du Liban ran out of fuel.
Used to illustrate infrastructure fragility and systemic dependence on generators.

2. Human Rights Watch (2023) — “Cut Off From Life Itself”
https://www.hrw.org/report/2023/03/09/cut-life-itself/lebanons-failure-right-electricity

Reports that since 2021, state electricity provision has dropped to roughly 1–3 hours per day, with median availability around two hours daily in late 2021–early 2022.
Supports claims about instability affecting engineering workflows.

3. OMSAR — Lebanon Digital Transformation Strategy (Approved 2022)
https://omsar.gov.lb/Assets/DT_EN.pdf

Official government strategy outlining Lebanon’s digital transformation timeline (1997–2022), governance structure, open data goals, and implementation challenges.
Provides institutional grounding for fragmentation and “reform fatigue.”

4. OECD (2020) — Digital Government in Lebanon
https://www.oecd.org/en/publications/digital-government-in-lebanon_a711b0c1-en.html

Analyzes governance silos, policy fragmentation, and implementation barriers in Lebanese digital reform.
Used to support structural critique of institutional discontinuity.

5. L’Orient Today (2025) — Fiber Optic Rollout Relaunched
https://today.lorientlejour.com/article/1485023/fiber-optic-internet-rollout-relaunched-in-lebanon.html

Reports that Lebanon’s fiber rollout, launched in 2018 and planned for completion by 2022, had reached only ~25% of its targets by mid-2023 before being relaunched.
Supports claims about connectivity fragility.

6. Open Data Inventory (ODIN) 2024/2025 — Lebanon Country Report
https://odin.opendatawatch.com/Report/countryProfile/LBN?year=2024

Ranks Lebanon 180th globally with a score of 33/100 in open data maturity.
Supports claim that public datasets and digital baselines are structurally weak.

7. ITU Global Cybersecurity Index (2020 Results, published 2021)
https://www.itu.int/dms_pub/itu-d/opb/str/D-STR-GCI.01-2021-PDF-E.pdf

Lists Lebanon with a score of 30.44 and rank 109 globally in cybersecurity readiness.
Used to justify privacy-by-design and caution around centralized video storage.

8. Law 220/2000 — Rights of People with Disabilities Act
WHO MiNDbank Repository
https://extranet.who.int/mindbank/item/6255

Lebanon’s primary legal framework guaranteeing rights for people with disabilities.
Provides legal foundation for accessibility claims.

9. ARTICLE 19 (2015) — Disability and Access to Information in Lebanon
https://www.article19.org/resources/lebanon-disability-access-information/

Examines the gap between disability rights frameworks and real-world information access.
Supports argument that legal recognition does not equal functional accessibility.

10. PubMed (2025) — Study on Deaf Individuals’ Access to Healthcare in Lebanon
https://pubmed.ncbi.nlm.nih.gov/40543229/

Qualitative research documenting interpreter scarcity, communication barriers, and healthcare access challenges for Deaf individuals.
Supports need for clinical vocabulary and real-world deployment.

11. Tele Liban (2024) — Launch of Sign-Language News Bulletin
https://today.lorientlejour.com/article/1414282/tele-liban-launches-news-bulletin-in-sign-language.html

Reports the introduction of sign-language news interpretation in Lebanon.
Shows bounded accessibility pilots exist but remain limited in scope.

12. Microsoft Research (2023) — ASL Citizen Dataset
https://www.microsoft.com/en-us/research/publication/asl-citizen-a-community-sourced-dataset-for-advancing-isolated-sign-language-recognition/

Community-sourced American Sign Language dataset with 83,000+ videos.
Used to show that dataset construction from scratch is standard in sign-language AI.

13. MS-ASL Dataset (Microsoft Research)
https://www.microsoft.com/en-us/research/publication/ms-asl-a-large-scale-data-set-and-benchmark-for-understanding-american-sign-language/

Large-scale ASL dataset emphasizing signer diversity and real-world conditions.
Supports argument that data is the global bottleneck in sign-language AI.

14. WLASL Dataset (WACV 2020)
https://openaccess.thecvf.com/content_WACV_2020/html/Li_Word-level_Deep_Sign_Language_Recognition_from_Video_A_New_Large-scale_WACV_2020_paper.html

Word-level large-scale sign dataset built due to lack of sufficient prior corpora.
Supports dataset-first architecture argument.

15. Google Research (2019) — MediaPipe On-Device Hand Tracking
https://research.google/blog/on-device-real-time-hand-tracking-with-mediapipe/

Describes real-time hand tracking implemented for on-device use.
Supports landmark-based, edge-compute architecture decisions.

16. McMahan et al. (2017) — Federated Learning (FedAvg)
https://proceedings.mlr.press/v54/mcmahan17a.html

Foundational paper introducing federated learning under communication and privacy constraints.
Supports privacy-by-design and distributed training approach.

17. Nielsen Norman Group — Response Time Limits
https://www.nngroup.com/articles/response-times-3-important-limits/

Defines user-perceived latency thresholds (0.1s instant; 1s flow-preserving; 10s attention loss).
Supports real-time performance justification.