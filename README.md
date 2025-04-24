

# prompt-strategy-comparison

---

# GenAI for Software Development (Prompt Engineering)

* [1 Introduction](#1-introduction)  
* [2 Getting Started](#2-getting-started)  
  * [2.1 Setup](#21-setup)  
  * [2.2 Folder Structure](#22-folder-structure)  
  * [2.3 Run Models](#23-run-models)  
* [3 Report](#3-report)  

---

# **1. Introduction**  
This project explores **prompt engineering strategies for AI models** on code-related tasks. Using **ChatGPT (GPT-4)** and **Claude AI**, we compare two prompting methods — **zero-shot** and **chain-of-thought** — across **22 software engineering tasks**, including code generation, bug fixing, and summarization. This project evaluates how different prompting styles affect the quality and reasoning of AI-generated solutions.

---

# **2. Getting Started**

This project requires **Python 3.10+** and is compatible with **macOS, Linux, and Windows**. While model interaction was conducted through web interfaces (ChatGPT and Claude), outputs and evaluations are stored and compared in this repository.

## **2.1 Setup**

(1) Clone the repository to your workspace:  
```shell
~ $ git clone https://github.com/Mohameddeidd/prompt-strategy-comparison.git
```

(2) Navigate into the repository:  
```shell
~ $ cd prompt-strategy-comparison
~/prompt-strategy-comparison $
```

(3) (Optional) Create a virtual environment if you're running supporting scripts locally:
```shell
~/prompt-strategy-comparison $ python -m venv venv/
~/prompt-strategy-comparison $ source venv/bin/activate
```

## **2.2 Folder Structure**

```
prompt-strategy-comparison/
├── prompts/
│   ├── task_01_chatgpt.md
│   ├── task_12_claude.md
│   └── ...
├── outputs/
│   ├── chatgpt_outputs/
│   ├── claude_outputs/
│   └── ...
├── report/
│   └── final_report.pdf
├── README.md
```

## **2.3 Run Models**

Model runs were completed manually using [ChatGPT (GPT-4)](https://chat.openai.com) and [Claude AI](https://claude.ai).  
All prompt inputs and outputs were saved in their respective markdown and text files within the `prompts/` and `outputs/` directories.

---

# **3. Report**

The final comparative analysis, including prompts, model outputs, reasoning, and conclusions, is available in the file:  
```plaintext
report/final_report.pdf
```
