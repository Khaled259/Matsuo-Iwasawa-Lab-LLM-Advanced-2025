Here is the English translation of the document provided in the images.

---

### **Page 1: Title & Revision History**

**LLM Course 2025 Final Assignment Detailed Materials**
*Updated: 2025/01/25*

**Revision History**

| Date | ver | Update Content |
| :--- | :--- | :--- |
| 2026/01/20 | 0.1.0 | Initial Release |
| 2026/01/28 | 1.0.0 | Final Version Fix |
| 2026/02/05 | 1.0.1 | Added details to Advanced Comp Rules > Competition Evaluation |

---

### **Page 2: 1. Objective & 2. Background**

**1. Objective**
Utilizing the knowledge and skills learned in the lectures so far, you will develop a **Local LLM** (a model where data and inference are completed entirely locally) to compete for scores on benchmarks called **Struct-Eval** and **AgentBench**.
This competition consists of two tracks: the **Main Comp**, which all students participate in, and the **Advanced Comp**, for those who wish to tackle more advanced challenges.

*   **Main Comp**
    *   Apply the knowledge and skills learned in the lectures. A competition suitable for concluding the LLM application course.
    *   **Target Level:** Beginners to Advanced LLM learners.
*   **Advanced Comp**
    *   A competition with higher difficulty that pursues more "Agent-like" behavior.
    *   **Target Level:** Intermediate to Advanced LLM learners with some experience and skills.

Those who develop excellent models in each competition will be recognized with an "**Excellence Award**."
Additionally, we will recognize participants who not only achieve high scores but also contribute to the community by sharing useful information with a "**Contribution Award**."

**2. Background**
An Agent is a framework used as a system that achieves a goal by repeating the loop of **"Observation of Environment -> Action -> Reflection of Result."** What is important is not just the ability to answer questions, but the entire process of what was observed, how it was thought about and planned, and what action was selected along the way.

The benchmark used for the **Main Comp**, **StructEval**, focuses on the issue that as LLMs are integrated into software development and business workflows, the ability to generate structured data such as **JSON/YAML/CSV** exactly according to specifications becomes important. However, the evaluation of such structured output is more difficult than evaluating "Naturalness (fluency of text)." In addition to format-specific syntax, hierarchy, and constraints, **StructEval** comprehensively evaluates 18 formats and 44 task types across two paradigms:
*   Non-rendering formats (JSON/YAML/CSV, etc.) vs. Rendering formats (HTML/React/SVG, etc.)
*   Natural Language -> Structure (generation) and Structure -> Structure (conversion).

Furthermore, when an Agent acts upon an environment, the action is often represented by a structured interface. A typical example is tool calling (function calling), where tool definitions and arguments are specified by **JSON Schema**, etc. Therefore, it is necessary for the model to stably output a structure (argument objects, etc.) that conforms to that. Consequently, the fidelity of structured output tested by **StructEval** can be said to be one of the essential basic abilities for modern AI Agents.

The benchmark used for the **Advanced Comp**, **AgentBench**, is a benchmark that classifies interactive environments into three systems: Code / Game / Web (OS, DB, Knowledge Graph, Loose/Games, Web Shopping/Browsing, etc.) and assumes autonomous behavior in diverse environments close to practical use. What is important here is not the ability to answer a single question, but the ability to operate the external environment and behave well as an agent to complete the task. It evaluates whether the goal can be achieved through accumulated actions within multi-turn conversational exchanges that do not end with a single response. In other words, it is a task truly befitting an Agent, repeating **Observation -> Action -> Result Reflection -> Re-planning...**

In this **LLM Final Assignment Comp**, we have modified and resized these for the competition. Details are provided in the rules below.

---

### **Page 3: 3. Relation to Course Completion & 4. Participants & 5. Participation Method**

**3. Relation to Course Completion**
The submission score and deliverables for the Main Comp are related to the completion requirements of the course, similar to attendance and quizzes. **Those aiming for course completion must participate in the Main Comp.**
Submissions or scores for the Advanced Comp are not related to completion requirements, so participation is optional.

**4. Participants**
Please develop individually. Throughout the process, management will be done via your **OmniCampus** account. Sharing information on the dedicated Slack channel is encouraged, and multiple people cooperating on development is allowed, **but the development of data or models and the generation of tasks (inference) must be done individually.** If a violation is suspected upon checking the deliverables, we may check the development process and invalidate the deliverables.

**5. Participation Method / Conditions**
There are no special participation methods or conditions for the **Main Comp**. Those aiming to complete the course are requested to participate.
There is no participation form, etc.; those who submit to the scoring system are considered participants.
Regarding the **Advanced Comp**, there are participation conditions. For details, please refer to the *Advanced Comp Rules_Participation Conditions*.

---

### **Page 4: 6. Main Comp Rules (Part 1)**

From here, we will explain the rules for the Main and Advanced Competitions.
For matters not listed in this document, please operate as necessary. (Inquiry Form)
**Definition of LLM in this competition:** The output must be from the model itself. If the output is not from the model, it is not considered an LLM.
**Warning:** If prohibited acts listed are not observed and the administration judges it so, it will be treated as equivalent to non-submission, so please be careful.

**6. Main Comp Rules**
This applies to the Main Comp. Please confirm carefully before participating.
The scope is feasible within the **Google Colab Free Plan (T4 GPU)**, and it is recommended for those with limited computing resources or those who have just started learning about LLMs.

**6.1 Main Comp Rules_Completion Requirements**
The score and deliverables of the Main Comp are related to the course completion requirements, similar to attendance and quizzes. **Those aiming for course completion are asked to develop and improve their models to achieve a score equal to or higher than the Baseline Score (to be published after the competition starts) announced by the administration, and submit them.**

*Note:* The score on the OmniCampus leaderboard is overwritten with each submission, so the highest score is not always displayed. However, **past scores of students are preserved in the DB, so if your highest score in the past has exceeded the baseline, it is OK.** (It is OK if the highest score exceeded the baseline even once).

**Notes**
*   **We will not respond to individual inquiries about whether you have exceeded the baseline, so please keep track of it yourself.**
    *   We plan to make past scoring history viewable on the student side, but we do not guarantee it, so please keep a record.
*   This is strictly *one* of the completion requirements. It is a necessary condition, not a sufficient condition.
    *   Attendance and quiz results will also be taken into account for the decision.
*   The baseline is a level that can be cleared if the sample code provided by us is executed with appropriate modifications such as parameter changes.

**6.2 Main Comp Rules_Competition Evaluation**
In the Main Comp, if you submit the **json file** generated using the developed model on OmniCampus, the score will be automatically calculated. The scoring results are reflected on the leaderboard periodically, and can be checked on OmniCampus.
The final score will be calculated separately at the timing of the competition's end, determining the ranking. Details of the evaluation will be released at the time of the ranking announcement.
**Errors may occur due to concentrated access near the deadline, so we recommend submitting with time to spare.**
The maximum number of submissions is set to **50 times (planned)**, so we recommend planned submissions.

---

### **Page 5: 6.3 Main Comp Rules_Benchmark Introduction**

In the Main Comp, evaluation is performed using a unique benchmark that is a modified version of **Struct Eval**.
Struct Eval is a benchmark that measures the ability to generate structured output in LLMs.
*Example:* "Output this in json format," "Convert json format to yaml format," etc.

The Struct Eval benchmark is broadly divided into two evaluation sets:
*   **Struct Eval - T**: Measures text generation.
*   **Struct Eval - V**: In addition to the above, performs visual evaluation of rendered content.
**In this competition, only Struct Eval - T is the target for evaluation.**
We test whether the LLM can generate accurate structured data that works without errors in the workflow of computer systems or software development AI agents.

**Struct Eval - T Task Example: JSON Generation Task**
For example, a prompt like the following is given:

...
`Please output JSON code.`

`Task:`
`Summarize metadata about a fictional scientific article.`

`Feature Requirements:`
`1. Top-level field "title" is a string`
`2. Field "authors" is a list of exactly two items`
`3. Each author has "name" and "affiliation"`
`4. Field "publication.year" is an integer`
`5. Field "keywords" is a list of strings`
...

Upon receiving this, the model is expected to output something like the following:

```json
{
  "title": "Temporal Anomalies in Sub-Atomic Particle Acceleration: A Case Study",
  "authors": [
    {
      "name": "Dr. Aris Thorne",
      "affiliation": "Institute of Theoretical Chronophysics, Zurich"
    },
    {
      "name": "Prof. Elena Voshkova",
      "affiliation": "Department of High Energy Physics, MIT"
    }
  ],
  "publication": {
    "year": 2028
  },
  "keywords": [
    "Chronophysics",
    "Particle Acceleration",
    "Temporal Dilution",
    "Quantum Mechanics"
  ]
}
```

