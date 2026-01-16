Ship-to-Shore Communication Latency Prediction with Environment-aware Multimodal LLMs
=
Dynamic environmental factors, including seasonal weather variations, signal obstructions caused by bridges, and waterway geometry, 
significantly influence end-to-end (E2E) latency prediction in wireless ship-to-shore communications.
To address these challenges, this work presents a Multimodal Environmental Augmented Navigation Dataset (MEAND). 
MEAND integrates heterogeneous multimodal information, including meteorological variables, e.g., wind speed, temperature, and rainfall, 
detailed waterway geometry, and fixed geographic features such as bridges and small islands, all of which directly affect wireless transmission performance.

Dataset Construction
--
<img width="4960" height="2178" alt="QApair_01" src="https://github.com/user-attachments/assets/c25f513a-1fb8-453a-9e4c-fc265d994e14" />
MEAND expands FND by incorporating multimodal environmental information. In particular, inland waterways wind speed, temperature, and rainfall, are considered, as they directly influence wireless data transmission quality. Moreover, we integrate geographic information from the Yangtze waterway bureau, and marked fixed features, such as bridge, waterway geometry, and small islands in inland waterway.

Model Preparation
--
* Qwen/Qwen2-7B-Instruct
* Deepseek-R1-Distill-Qwen-1.5B
* huggyllama/llama-7b

LoRA Configurations
--
<img width="5844" height="2578" alt="lora2_01" src="https://github.com/user-attachments/assets/4a6c9653-09cc-4c16-95d4-b474495cdc5d" />
This subsection constructs a lightweight model for ship-to-shore E2E  communication latency prediction. We select deepseek-R1-1.5B model as foundation model and fune-tuning it with LoRA using our MEAND dataset to adapt the model to latency prediction tasks.

Frequently Asked Questions
--
Q：The dataset appears relatively small. How do you ensure the model's performance isn't due to overfitting on limited data?<br>
A：


Q:The networking aspects and wireless technology details are not clearly described. What specific communication technologies are used?<br>
A:
