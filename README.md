# Creation and Evaluation of a Multilingual Synthetic Clinical Dataset for PHI De-Identification

## Motivation and Objectives 
The expanded use of large language models (LLMs) in healthcare has intensified privacy concerns, particularly in handling clinical notes, which contain sensitive personal health information (PHI). Privacy regulations such as the Health Insurance Portability and Accountability Act (HIPAA) and General Data Protection Regulation (GDPR) restrict the availability of clinical data for model training, limiting advancements in natural language processing (NLP) within this field. Privacy risks associated with closed, cloud-based corporate LLMs add further challenges to clinical NLP, especially for languages with limited resources. While previous work has shown that synthetic general-domain datasets can be generated to mask personally identifiable information, developing domain-specific datasets tailored to the unique needs of clinical NLP remains an open task [^1].

This project aims to develop a prototype system that generates synthetic, multilingual clinical notes tailored for PHI de-identification model training. Such models are essential for de-identifying real-world clinical notes, making these notes usable for advanced, privacy-compliant NLP applications within the biomedical domain.


![Overview IMG](https://github.com/coree/blah9-deid/blob/main/img/blah9-deid.png)

##  Goals
- Develop a pipeline utilizing LLMs like GPT4o as agents to produce a **synthetic clinical notes dataset for the PHI de-identification** task across **five languages**: English, Spanish, German, Italian, and Dutch.
- **Evaluate models trained on synthetic data against real-world gold-standard datasets**.

## Methodology
Our approach involves a multi-stage pipeline that uses LLMs to generate, annotate, and evaluate synthetic clinical notes:

**1. Synthetic Data Generation**  
   A set of LLM agents will produce multilingual clinical notes that mirror real-world text. This model will address existing gaps in non-English datasets, with particular emphasis on low-resource languages.

**2. Annotation for De-Identification**
   An additional LLM will annotate the synthetic notes for de-identification, marking PHI entities (e.g., names, dates) to prepare the data for privacy-compliant model training.


**3. Training and Evaluation**
   Pre-trained language models (PLMs) will be trained on the synthetic dataset and evaluated against public datasets, such as **Nursing Notes**[^2,3], **MedDocan**[^4], and **MultiLeg**[^5], to verify the model’s effectiveness when applied to real-world data.

**4. Red-Teaming and Quality Assurance (Optional)**
  An optional final step involves red-teaming, where an LLM rigorously evaluates the de-identified text. This red-team LLM will check for leaking entity types based on gold-standard datasets and provide a qualitative assessment, including a note and a label (“identifiable,” “partially identifiable,” or “non-identifiable”), for a comprehensive privacy check. This step will be implemented if time permits within the hackathon constraints.

This pipeline allows for robust evaluation and refinement, ensuring the synthetic dataset meets de-identification standards suitable for training models that generalize well to real-world data.

## Expected Results
By the end of the hackathon, we anticipate the following outcomes:

### Prototype Synthetic Dataset 
   A multilingual, PHI-annotated clinical dataset optimized for de-identification model training.

### Evaluation Insights
   Analysis of the performance of models trained on synthetic data when tested against datasets like Nursing Notes, providing insights into the applicability of LLM-generated synthetic data for clinical NLP tasks.

### Red-Team Analysis (Optional) 
   A red-team LLM that identifies privacy leaks in a more nuanced manner than simple named entity recognition (NER) metrics, providing deeper insights into privacy fidelity.

##  Timeline 
Our timeline is designed to support the development of a foundational prototype, with room for incremental improvements based on red-team feedback:

- **Day 1:** Codebase setup and initial text generation.
- **Day 2:** Synthetic text generation for multilingual clinical notes.
- **Day 3:** Model training and preliminary evaluation; enhancement of the generation system.
- **Day 4:** Evaluation refinement and red-teaming.
- **Day 5:** Presentation of results and reporting.

This timeline focuses on delivering a minimal working prototype, enabling us to explore LLMs’ potential in creating privacy-compliant clinical data.

## Conclusion
This project explores LLM-based synthetic data generation as a strategy to address data scarcity in clinical de-identification by producing a privacy-compliant, multilingual synthetic clinical dataset. Our approach combines generation, annotation, and red-teaming to ensure dataset quality and privacy compliance, supporting BLAH’s mission to enhance biomedical data interoperability. This prototype could ultimately pave the way for scalable, privacy-conscious NLP solutions across healthcare sectors.

## References
[^1] Ai4privacy/PII-masking-400k · datasets at hugging face. Hugging Face Datasets Ai4Privacy/PII-Masking-400k. (n.d.). https://huggingface.co/datasets/ai4privacy/pii-masking-400k  
[^2] Douglass, M., Long, B., Moody, G., Szolovits, P., Lehman, L., Mark, R., & Clifford, G. D. (2007). Deidentified Medical Text (version 1.0). PhysioNet. https://doi.org/10.13026/jc2a-ca12.   
[^3] Neamatullah I, Douglass M, Lehman LH, Reisner A, Villarroel M, Long WJ, Szolovits P, Moody GB, Mark RG, Clifford GD. Automated De-Identification of Free-Text Medical Records. BMC Medical Informatics and Decision Making, 2008, 8:32. doi:10.1186/1472-6947-8-32  
[^4] Marimon, Montserrat, et al. "Automatic De-identification of Medical Texts in Spanish: the MEDDOCAN Track, Corpus, Guidelines, Methods and Evaluation of Results." IberLEF@ SEPLN. 2019.  
[^5] Vīksna, Rinalds, and Inguna Skadiņa. "MultiLeg: Dataset for Text Sanitisation in Less-resourced Languages." Proceedings of the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING 2024). 2024.  