---

### **Page 6: Evaluation Logic**

For this, there are scoring criteria for each task to judge whether it conforms to the JSON specification, as follows:

```json
"raw_output_metric": {
    "title",
    "authors[0].name",
    "authors[1].affiliation",
    "publication.year",
    "keywords[2]"
}
```

This is interpreted as follows:
*   `title`: OK if "title" exists at the top level.
*   `authors[0].name`: OK if "name" exists in the 0th element of authors.
*   `authors[1].affiliation`: OK if "affiliation" exists in the 1st element of authors.
*   `publication.year`: OK if "year" exists inside the nested "publication".
*   `keywords[2]`: OK if there is a 3rd element in the Keyword array.
*   *Note: The value inside does not matter.*

The actual evaluation data looks like the following, and `raw_output_metric` is the scoring criteria part explained above.

**Example of Evaluation Data**
```json
[
  {
    "task_id": "000500",
    "query": "Please output JSON code:\n\nTask:\n...",
    "feature_requirements": "",
    "task_name": "Text to JSON",
    "input_type": "Text",
    "output_type": "JSON",
    "query_example": "",
    "VQA": [],
    "raw_output_metric": [
       "novel.title",
       "novel.author.name",
       "novel.characters[0].name"
    ],
    "rendering": false
  }
]
```

---

### **Page 7: Inference Result & Modifications**

The inference for this looks like the following.

