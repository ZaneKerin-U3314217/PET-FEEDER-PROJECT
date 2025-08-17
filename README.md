# Pet Feeder System – Problem Solving Process
Pet Feeder Project submission for University of Canberra, Introduction to IT (4478) class by Zane Kerin U3314217, 
A comprehensive walkthrough of designing a low-cost, programmable automated pet feeder for a local animal shelter. This repository captures each step of the problem-solving process, from initial analysis through diagrams, pseudocode, evaluation, and testing.

---

## Table of Contents

1. [Problem Statement](#problem-statement)  
2. [Problem-Solving Process](#problem-solving-process)  
   - [Step 1: Analyse the Problem](#step-1-analyse-the-problem)  
   - [Step 2: Organise and Describe the Data](#step-2-organise-and-describe-the-data)  
   - [Step 3: Logical Flow Diagram](#step-3-logical-flow-diagram)  
   - [Step 4: Pseudocode (Word Code)](#step-4-pseudocode-word-code)  
   - [Step 5: Refine, Evaluate, and Test](#step-5-refine-evaluate-and-test)  
3. [Repository Structure](#repository-structure)  
4. [Viewing & Running the Work](#viewing--running-the-work)  
5. [Contributing](#contributing)  
6. [License](#license)  

---

## Problem Statement

A local animal shelter needs a low-cost, programmable automated pet feeder that can:
- Dispense food for cats and dogs at scheduled times.  
- Monitor whether food has been consumed or measure the amount consumed.  
- Alert staff if there’s an issue (e.g., no food dispensed, food not eaten).  

Your task is to design and simulate the logic and behavior of this system using pseudocode, diagrams, and documented processes before any hardware implementation.

---

## Problem-Solving Process

### Step 1: Analyse the Problem

- Identify stakeholders and their needs (shelter staff, animals).  
- Clarify functional requirements: scheduling, dispensing, monitoring, alerts.  
- Note constraints: must be low-cost, programmable, reliable.  

### Step 2: Organise and Describe the Data

- Define data inputs: current time, feeding schedule, sensor readings (food level, consumption).  
- Define data outputs: motor control signals, alert messages (email/SMS).  
- Document allowable ranges and formats for each data element.  

### Step 3: Logical Flow Diagram

- Create a flowchart illustrating system initialization, scheduled checks, dispensing logic, consumption verification, and error handling.  
- Highlight decision points (e.g., “Is it feeding time?”, “Was food consumed?”).  

### Step 4: Pseudocode (Word Code)

- Translate the flowchart into step-by-step pseudocode, using clear, descriptive statements.  

### Step 5: Refine, Evaluate, and Test

- Review logic for edge cases (power loss, sensor failure).  
- Develop test cases to simulate normal operation and failure modes.  
- Document evaluation results and iterate on the design.

## Repository Structure

```text
/
├─ Step1_Analysis/
│   └─ Step1_Report.md
├─ Step2_Organize_and_Describe_the_Data/
│   └─ Step2_Report.docs
├─ Step3_Flowchart/
│   └─ PF_Diagram_PNG.png
│   └─ PF_Diagram_RAW.drawio
|   └─ Flowchart_Revision_After_Step5/
|      └─ PF_Revised_Diagram_PNG.png
|      └─ PF_Revised_Diagram_RAW.drawio
├─ Step4_Implement_the_Solution/
│   └─ Step4_Report.md
├─ Step5_Evaluate_and_Refine_the_Solution/
│   └─ Step5_Report.docx
|   └─ Revised_Wordcode.docx
|   └─ Flowchart_Revision/
|      └─ PF_Revised_Diagram_PNG.png
|      └─ PF_Revised_Diagram_RAW.drawio

```

---

## Viewing & Running the Work

- Open the Markdown reports in any text editor or GitHub to review analysis and data definitions.  
- View `Step3_Flowchart/PF_Diagram_PNG.png` in an image viewer for the system’s logical flow.  
- Read `pseudocode/feeder_system_pseudocode.md` for the detailed word-code implementation.  
- Simulated test cases described in `Step5_Evaluate_and_Refine_the_Solution/Step5_Report.docx` to validate the logic.

---

## Contributing

Contributions, feedback, and questions are welcome. Please:

1. Fork the repository.  
2. Create a feature branch (`git checkout -b feature/your-feature`).  
3. Commit your changes (`git commit -m "Add feature"`).  
4. Push to the branch (`git push origin feature/your-feature`).  
5. Open a pull request describing your changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


## CHANGELOG
16/08/2025 (8:32 PM):
- Repository created.

17/08/2025 (9:45 AM):
- Invited Heena and Julio to the Repository (if they're reading this, it's not finished yet, please don't mark this version!!)

17/08/2025 (1:04 PM):
- Uploaded assignment work to it's relevant folders. 

17/08/2024 (5:23 PM):
- Revised readme and folder structure after consulting with Microsoft CoPilot, generally reorganized file structure. Readme is now pro
