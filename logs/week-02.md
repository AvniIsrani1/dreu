# Week 2

**Dates:** 06-15 to 06-21

## Goals
- Begin reading related work at the intersection of machine learning and quantum error correction.
- Identify whether existing approaches are proactive or reactive.
- Understand common datasets, circuit types, error models, baselines, and evaluation metrics used in ML-based quantum error correction papers.


## Approach and Implementation

This week, I focused on transitioning from quantum computing foundations to related work directly connected to my project. I began reading papers about machine learning for quantum error correction and documented my notes in our shared Box folder. Since the project focuses on proactive quantum error prediction, I specifically paid attention to whether the papers were predicting future errors or reacting to already-detected errors.

Most of the papers I read so far were reactive rather than proactive. Several focused on error detection or correction after syndrome information was already available, rather than using historical circuit behavior to predict future error risk. I also read a survey paper that helped summarize why machine learning is useful for quantum error correction. One of the main points was that traditional quantum error correction has major resource overhead, and that as code distance increases, the number of required resources also increases.

While reading, I compared the papers based on what type of circuit or code they used, what errors they considered, what models they trained, what baselines they compared against, and what metrics they reported. Many of the papers used surface codes. Some papers focused on circuit-level errors, where the output is whether the overall circuit has an error, while others focused on qubit-level errors, where the output identifies which specific qubits have errors.

I also noticed that many papers create their own simulated datasets rather than using one shared benchmark dataset. Some papers used Stim for quantum error correction simulation, while others used PyTorch for the machine learning component. So far, I have not found many papers that use Qiskit directly for this type of work. Common baselines included traditional decoding approaches such as minimum weight perfect matching, as well as machine learning baselines depending on the specific paper.

During my meeting with Dr. Asadinia, I summarized the papers I had read so far and explained that they were mostly reactive. We discussed how this supports the motivation for my project, since proactive prediction appears to be less common in the papers I have reviewed so far. Dr. Asadinia also suggested that I should begin implementation by creating a simple quantum circuit, running it without errors, saving the baseline results, and then injecting different errors at different rates.

After our meeting, I started to read some more proactive papers. The main idea here was to predict the error first and then change the computation strategy before running the final circuit. 

## Results
- Began literature review on machine learning for quantum error correction.
- Documented notes on common circuit types, tools, baselines, and evaluation metrics. 
- Did not complete: I did not start the implementation yet. 

## Notes
- I will be traveling next week (06-22 to 06-28), so Dr. Asadinia and I will meet the following week.