**Example of Inference Result**
```json
[
  {
    "task_id": "000500",
    "query": "Please output JSON code:\n\nTask:\n...",
    ...
    "raw_output_metric": [...],
    "rendering": false,
    "generation": "```json\n{\n \"novel\": {\n  \"title\": \"The Obsidian Labyrinth\",\n  \"author... "
  }
]
```

The inference result by the LLM is assigned as `"generation"`. regarding this generation result:
*   Can it be parsed as JSON (in this example)?
*   How much of the scoring criteria in `raw_output_metric` does it satisfy?
are evaluated.

**However, this is the evaluation data and method of the original StructEval-T. In this competition, the following modifications have been made:**

*   `raw_output_metric` is hidden so it cannot be known from the evaluation data.
    *   The evaluation system (OmniCampus) embeds it by linking it with `task_id`.
*   The `raw_output_metric` of each task has been changed (scoring criteria have been changed).

In this competition, the scoring criteria are hidden from the participants, and furthermore, the scoring criteria themselves are changed.
This is to prevent participants from conducting learning specialized for the scoring criteria of the evaluation data. (Let's stop learning that strongly intends for the evaluation data, which is the original story).

**Additionally:**
*   The evaluation method and algorithms are generally the same as the original, but some changes have been made for the competition.
*   Regarding the overall score used in the competition: The evaluation scores for each format are averaged, and a unique weighting is applied to calculate it.

*Because of this, please note that there will be some discrepancies in the scoring results compared to running the original Struct Eval.*
*Details of the evaluation will be private.*

---

### **Page 8: Learning Hints & Submission Deliverables**

**Learning Hints**
The format of the tasks are:
*   TEXT to OO: Output a specific format from natural language sentences (Generation Task).
    *   Example tasks explained earlier fall here.
*   OO to XX: Convert from a specific format to a specific format (Conversion Task).
These are the 2 patterns.
Also, the formats handled are the following 5 types:
*   JSON
*   YAML
*   TOML
*   XML
*   CSV

In this competition, we evaluate the **"ability to stably generate the correct structure" in the "specified output format."**
Therefore, please work on it with the intention of **not breaking the syntax, not dropping requested keys, not outputting unnecessary sentences (outputting only code)**.

**6.4 Main Comp Rules_Deliverables**
Participants are to submit the following two items:
1.  A **JSON file** output using the **inference code provided by the administration**.
2.  The **URL** of the model you developed, uploaded to **Hugging Face**.
    *   a. Make the model **public** so the administration can use it.
    *   b. Please also include a **README**.

**For both 1 and 2, please submit via the submission page on OmniCampus.**

The json file (evaluation data: `public_150.json`) which is the input for the task is a file containing the following format:
*(Image shows a JSON block with "task_id", "task_name", "query", etc.)*

When using the inference code provided by the administration, a **json file** like the following will be output as the result.
The inference result is generated as `"generation"` for the corresponding `task_id`.
*(Image shows a JSON block with "task_id" and the generated output in "generation")*

Please submit this file (filename: `inference.json`).
Just to be safe, we recommend checking the data after downloading (DL) the inference result.

---

### **Page 9: Submission Details & Prohibitions**

**Regarding submissions, please note the following points:**

*   **Inference (Creation of Deliverables):** Please use the **standard code provided by the administration**.
    *   The model used for inference should be uploaded to HuggingFace. Please make sure it is a model developed by yourself (details on model restrictions described later).
*   **Editing the deliverable (`inference.json`) created by the inference code is prohibited.** (Examples below)
    *   Editing using services like ChatGPT or APIs.
    *   Checking and editing by human hand.
    *   Please do not do anything to try to raise the score by doing things like the above.
*   Please upload the developed model to **Hugging Face**, not OmniCampus.
    *   At that time, please set the model's public setting to **Public**.
*   The **README** is a distribution from the administration, so please write it following the sample presented.



Here is the English translation of the provided document images.

---

### **[Page 10] 6.5 Main Comp Rules_Materials Distributed by Administration**

**Distribution timing will be at the start of the Main Comp.**

*   **Evaluation Data**
    *   File Name: `public_150.json`
    *   **<u>DO NOT use for training</u>**
        *   If you are new to competitions, please also refer to the supplementary material "Agreements in LLM Model Development".
    *   **<u>DO NOT modify. Manual intervention, tools, and LLMs are strictly prohibited.</u>**
*   **Standard Code**
    *   Model Training Code
        *   File Names:
            *   `2026_Final_Assignment_MainComp_Standard_Code1_(SFT).ipynb`
            *   `2026_Final_Assignment_Qualifiers_Standard_Code3_(DPO).ipynb`
        *   These can be freely modified.
        *   HuggingFace WRITE permission will be required.
        *   Includes a HuggingFace README sample.
            *   There is a cell for writing the README, so please use it as a reference.
    *   Model Inference Code (Inference Code)
        *   `2026_Final_Assignment_MainComp_Standard_Code2_(Submission_JSON_Generation).ipynb`
        *   **<u>Please use this without modifying anything other than the model information.</u>**
            *   **<u>Therefore, RAG, Tool Use, or linking with external services running during inference are all prohibited.</u>**
        *   This will create the submission json file (`inference.json`).
*   **Training Data Summary**
    *   Synthetic data created by the administration.
    *   Other license-compatible datasets are planned to be introduced.
    *   *Note: These do not guarantee that the score will definitely increase.*

---

### **[Page 11] 6.6 Main Comp Rules_Model Related**

**The restrictions regarding the models to be developed are as follows:**

*   The designated base models for learning in this competition are:
    *   `Qwen/Qwen3-4B-Instruct-2507`
    *   `unsloth/Qwen3-4B-Instruct-2507`
    *   Use of models other than these is not permitted. Derivative models are also prohibited.
*   The model to be submitted must be a model trained on the designated base model.
    *   Changes to the model architecture are not permitted.
*   The model to be submitted must be uploadable as a model to Hugging Face.
    *   A WRITE authority key is required. Please check "Supplementary Materials > How to obtain a HuggingFace Token" for how to obtain it.
*   The submitted model must have some changes applied to it.
    *   Updating parameters via SFT, RLHF, DPO, etc., satisfies this condition.
    *   Quantization also counts as a change.
*   Using StructEval data at any stage of model development is prohibited.
    *   Using the evaluation data provided by the administration is obviously prohibited, but using the original StructEval data is also prohibited.
*   Tuning using the leaderboard is prohibited.

### **6.6 Main Comp Rules_Training Data Related**

**The restrictions regarding data used for model training are as follows:**

*   **Use of data other than that provided or introduced by the administration is prohibited.**
    *   Please conduct training within the scope of data provided or introduced by the administration.
*   **Creation of data using LLMs is prohibited.**
    *   It is prohibited to modify or synthesize data provided or introduced by the administration using an LLM.
*   **Creation of data WITHOUT using LLMs is allowed.**
    *   Please check the supplementary materials for details.
        *   Supplementary Materials > Agreements in LLM Model Development
        *   Supplementary Materials > Data Creation by LLM
    *   For example, it is possible to modify data provided or introduced by the administration without using an LLM.

---

### **[Page 12] 7. Advanced Comp Rules**

**These are the rules for the Advanced Comp. Please review them carefully before participating.**
Participation is optional. It is a competition for advanced users where you can work with freer rules than the Main Comp, and the difficulty is higher, so please be prepared if you participate.
Also, the Advanced Comp is related to the selection of the Excellence Award, so those aiming for the Excellence Award should actively participate in the Advanced Comp.

**7.1 Advanced Comp Rules_Participation Conditions**
**There are participation conditions for the Advanced Comp.**
Please apply for participation via the [Google Form] by 23:59 on Wednesday, 2026/02/04.
*The participation form is scheduled to open after the competition briefing on 2026/01/28 (Wed).*

**<u>Based on the submission history of deliverables in the Main Comp as of 17:00 on Sunday, 2026/02/08, we will select participants from those who applied via the participation form (Maximum 200 participants expected).</u>**
The development environment for the Advanced Comp will be opened to those selected.
We ask that you actively participate in the Main Comp and develop a good model.

**<u>Please ensure that the submission page is used only by Advanced Comp selectors.</u>**

**7.2 Advanced Comp Rules_Competition Evaluation**
In the Advanced Comp, the developed model is run in the OmniCampus backend environment, and a tentative score is automatically calculated using an evaluation program. The scoring results are periodically reflected on the leaderboard and can be checked on OmniCampus.
The score on the leaderboard is tentative; the final score will be calculated separately at the timing of the competition's end, determining the ranking. Details of the evaluation will be released at the time of the ranking announcement after the competition ends.
We ask you to develop a model that can respond generally to the tasks in this competition, without overfitting to the contents of the evaluation data. (Please also read the Supplementary > Agreements in LLM Model Development).

**<u>You can submit up to a maximum of 20 times (planned). Since the number of times is limited, we recommend planned submissions.</u>**
**<u>Errors may occur due to concentrated access near the deadline, so we recommend submitting with time to spare.</u>**

---

### **[Page 13] Requests regarding Scoring System and Submit**

**Since this scoring system utilizes GPU instances, scoring failures are expected as follows:**
1.  Failure to secure GPU resources at the time of scoring.
2.  Errors during scoring.
3.  Exceeding scoring time limit (described later).
We apologize, but for case 1, please wait a while. For cases 2 and 3, please carefully verify beforehand whether inference runs using the development environment, and if the execution time is okay.

**Also, evaluation in the scoring system is performed as follows:**
1.  Launch a `vllm` Docker container using the submitted model information.
2.  Inference.
The scoring execution time includes both 1 and 2.

**<u>About Scoring Errors</u>**
**<u>Due to system specifications, the submission count is consumed even in cases of errors or exceeding scoring time (described later).</u>**
We apologize, but please carefully verify beforehand whether inference runs using the development environment, and if the execution time (including vllm startup time) is okay.

**<u>About Scoring Time Limit</u>**
**<u>A time limit of 2 hours 20 minutes (planned) is set for one scoring run. If this is exceeded, it will be a "Scoring Failure".</u>**
The count starts from when the submission begins.
Reference: The scoring execution time for the designated learning model (untrained/no LoRA attached) is a maximum of 1 hour 40 minutes.

**<u>Request for Cooperation for Smooth Operation</u>**
Since limited computing resources are shared among all participants, we would appreciate your cooperation in distributing the load on the infrastructure.
As a guideline, if you aim for **<u>about 1 submission every 4 days</u>**, the system will stabilize, and the waiting time for scoring for everyone will be shortened.

**<u>About Trouble Near the Deadline</u>**
If submissions fail due to the impact of concentrated access just before the end of the competition, we will check logs and past usage status (whether there were unreasonable consecutive posts, etc.) and consider relief measures individually.
We will prioritize support for those who cooperate with stable operation, so we appreciate your cooperation.

To ensure everyone can use the scoring infrastructure stably, we ask for your understanding and cooperation on the points above.

---

### **[Page 14] 7.3 Advanced Comp Rules_Benchmark Introduction**

In the Advanced Comp, **AgentBench** is used.
It is a benchmark that builds 8 diverse interactive environments mimicking the real world, such as OS operation, DB operation, Online Shopping, Reasoning Puzzles, etc., and solves tasks given to the model.
Examples:
*   Plan and execute a series of physical actions inside a house such as "Search -> Pick up -> Clean -> Place".
*   Actually execute SQL and answer in response to a question.

This time, we will adopt 2 tasks from these and compete on the total score.
(*Refer to the paper for how to calculate the total score. Other information will be released at the time of final result announcement.*)

*   **DB Bench:**
    *   Task to receive table information and requests, assemble appropriate queries, and operate the DB.
    *   **<u>150 questions (reduced for the competition).</u>**
*   **ALFWorld:**
    *   Task to receive environment description + task goal, and output actions to achieve the goal.
    *   50 questions.

We test the ability of an Agent to obtain the expected response by acting on instructions given to the LLM, interacting with the environment, and correcting its actions.

**<u>Task Example_DB Bench:</u>**
The Agent (LLM) receives a prompt like the following from the system.
Instructions on the Agent's description style, the problem text, and table information.

*(Prompt Example)*
`User:`
`I will ask you a question, then you should help me operate a MySQL database with SQL to answer the question.`
`You have to explain the problem and your solution to me and write down your thoughts.`
`After thinking and explaining thoroughly, every round you can choose to operate or to answer.`
`your operation should be like this:`
`Action: Operation`
`'''sql`
`SELECT * FROM table WHERE condition;`
`...`
`You MUST put SQL in markdown format without any other comments. Your SQL should be in one line.`
`Every time you can

Here is the English translation of the document images provided.

---

### **[Page 15] 7.6 Advanced Comp Rules_Model Related**

**The restrictions regarding the models to be developed are as follows:**

*   **The designated base models for learning in this competition are:**
    *   `Qwen/Qwen2.5-7B-Instruct`
    *   `Qwen/Qwen3-4B-Instruct-2507`
    *   Use of models other than these is not permitted. Derivative models are also prohibited.
*   **The submitted model must be a model trained on the designated base model.**
    *   Changes to the model architecture are not permitted.
*   **The model must be uploadable to Hugging Face.**
*   **You must apply some form of change to the model.**
    *   Updating parameters via SFT, RLHF, DPO, etc., satisfies this condition.
    *   Quantization also counts as a change.
*   **Using `AgentBench` and `ALFWorld` data at any stage of model development is prohibited.**
    *   Generating synthetic data using this data is also prohibited.
*   **Tuning using the Main Comp leaderboardHere is the English translation of the document provided in the images.

---

### **[Page 15] 7.6 Advanced Comp Rules_Model Related**

The restrictions regarding the models to be developed are as follows:

*   **The designated training models for this competition are:**
    *   `Qwen/Qwen2.5-7B-Instruct`
    *   `Qwen/Qwen3-4B-Instruct-2507`
    *   Use of models other than these is not permitted. Derivative models are also prohibited.
*   **The submitted model must be a model trained on the designated base model.**
    *   Changes to the model architecture are not permitted.
*   **It must be possible to upload the model to Hugging Face.**
*   **You must apply some form of change to the model.**
    *   Updating parameters via SFT, RLHF, DPO, etc., satisfies this condition.
    *   Quantization also counts as a change.
*   **Using AgentBench and ALFWorld data at any stage of model development is prohibited.**
    *   Generating synthetic data using this data is also prohibited.
*   **Tuning using the Main Comp leaderboard is included in this prohibited behavior.**
*   **Distillation is allowed.**
    *   However, the teacher model must only be from the **whitelist of models** provided separately.
    *   The architecture of the final model to be scored must be identical to the designated model and must be based on the designated model.
*   **Since the evaluation environment runs on L4 GPU instances, please do not train models that do not run on an L4 GPU with 24GB VRAM.**

*\*The whitelist is scheduled to be released at the start of the Advanced Comp.*

---

### **[Page 16] Backend Execution Command & Important Points**

Since this competition loads participants' models on the backend for inference, there are strict specifications for the model format. For inference, the official `vLLM` Docker image is used, started with the command below.
**Please note that models that do not is included in this prohibited behavior.**
*   **Distillation is available (allowed).**
    *   However, for the teacher model, **use only the models on the separately provided whitelist.**
    *   The architecture of the final model to be scored must be identical to the designated base model and must be based on the designated model.
*   **The evaluation environment runs on L4 GPU instances, so please do not train models that do not run on L4 GPU VRAM (24GB).**

*The whitelist is scheduled to be released at the start of the Advanced Comp.*

**Since the competition loads participant models on the backend for inference, there are strict specifications for the model format.**
For inference, the official vLLM Docker image is used, started with the command below.
**Please note that models not working in this environment will be considered evaluation failures.**

```bash
docker run --runtime nvidia --gpus all \
    --ipc=host \
    vllm/vllm-openai:v0.13.0 \
    --model "Participant's submitted model path" \
    --max-model-len 8192 \
    --gpu-memory-utilization 0.95
...
```

**Important Points**
*   **Architecture changes prohibited:** Changing the architecture of the designated model is not allowed.
*   **Tokenizer change restrictions:** Adding vocabulary is prohibited.
    *   If the parameter size of the Embedding layer changes due to added vocabulary, there is a high risk of shape mismatch errors during vLLM startup.
*   **Handling Adapters (LoRA, etc.):**
    *   If using adapters like LoRA, **you must submit the model in a merged state with the base model.** The method of dynamically loading adapters at runtime is not possible.
*   **Quantization:**
    *   The administration will not apply startup options such as `--quantization`.
    *   If submitting a quantized model (AWQ, GPTQ, etc.), the quantization settings in the model's `config.json` (`quantization_config`) must be correctly described, and it must be in a format that vLLM can automatically recognize (format saved by AutoAWQ/AutoGPTQ, work in this environment cannot be evaluated.**

```bash
docker run --runtime nvidia --gpus all \
    --ipc etc.).
*   **Mandatory Chat Template:**
    *   Since OpenAI-compatible endpoints (`http://localhost:=host \
    vllm/vllm-openai:v0.13.0 \
    8000/v1/chat/completions`) are used, please ensure that a correct `chat--model "Participant's_Submission_Model_Path" \
    --max-model-len 8192_template` is included in `tokenizer_config.json`.

*Inference tests using vLLM are possible in the development \
    --gpu-memory-utilization 0.95
...
```

**Important Points**

* environment beforehand. Please use it to verify if inference runs.*

---

### **[Page 16]    **Architecture Change Prohibited:** Changing the architecture of the designated model is not allowed.
*   **Tokenizer Change7.7 Advanced Comp Rules_Data Related**

**The restrictions regarding data used for LLM learning are as follows Restriction:** Adding vocabulary is prohibited.
    *   If the parameter size of the Embedding layer changes due to added vocabulary, there is:**

*   **Synthetic data is allowed.**
    *   However, **use only models on the separately provided whitelist.**
 a high risk of shape mismatch errors during vLLM startup.
*   **Handling of Adapters (LoRA        *   You are free to quantize the whitelist models.
*   **For the Advanced Comp, it is OK to find, etc.):**
    *   If using adapters like LoRA, **you must submit the model in a state where data yourself that has no licensing issues and use it for training.**
*   **When using data other than that provided or introduced by the administration, please pay attention to the following points:**
    *   Use licenses that do not restrict non it is merged with the base model.** The method of dynamically loading adapters at runtime is not allowed.
*   **Quantization:**
    *   The administration will not add startup options such as `--quantization`.
    *   If submitting a-commercial use.
    *   Use only data that is obtained without permission issues, or where the provider allows use.
    *   The administration will only respond to inquiries regarding data provided or introduced by the administration.
    * quantized model (AWQ, GPTQ, etc.), the quantization settings (quantization_config) must be correctly described in   Use of paid data is prohibited.
    *   Use of data that is not public (accessible free of charge by the model's `config.json`, and it must be in a format that vLLM can automatically recognize without settings ( anyone) is prohibited.
    *   **<u>Please be extremely careful with the handling of various licenses.</u>**format saved by AutoAWQ/AutoGPTQ, etc.).
*   **Chat Template Mandatory:**
    *   Since the
*   **Of course, do not use the data used in AgentBench, nor data that mimics it.**

### OpenAI-compatible endpoint (`http://localhost:8000/v1/chat/completions`) is used, **8. Tool Usage in Development**

**Restrictions regarding APIs, libraries, software, external tools, etc. (Common please ensure that a correct `chat_template` is included in `tokenizer_config.json`.

**You can test to Main & Advanced Comp)**
If the administration judges that prohibited acts listed are not observed, it will be treated as inference with vLLM in the development environment beforehand. Please use it to confirm that inference runs.**

---

### **[ equivalent to non-submission, so please be careful.
*In this competition, "LLM" refers to models inPage 17] 7.7 Advanced Comp Rules_Data Related**

The restrictions regarding data used for LL general that output text, and so-called "Embedding Models" that do not output text are not included in this definition.*M training are as follows:

*   **Synthetic data is allowed.**
    *   However, **only models

**Allowed:**
*   **Development Coding Assistance:**
    *   Using coding support AI/LLMs for program on the separately provided whitelist** may be used.
        *   You are free to perform quantization on whitelist models.
* code creation, debugging, etc.
    *   Example: Code generation by GitHub Copilot, Cursor, ChatGPT (   **For the Advanced Comp, you may find data yourself that poses no licensing issues and use it for training.**
*   **Web version), etc.
    *   **<u>Must be used ONLY as coding assistance.</u>**
        *If using data other than that provided or introduced by the administration, please be careful of the following points:**
    *   Use   (Note: Technically you could ask Codex or ClaudeCode to synthesize data, but please do not do so.)
*    data with licenses that do not restrict non-commercial use.
    *   Only use data obtained without permission issues, or data that**Model Execution Libraries/Tools:**
    *   Libraries or inference/training tools to run **permitted models (Main the provider allows for use.
    *   The administration will only respond to inquiries regarding data provided or introduced by the Comp: Designated Learning Models / Advanced Comp: Designated Learning Models + Whitelist Models)**.
    *   Assuming use administration.
    *   Use of paid data is prohibited.
    *   Use of data that is not public for model inference/training, or synthesis (*only in Advanced Comp*), but may be used otherwise.
*    (accessible free of charge to anyone) is prohibited.
    *   **<u>Please be extremely careful regarding the handling of various**Non-LLM Data Processing:**
    *   Regular expressions, morphological analysis, Excel operations, and data processing ** licenses.</u>**
*   **Obviously, do not use the data used in AgentBench, nor data that imnot relying on LLM inference capabilities**.
    *   Text processing using encoder models like BERT, RoBERTa, DeBERitates it.**

---

### **[Page 18] 8. Handling of Tools in Development**

The restrictions regarding APIs, libraries, software, external tools, etc., are as follows (Common to Main Comp and AdvancedTa, etc.

**Prohibited / Forbidden Acts:**
*   **API Usage of Major Commercial Models (OpenAI, Anthropic, Google, etc.)**
    *   Use of APIs for closed commercial models such as ChatGPT API, Claude API, Comp).
If the listed prohibited matters are not observed and the administration determines so, it will be treated strictly, equivalent to non- Gemini API, regardless of whether paid or free, is prohibited.
*   **API Usage of Permitted Models (submission, so please be careful.
*Note: In this competition, "LLM" refers to all models that output LLMain Comp: Designated Models, Advanced Comp: Designated + Whitelist) other than open models.**
    *   Llama3, etc.
*   **Data Synthesis and Expansion using Translation Services**
    *   Data augmentation usingM, and so-called encoder models that do not output LLM are not included in this.*

**Allowed:**
*   **Development Coding Assistance:**
    *   Using coding support AI/LLMs for program code creation, debugging closed translation services (English -> Japanese -> English to increase variation, etc.) is prohibited.

---

### **[, etc.
    *   Example: Code generation by GitHub Copilot, Cursor, ChatGPT (Web version), etc.
    Page 17] Important Points**

*   Regarding LLM models, everything is restricted to the **Designated Learning Models + Whitelist**, so do not use others.
*   Non-LLM processing (Rule-based is obvious, but also processing using models like BERT) is **OK**.
*   Coding Agents should be used **only for writing code**.
*   Do not use closed model **APIs**.
*   Do not use **APIs** of open models other than the Whitelist models.
*   Use translation **only for reading documents in your native language**.

**Notes**
*   If scraping for data synthesis in the Advanced Comp, please follow `robots.txt` and rules specified by the site, and observe the terms of service. Also, be careful not to include personal information.
*   **<u>Must be used only as coding assistance.</u>**
        *   Asking Codex or ClaudeCode to synthesize data is technically possible, but please do not do it.
*   **Model Execution Libraries/Tools:**
    *   Libraries and inference/training tools to run allowed models (**Main Comp: Designated Training Models, Advanced Comp: Designated Training Models + Whitelist Models**).
        *   It is assumed they are used to infer/train models or synthesize (Advanced Comp only), but they may be used otherwise.
*   **Non-LLM Data Processing:**
    *   Regular expressions, morphological analysis, Excel operations, and other data processing that does not rely on LLM inference capabilities.
    *   Text processing using*   **You must strictly follow the terms of service of each service.**
*   Those participating in the finals should also check encoder models like BERT, RoBERTa, DeBERTa, etc.

**Not Allowed / Prohibited Actions:**
* "Supplementary Materials > About Data Creation".

### **9. Development Environment**

**We do not provide a development environment   **API Usage of Major Commercial Models (OpenAI, Anthropic, Google, etc.)**
    *   Use for Main Comp participants.** Please prepare a Google Colab environment, etc., yourself and work on development. The content of the competition itself of APIs for closed commercial models such as ChatGPT API, Claude API, Gemini API, etc., is prohibited regardless of whether they is feasible within the Google Colab Free Tier (T4 GPU).

**We will provide a development environment for Advanced Comp participants.** are paid or free.
*   **API Usage of Allowed Models (except Designated Training Models + Whitelist Models)**
    *   API usage of open models other than those allowed (e.g., Llama3, etc.) This will be an environment capable of inference and evaluation for AgentBench. You may also use it for model training. (* is prohibited.
*   **Data Synthesis and Augmentation using Translation Services**
    *   Data augmentation using closed translationModel training code is not planned to be provided.*)

**Basic Specs**
*   CPU Memory: 32GB
*   GPU: L4 (24GB)
*   Storage:
    *   Please refrain from services (e.g., English -> Japanese -> English to increase expressions) is prohibited.

---

### **[Page  downloading data or files exceeding 100GB.
    *   Due to volatility, if you wish to persist19] Key Points & 9. Provided Development Environment**

**Points**
*   Regarding LLM models, everything is data, please download appropriately.

**Important Notes**
*   Participants cannot install new containers like Docker.
* restricted to Designated Training Models + Whitelist, so do not use others.
*   Non-LLM processing (Rule   It is possible to write scripts individually and use them comfortably, but the administration will not provide support for customization.
*   Libraries like `uv` or `miniconda` and other software not conflicting with competition rules are usable, but operation is not verified. Since-based is fine, processing using models like BERT is OK).
*   Coding Agents should only be used for writing code.
 there is no support from the administration, please use at your own responsibility.
*   Inference code is placed in the exercise*   Do not use closed model APIs.
*   Do not use APIs of open models other than Whitelist models.
*   Translation should only be used for reading documentation in your native language.

**Notes**
*   If scraping for environment, and it is possible to execute it to check inference time and output, but please note that it assumes execution strictly data synthesis in the Advanced Comp, please observe `robots.txt` and the rules specified by the site, and do it within the exercise environment.
*   **<u>There are restrictions on usage time. Usage is possible up to a total of within the terms. Also, be careful not to include personal information.
*   Be sure to follow the terms of service for 60 hours (planned) depending on GPU usage amount. (If using 2 L4s simultaneously, consumption each service.
*   Those participating in the final match should also check the Supplementary Materials > Data Creation.

** time is 2x; if using 4 simultaneously, it is 4x).</u>**

Please check the separate9. Provided Development Environment**
For Main Comp participants, we do not provide a development environment. Please prepare your own environment manual for usage instructions.

---

### **[Page 18] 10. Excellence Award**

We will commend those who have made excellent efforts in the competition.

**Selection Conditions for Excellence Award are as follows:**
 such as Google Colab and work on development. The content of the competition itself is feasible within the **Google Colab Free*   Candidates are those who have observed the rules of the Advanced Comp and Main Comp.
*   In addition to Tier (T4 GPU)**.
For Advanced Comp participants, we will provide a development environment. This will be an environment capable the final score, submission content will be reviewed for selection.
*   **Submission of development documents is required.**
     of inference and evaluation for AgentBench. You may use it for model training. (Model training code is not planned to be provided).*   You will be asked to submit a development document explaining the model development process on Notion.
    *   *We

**Basic Specs**
*   CPU Memory: 32GB
*   GPU: L4 (2 will contact you separately regarding the content of the development document.*

*Selection conditions are subject to change.*

**The Selection4GB)
*   Storage:
    *   Please refrain from downloading data or files exceeding 100GB.
    *   Due to volatility, please use DL etc. appropriately if you want to keep data permanently.

 Categories are planned as follows:**
*   **<u>General Category</u>**
    *   Maximum 20 people**Important Notes**
*   Participants cannot install new containers such as Docker.
*   Writing scripts individually and using them comfortably is possible, but the administration will not support customization.
*   Libraries such as `uv` or `miniconda from the **Advanced Comp**.
*   **<u>U-29 Category</u>**
    *   Maximum 5 people from the **Advanced Comp or Main Comp**.
    *   Limited to students or young professionals aged 29 or under (Elementary school to Graduate school).
*   **<u>U-18 Category</u>**
    *   A few people from` and other software not conflicting with competition rules are available, but operation is not verified. Administration support is not available, so please use the **Advanced Comp or Main Comp**.
    *   Limited to students aged 18 or under (3rd at your own risk.
*   Inference code is placed within the exercise environment. It is possible to execute it to check-year High School students or 3rd-year Kosen students and below).

*Announcement of Excellence Awards and details are inference time and output, but please note that it is intended only for execution within the exercise environment.
*   ** scheduled for the Final Results Presentation.*

### **11. Posts on Dedicated Channel and Contribution Award**

**<u><u>There is a limit on usage time. You can use it up to a total of 60 hours (planned) dependingPosting Rules</u>**
*   We have prepared a dedicated channel for sharing competition information on the Slack of the Matsuo Lab LLM Community.
    *   `#12_llm2025_competition_discussion on GPU usage. (If using 2 L4s simultaneously, consumption time is 2x; if using 4`
*   We invite posts related to the competition here.
*   We assume you will write on **LL simultaneously, it is 4x).</u>**

Please check the separate procedure manual for usage instructions.

---

### **[M Course Notion**, etc., and post the link and summary to Slack, but strict formatting is not designated.
*   Page 20] 10. Excellence Awards**

Those who engage in excellent initiatives in the competition will be commendedPlease refrain from sharing the entire model output.

Analysis of other participants, disclosure of your own methods, introduction of methods.

**Selection Conditions for Excellence Award are as follows:**
*   Targets are those who have observed the rules of the, battle diaries, code, etc., information related to the competition is welcome, including failures.
Students, please verify Advanced Comp and Main Comp.
*   In addition to the final score, submission contents will be added and selected.
*   **Submission of development documents is required.**
    *   You will be asked to submit a development document explaining the model posts you think are good with an emoji (💜).
Also, we have prepared a Contribution Award to praise those who made such posts and contributed to the competition.

---

### **[Page 19] Contribution Award Rules**

 development process on Notion.
    *   *We will contact you separately regarding the content of the development document.*

*\**   **<u>Only posts made in the dedicated channel are eligible for the award.</u>**
*   The target period is fromSelection conditions are subject to change.*

**The selection categories are planned as follows:**
*   **<u>General Category</u>** the start of the Main Comp to the day before the competition ends.
    *   2026/02/0
    *   Max 20 people from Advanced Comp
*   **<u>U-29 Category</u>**
2 (Mon) 12:00 ~ 2026/03/01 (Sun) 2    *   Max 5 people from Advanced Comp or Main Comp
    *   Limited to students aged 293:59
*   The Main Comp and Advanced Comp are both eligible for posts.
*   Eligible or under (from elementary school students to graduate students)
*   **<u>U-18 Category</u>**
    *    Posts
    *   If there is no Notion link, only the text post is eligible.
    *   RepliesA few people from Advanced Comp or Main Comp
    *   Limited to students aged 18 or under (High are not eligible.
*   If a violation is discovered in the competition, that participant loses eligibility for the Contribution Award. school 3rd year or below) or technical college 3rd year or below.

Announcement of Excellence Awards and details are
*   If the poster does not follow the posting rules or Contribution Award rules, they are not eligible for the Contribution Award scheduled for the Final Results Presentation.

**11. Posting on Dedicated Channels & Contribution Awards**

**<u>Posting Rules</u>**.

**The Contribution Award categories are the following two:**

**<u>Contribution Department Award</u>**
Maximum 5 people selected under the following conditions:
*   Those with a high count of 💜 emojis.
*   If a single user makes
*   We have prepared a dedicated channel for sharing competition information on the Slack of the Matsuo Lab LLM Community.
    *   `#12_llm2025_competition_discussion`
*    multiple posts, the count of 💜 is not summed up; only the post with the highest number is considered.
*   We invite posts related to the competition here.
*   We assume you will write on **LLM Course Notion**,Only the emoji 💜 is counted.

**<u>Contribution Department Special Award</u>**
Maximum 5 people selected under the etc., and post the link and summary to Slack, but strict format is not specified.
*   Please refrain from sharing the following conditions:
*   Among articles posted in the dedicated channel, those highly evaluated by the lecturers of the LLM entire model output.

Analysis of other participants, disclosure of your own methods, introduction of methods, diary, code, etc., course.

We will commend those who shared insights in model development and contributed to many people.
Those participating in the Contribution category, please actively post in the dedicated Slack channel.
Other students, please actively evaluate with emojis.

*Announcement and information related to the competition is welcome, including failures.
Fellow students, please press an emoji (💜) on posts you think are details of the Contribution Award are scheduled to be announced at the Final Results Presentation.*

### **12. Schedule and good.
We have prepared a Contribution Award to praise those who made such posts and contributed to the competition.

---

### Deadlines for Deliverables**

**2026/01/28 (Wed) 21 **[Page 21] Contribution Award Rules**

*   **<u>Only posts made in the dedicated channel are:00 ~ 21:30:**
*   Competition Briefing held.
*   Start of eligible for the award.</u>**
*   The target period is from the start of the Main Comp to the day before the Advanced Comp participation entry via [Google Form].

**2026/02/02 (Mon) 12:00:**
*   Opening of Main Comp, and publication of Completion Requirement Score.
*   Deployment of competition ends.
    *   2026/02/02 (Mon) 12:00 administration materials.
*   Start accepting article posts on the dedicated channel for the Contribution Award.

**2026/02/04 (Wed) 23:59:**
*   Close of Advanced Comp participation acceptance - 2026/03/01 (Sun) 23:59
*   Posts in the Main Comp and Advanced Comp (both) are eligible.
*   Eligible Posts
    *    via [Google Form].

**2026/02/08 (Sun) 17:If there is no Notion link, only the text of the post is eligible.
    *   Replies are not eligible.
00:**
*   Based on the Main Comp model submission status at this point, Advanced Comp selectors will be decided.

**2026/02/09 (Mon) 12:00:**
*   If a violation is discovered in the competition, that participant loses eligibility for the Contribution Award.
*   If the poster does*   Opening of Advanced Comp, and deployment of administration materials.
*   **<u>The Main Comp continues even after not observe the posting rules or Contribution Award rules, they will not be eligible.

The categories for the Contribution Award are the the Advanced Comp starts. Submission to achieve completion requirements is possible until 3/2.</u>**

**2026 following two:

**<u>Contribution Category</u>**
Up to 5 people selected under the following conditions:
*   /03/01 (Sun) 23:59:**
*   Close acceptance of article posts on the dedicated channel for the Contribution Award.

**2026/03/02 (Mon) Those whose number of 💜 emoji presses by users was high.
*   If a single user makes multiple posts, the number of 💜 is not summed up; only the post with the highest number is considered.
*   Only the 💜12:00:**
*   Close of Main Comp & Advanced Comp. After this, Main Comp deliverables (json file, HuggingFace URL) and Advanced Comp deliverables (csv) cannot be submitted, so please be careful.
* emoji is counted.

**<u>Contribution Special Category</u>**
Up to 5 people selected under the following conditions:   We will not accept submissions or replacement requests after the deadline, so please be careful.
*   **<u>Errors may
*   Among the articles posted on the dedicated channel, those highly evaluated by the lecturers of the LLM course. occur due to concentrated access near the deadline, so we recommend submitting with time to spare.</u>**
*   **

We will commend those who shared insights in model development and contributed to many people.
Those participating in the Contribution Category, please strictly<u>Especially for the Advanced Comp, since scoring may become heavy, we recommend early scoring.</u>**

*Requests for creation post in the Slack dedicated channel.
Other students, please actively evaluate with emojis.

Announcement and details of the Contribution Award are scheduled to be announced at the Final Results Presentation.

---

### **[Page 22]  of development documents for the Excellence Award will be communicated later.*

**Mid-March 2026:**
*   Final12. Schedule and Deadlines**

**2026/01/28 (Wed)  Results Presentation (Main Comp & Advanced Comp).
*   After scrutinizing results, Excellence Awards will be announced.
*   21:00 - 21:30:**
*   Competition Briefing held.
*   Advanced Comp participation entry starts via [Google Form].

**2026/02/02 (Mon)Contribution Awards will be announced.

---

### **[Page 20] Supplementary**

### **How to Obtain Hugging 12:00:**
*   Main Comp opens, and baseline score (completion requirement) released.
*   AdministrationFace Token (READ / WRITE)**

To save your own models or datasets to Hugging Face, or to change settings, a materials distributed.
*   Acceptance of article posts on the dedicated channel for the Contribution Award begins.

**2026/02/04 (Wed) 23:59:**
*   Advanced Comp "Token" for writing is required. In the Main Comp standard code, a **WRITE** permission is required to upload the model. Also, running the evaluation system in the Advanced Comp requires **READ** permission.

**Important Warning**
A token is the same participation acceptance via [Google Form] closes.

**2026/02/08 (Sun) as a "Password". If this token becomes known to others, there is a fear that your repository will be overwritten arbitrarily.
Please be careful not to paste it directly into GitHub, etc., and publish it.

**Procedure**
1.  Log in to Hugging Face (https://huggingface.co/).
2.  Click on 17:00:**
*   Based on the Main Comp model submission status at this point, Advanced Comp selectors are your icon at the top right of the screen.
3.  Select **Settings** from the menu.
4 decided.

**2026/02/09 (Mon) 12:00:**
.  Click **[Access Tokens]** in the side menu on the left.
5.  Click the ***   Advanced Comp opens, and administration materials distributed.
*   **<u>The Main Comp continues even after the Advanced Comp[+ Create new token]** button located near the center of the screen.
6.  A settings window will starts. Late submission for obtaining completion requirements is possible until 3/2.</u>**

**2026/0 open, so enter/select the following items:
    *   a. **Token Name:** Give it a name3/01 (Sun) 23:59:**
*   Acceptance of article posts on the dedicated channel for the Contribution Award closes.

**2026/03/02 (Mon)  easy for you to understand (e.g., `my-token`, etc.).
    *   b. **Token type:** Select one according to the purpose.
        *   i. **<u>Read: For Reading Only</u>**
            *   12:00:**
*   Main Comp & Advanced Comp close. After this, Main Comp deliverables (json file, HuggingFace URL) and Advanced Comp deliverables (csv) cannot be submitted, so please be careful.
*1. Use when only downloading models or data, or viewing private repositories.
            *   2. Use this for the Advanced Comp evaluation.
        *   ii. **<u>Write: For Writing</u>**
            *   1   We do not accept submissions or replacement requests after the deadline.
*   **<u>Errors may occur due to concentrated access near the deadline, so we recommend submitting with time to spare.</u>**
*   **<u>Especially for the Advanced Comp,. Use when uploading your own model or editing a repository.
            *   2. Use this in the Main Comp standard code. Finally, press the **[Create token]** button at the bottom to complete.
7.  Click ** there is a possibility that scoring will become heavy, so we recommend early scoring.</u>**

*\*We will contact you laterCopy** next to the created token to copy the token.
    *   a. Paste the copied string into a regarding the request for creating development documents for the Excellence Award.*

**After mid-March 2026:** memo, etc., and keep it safe.

### **About Licenses**

*Please understand this as a **general
*   Final Result Presentation (Main Comp / Advanced Comp).
*   After scrutinizing the results, Excellence Awards will social rule**, not limited to this competition.*
*In this section, explanation is kept to the minimum necessary for participating be announced.
*   Contribution Awards will be announced.

---

### **[Page 23] Supplement in the competition.*
*Those who wish to learn in detail, please refer to the references listed at the end of this section.*

**Caution**
*   The author does not possess qualifications to provide legal advice.
*   Also**

**How to obtain a HuggingFace Token (READ / WRITE)**

To save your own models or datasets to, accuracy of the content is not guaranteed. We cannot compensate for any damages arising from the content described here.

** Hugging Face or change settings, a "Token" for writing is required. In the standard code for the Main Comp,1. What is a "License" in the first place?**
"License" is a rule where the copyright a **WRITE permission** is required to upload the model. Also, running the evaluation system in the Advanced Comp requires a **READ permission holder permits the exercise of exclusive rights under certain conditions in the future. Generally, a "License" forces permission saying "**You may do**.

**Important Note**
A token is like a "password". If this token becomes known to others, there is a a certain act**" (**permission**) and "**Its conditions**".

In the context of intellectual property, regarding copyrighted fear that your repository will be overwritten arbitrarily.
Please be careful not to paste it directly into GitHub etc. and make it public.

**Procedure**
1.  Log in to Hugging Face ([https://huggingface.co/ works (software, data, model weights, etc.), "How can I use it?", "How far is it allowed](https://huggingface.co/)).
2.  Click on your icon at the top right of the screen.
?", "What must I protect?" are explicitly indicated by the right holder, which is the license.

**2. Major3.  Select **Settings** from the menu.
4.  Click **[Access Tokens]** in the left Principle: Do not use if the license is unclear**
Many public models, data, and codes indicate the usable scope with side menu.
5.  Click the **[+ Create new token]** button near the center of the screen.
 "License" or "Terms of Use (Terms)". **Be sure to check before use, and if unclear/ambiguous/acquisition6.  A settings window will open, so enter/select the following items:
    *   a. Token route is suspicious, do not use** is the safety principle. Practically, think "**If no license is written, usability Name: Give it a name easy for you to understand (e.g., my-token, etc.).
     is low**".

**3. Three Checkpoints to hold from a Competition Perspective**
In this competition, please*   b. Token type: Please select either depending on the purpose.
        *   i. **<u>Read: Read- be sure to check the following 3 points regarding licenses.

*   **Commercial Use Permitted?**
    *only</u>**
            *   1. For downloading models or data, or viewing private repositories only.
            *   2   *Basically not relevant for this competition, but important looking ahead to future publication.*
*   **Is there a. Use this for the Advanced Comp evaluation.
        *   ii. **<u>Write: Read and Write</u>**
 License Inheritance Obligation (Copyleft)?**
    *   Need to inherit the same license upon derivatives or redistribution?            *   1. When uploading your own model or editing a repository.
            *   2. Use this in the Main Comp standard code.
        *   Finally, press the **[Create token]** button at the bottom to
*   **Can it be used for Learning / Distillation / Synthetic Data Generation?**
    *   Check complete.
7.  Click **Copy** next to the created token to copy the token.
    *    not only the license but also **Terms of Use**.

**4. In LLM Development, what does the license attach to?**
*   **<u>Code (Training/Inference/Evaluation scripts, libraries)</u>**
    *   Software licenses likea. Paste the copied string into a memo pad etc. and keep it safe.

**About Licenses**
**\* MIT / Apache-2.0 / BSD / GPL / MPL apply.
*   **<u>Data (Training dataPlease understand this as a general social rule, not limited to this competition.**
*Here, we limit the explanation to the minimum, evaluation data, data used for synthesis, collected URL lists, etc.)</u>**
    *   **Important Caution necessary for participating in the competition.
Those who want to learn in detail, please refer to the references listed at the end of:**
        *   **The license of the entire dataset and the origin/license of individual data inside do not necessarily this section.*

**Caution**
*   The author does not hold qualifications to give legal advice.

---

### ** match.**
    *   **Common NG (No Good) example in practice: Believing only the Data Card notation is[Page 24] Supplement - About Licenses**

*   Also, accuracy of the content is not guaranteed. dangerous.**
        *   Data card says "CC0", "MIT", "CC BY", etc., loosely.
        * We cannot compensate for any damages arising from the content described here.

**1. What is a "License" in the   But looking inside, it's synthetic data generated by ChatGPT / OpenAI API, etc.
        *   -> OpenAI's Terms of Use prohibit **developing a competing model using output** (with limited exceptions).
        *    first place?**
A "License" is a rule where the copyright holder allows the exercise of exclusive rights in the future under certain-> In other words (regardless of the Data Card notation), that synthetic data cannot be used for LLM development.
 conditions.
Generally, a "License" forces **"You may do a certain action (permission)"** and **"its*   **<u>Model (Weights/Parameters)</u>**

---

### **[Page 21] About conditions"**.

In the context of intellectual property, regarding copyrighted works (software, data, model weights, etc.): Licenses (Continued)**

*   **<u>Output (Deliverables):</u>**
    *   Example: Synthetic data, generated text, logs, deliverables.
    *   Caution regarding output:
        *   Separate from the copyright of the generated
"How can I use it?", "How far is it allowed?", "What must I protect?"
A license is something object itself, "How to use the output" may be restricted by the model's Terms of Use / License. where the **right holder has explicitly indicated** these things.

**2. Major Principle: Do not use things with unclear licenses**
Many public models, data, and code indicate the scope of availability in "Licenses" or "Terms of
        *   (Especially cases like "Do not use output for learning", "Cite this explicitly", etc.)
    *   **Points to be especially careful about:**
        *   **Can I reuse the output as training data?** Use (Terms)".
**Make sure to check before use, and if it's unclear/ambiguous/acquisition
        *   **Can I improve other LLMs with the output?**
        *   In Proprietary Models route is suspicious, assume "Do not use" or "High possibility it cannot be used".**

**3. Three (ChatGPT / Gemini, etc.), **there are cases where using generated data for creating competing models is restricted.**

**5. checkpoints to keep in mind from a competition perspective**
In this competition, please be sure to check the following 3 points Infectiousness (Viral Nature) of Licenses**
In LLM development, the influence of licenses often comes from the following two systems: regarding licenses.

*   **Commercial Use Allowed?**
    *   *Although basically irrelevant in this competition, it
*   Restrictions from Copyright Licenses
    *   GPL / AGPL / MPL
    *   CC BY-SA is important considering future publication.*
*   **Is there a License Inheritance Obligation (Copyleft)?**
    *
*   Restrictions from Terms of Use / Contracts / Policies
    *   Contractual inheritance obligations to derivative models
   Whether it is necessary to inherit the same license when creating derivatives or redistributing.
*   **Can it be used    *   Display obligations
    *   Prohibitions on learning/distillation

**If synthetic data is generated using for Training / Distillation / Synthetic Data Generation?**
    *   Check not only the license but also the ** an LLM, software license copyleft is not necessarily automatically inherited by the data. On the other hand, usage of output and usage for learning may well be restricted by the model's Terms of Use and Additional Terms (AUP / Terms).**

In conclusion, **please be sure to check BOTH the "License + Terms of Use" of the model used for generation.**Terms of Use**.

**4. Where does a license attach in LLM development?**

*   **<u>Code (Training/Inference/Evaluation scripts, Libraries)</u>**
    *   Software licenses such as MIT / Apache-2.0 / BSD / GPL / MPL apply.
*   **<u>Data (Training Data, Evaluation Data, Data

**6. List of Famous Licenses**
Copyleft Free (Permissive)
*   MIT
*   Apache  used for synthesis, Collected URL lists, etc.)</u>**
    *   **Important Note:**
        *   **The license2.0
*   BSD-2, BSD-3
Copyleft Exists (Viral)
*   G of the entire dataset and the origin/license of individual data inside do not necessarily match.**
    *   **CommonPLv3
*   AGPL
*   MPL-2.0
*   CC BY-SA "No-Go" (NG) example in practice: Dangerous to believe only the Data Card description**
        * (*Note: License primarily for documents/data*)

Licenses for Models / Weights (*Many possess unique clauses*)
*   Llama 3.1 community license
*   Qwen license

**7. Summary**
*   **   The Data Card says "CC0", "MIT", "CC BY", etc., loosely.
        *   But lookingAlways check the license/terms of use for each tool, model, and data used.**
*   **If multiple copy inside, it's synthetic data generated by ChatGPT / OpenAI API, etc.
        *   => OpenAI's Terms ofleft licenses are involved, there is a possibility that incompatible combinations make distribution impossible. In that case, measures such as avoiding the Use **prohibit developing models that compete using the output** (with limited exceptions).
        *   => In other words combination / finding alternative materials are necessary.**
*   **Practically for the Competition...**
    *   In the, regardless of the Data Card description, that synthetic data cannot be used for LLM development.
*   **<u> whitelist models this time, we have selected those with relatively loose licenses usable for synthesis and distillation.
    *   However, **<u>Model (Weights, Parameters)</u>**

---

### **[Page 25] Supplement - Licenses (Continued)**

please be extremely careful when adding data yourself.</u>**
    *   License information is displayed on the page for Hug*   **<u>Output (Deliverables):</u>**
    *   Example: Synthetic data, generated text, logs, deliverables.gingFace models/datasets, so please be sure to check.

**Reference**
- AI and License/Copyright/Legal
    *   Notes regarding output:
        *   Apart from the copyright of the generated object itself, "How to use the System (Lecture by Prof. Yusuke Oda, NII) [Link]
- There are supplementary materials about licenses in the LL output" may be restricted by the model's Terms of Use / License.
        *   (e.g., "M Course 2025 Basic Edition Day 8 materials.

---

### **[Page 22]If using the output for training, include this credit", etc.)
    *   **Especially be careful:**
        *    About Data Creation**

While holding the LLM competition, we frequently receive questions like "Is this permissible data synthesis?", "**Can the output be reused as training data?**
        *   **Can the output be used to improve otherDoes this method correspond to data synthesis?" regarding permitted/prohibited acts of data synthesis.
We will list examples below, LLMs?**
        *   In Proprietary Models (ChatGPT / Gemini, etc.), **there are cases where so please judge "This is data synthesis by LLM" vs "This is data creation using technologies other than LLM using generated data to create competing models is restricted.**

**5. License Propagability (Viral Nature)**
In LLM development".

*Note: "LLM" in this competition includes general models that output text, and so-called Embedding, the influence of licenses often comes from the following two systems:
*   Copyright License derived restrictions
    *    Models that do not output text are not included in this.*

**<u>Example of Data Creation NOT using LLM</u>**
*   Data Cleaning:
    *   Doing the following using regular expressions or scripts:
        *   GPL/AGPL/MPL
    *   CC BY-SA
*   Terms of Use / Contract / Policy derived restrictions
    *   Contract inheritance obligation to derivative models
    *   Display obligations
    *   ProhibDeleting unnecessary characters
        *   Unifying formats
        *   Deduplication
*   Manual Correction:
    *itions on Learning / Distillation

**If synthetic data is generated using an LLM, software license copyleft is not necessarily   Correction of typos, annotation done by humans checking content.
*   Non-Generative Data Augmentation:
    * automatically inherited by the data. On the other hand, usage of the output and use for learning may be restricted by the model   Synonym replacement using thesauruses (WordNet, etc.), adding random noise, and traditional data augmentation methods not relying's Terms of Use and Additional Terms (AUP / Terms).**

Conclusion: **Make sure to check both on LLM inference capabilities.
*   Text processing using models falling outside the definition of LLM stated in this document (Encoder the "License + Terms of Use" of the model used for generation.**

**6. List of Famous Licenses** models like BERT, RoBERTa, DeBERTa, etc.)

**<u>Example of Data Creation (Synthesis) USING
Copyleft: None (Permissive)
*   MIT
*   Apache 2.0
*   BSD- LLM</u>**
*   Using Generative AI models (including APIs and local models) such as OpenAI GPT series, Claude2, BSD-3

Copyleft: Yes (Viral)
*   GPLv3
*   AG, Gemini, Llama, etc., to generate new text data.
*   Using LLM to rewrite existing text (RePL
*   MPL-2.0
*   CC BY-SA (*Mainly a license for documents/phrasing) or summarize it.
*   Using LLM output as teacher data for training.

Thus, the point isdata*)

Model/Weights oriented Licenses (*Many have unique clauses*)
*   Llama 3.1 community:
**<u>"In the process of building data, is an LLM directly involved in creating the data?"</u>** license
*   Qwen license

---

### **[Page 26] 7. Summary & Data Creation**



Examples not using LLM are rule-based processing (regular expressions, string manipulation, template processing) or manual creation (**7. Summary**
*   **Always check the license/Terms of Use for each tool, model, and data you usewriting yourself, manual labeling, annotation).

Examples of Data Creation (Data Synthesis) using LLM are using LLM weights.**
*   **If multiple copyleft licenses are involved, incompatible combinations may become undistributable. In that case, actions (API or local doesn't matter) to make LLM generate text, perform identification, etc.

**FAQ ( such as avoiding the combination / searching for alternative materials are necessary.**
*   **Practically for the competition...**Frequently Asked Questions)**

Q. Is it allowed to have an LLM write "code to process data"?
A. **Yes.** This is considered auxiliary use and is permitted. However, having the LLM create or rewrite the "content of the data
    *   For the whitelist models this time, we have selected those with relatively loose licenses so they can be used for synthesis and distillation.
    *   However, **<u>please be extremely careful when adding data yourself.</u>**
    " itself is prohibited.

Q. Can I use LLM for data quality checks (filtering)?
A. **No (Prohibited).** Judging "Is this data high quality?" by an LLM and using the selected dataset as a result falls*   For HuggingFace models/datasets, license information is displayed on the page, so please strictly check it.

**References**
*   AI and License - Copyright - Legal System (Lecture by Dr. Yusuke Oda, NII) [https://youtu.be/5AlX1SwhJsY](https://youtu.be/5Al under "Dataset construction utilizing LLM knowledge," so it is prohibited.

Also, recently there are many cases where LLM is usedX1SwhJsY)
*   LLM Course 2025 Basic Edition Day 8 Materials contain for translation, but obtaining text with different expressions using these is also a type of synthesis.
(*In this competition, LL supplementary materials about licenses.

**About Data Creation**
When holding an LLM competition, we frequently receive questions regardingM translation and non-LLM translation are uniformly prohibited > 8. Tool Usage in Development*)

### **Ag permission/prohibition of data synthesis, such as "Is this data synthesis by LLM?" or "Does this methodreements in LLM Model Development**

**<u>Let's stop using evaluation data for training</u>**
Training on benchmark fall under data synthesis?".
We will list examples below, so please judge "This is data synthesis by LLM" data or evaluation data intended for testing is like cheating. This makes it impossible to measure whether the model is excellent or not for vs "This is data creation using technologies other than LLM".

*Note: In this competition, "LLM" refers to the benchmark.
This is called "Data Leakage" or "Contamination".

**<u>Let's stop learning all models that output LLM, and so-called encoder models that do not output LLM are not included in this the benchmark data</u>**
For the Main Comp, we ask you to use only the data designated by the administration,.*

**<u>Example of Data Creation NOT using LLM</u>**
*   **Data Cleaning:**
    *    but for the Advanced Comp, participants can freely choose data that has no licensing issues. However, let's stop usingDoing things like the following using regular expressions or scripts:
        *   Deleting unnecessary characters
        *   Unifying data used in the benchmark.
If the data used in the benchmark is unintentionally used, overlapping with the training data for formats
        *   Deduplication
*   **Manual Correction:**
    *   Correction of typos and annotation done evaluation, implies that the model is merely "memorizing" the data, and there is a possibility that its performance is over by humans confirming the content.
*   **Non-Generative Data Augmentation:**
    *   Synonym replacement using thes-evaluated. This also corresponds to Contamination.
You might think "Isn't it fine since the benchmark targets varyauruses (WordNet, etc.), adding random noise, and other data augmentation methods that do not rely on LLM inference this time?", but it is safer to avoid it.

**<u>Let's avoid data creation that is overly conscious of the evaluation power.
*   **Text processing using models that fall outside the definition of LLM stated in this document (Encoder data</u>**
Essentially, model development competitions aim to properly evaluate the generalizability of the model. Therefore, acts of models like BERT, RoBERTa, DeBERTa, etc.)**

**<u>Example of Data Creation (Synthesis) analyzing statistical features of the evaluation data (test data) and creating training data overly adapted to it are considered acts close to data leakage USING LLM</u>**
*   Using Generative AI models (including API and local models) such as OpenAI GPT. It is safer to avoid this.

**Prohibition of excessive analysis:**
Please avoid acts of visual inspection, text series, Claude, Gemini, Llama, etc., to generate new text data.
*   Using LLM to paraphrase mining, distribution analysis, etc., of the evaluation data to reverse-calculate/identify trends (topics, keyword distributions, etc.) existing text (Rephrasing) or summarize it.
*   Using LLM output as teacher data for training. of the evaluation data.

**Restriction on optimization:**
Based on the analysis results above, intentionally creating/selecting training

The point is as follows:
**<u>"In the process of constructing data, is an LLM directly involved data similar to the evaluation data to impair the practical evaluation of the model should be refrained from.

**Permitted Scope:**
 in the data creation?"</u>**

Examples not using LLM: Rule-based processing (regular expressions, string manipulation, template processing), Manual creation (writing it yourself, manual labeling, annotation).

Examples of data creation (data synthesisMinimal data checking such as format confirmation is permitted, but please strictly observe the principle of treating it strictly as "unknown data".
