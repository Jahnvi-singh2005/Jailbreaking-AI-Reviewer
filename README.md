# Jailbreaking-AI-Reviewer

This code is part of a research project on Jailbreaking LLMs and their prospective use for the purpose of peer review, that is, "AI - Reviewer". Various prompt injection strategies, like inserting malicious and manipulative prompt in white text, were implemented on research papers. The LLMs were then asked to provide a review on the paper. The LLM reviewer gave a higher score which the prompt injection and other similar strategies implemented, as compared to the original paper.
 
The workflow is as follows:

* PDF Extraction: The script uses PyMuPDF (fitz) to extract the full text from a PDF research paper.

* Prompt Engineering: A highly detailed system prompt defines the AI's role, the evaluation rubric, and a set of strict, falsification-oriented rules (the RBCL). This prompt instructs the AI to "presume rejection" and look for fatal flaws.

* AI Evaluation: The extracted text, the rubric, and the system prompt are sent to the gemini-2.5-flash model.

* Structured Output: The AI returns a structured JSON object containing a detailed review, including per-criterion scores and justifications for each.
