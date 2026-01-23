Ship-to-Shore Communication Latency Prediction with Environment-aware Multimodal LLMs
=
Dynamic environmental factors, including seasonal weather variations, signal obstructions caused by bridges, and waterway geometry, 
significantly influence end-to-end (E2E) latency prediction in wireless ship-to-shore communications.
To address these challenges, this work presents a Multimodal Environmental Augmented Navigation Dataset (MEAND). 
MEAND integrates heterogeneous multimodal information, including meteorological variables, e.g., wind speed, temperature, and rainfall, 
detailed waterway geometry, and fixed geographic features such as bridges and small islands, all of which directly affect wireless transmission performance.

Dataset Construction
--
<img width="1213" height="663" alt="64e2d5c4bcfc710033a9ce8e6afa2e8" src="https://github.com/user-attachments/assets/7d1388ef-6a5a-4269-8be9-03dc2f2fe824" />

<img width="4960" height="2178" alt="QApair_01" src="https://github.com/user-attachments/assets/c25f513a-1fb8-453a-9e4c-fc265d994e14" />
MEAND expands FND by incorporating multimodal environmental information. In particular, inland waterways wind speed, temperature, and rainfall, are considered, as they directly influence wireless data transmission quality. Moreover, we integrate geographic information from the Yangtze waterway bureau, and marked fixed features, such as bridge, waterway geometry, and small islands in inland waterway.

Model Preparation
--
* Qwen/Qwen2-7B-Instruct
* Deepseek-R1-Distill-Qwen-1.5B
* huggyllama/llama-7b

LoRA Configurations
--
This subsection constructs a lightweight model for ship-to-shore E2E  communication latency prediction. We select deepseek-R1-1.5B model as foundation model and fune-tuning it with LoRA using our MEAND dataset to adapt the model to latency prediction tasks.

Frequently Asked Questions
--
Q1：The dataset appears relatively small. How do you ensure the model's performance isn't due to overfitting on limited data?<br>
A1：Collecting large-scale, fine-grained measurement-based data for inland waterway communications is inherently challenging due to practical constraints, such as limited infrastructure, complex waterway geometry, seasonal effects, and dynamic environmental conditions. These factors explain why datasets in this domain are typically limited in size. Notably, the data collected in this work are aggregated hourly, with each point representing a statistical characteristic (e.g., average or weighted latency) rather than a single-time instantaneous measurement. This aggregation reduces random noise and short-term fluctuations, thereby enhancing information accuracy and reliability. Moreover, to mitigate overfitting, we integrate Dropout regularization into our neural network architecture [1]. During training, this technique randomly deactivates a subset of neurons in each layer, encouraging the model to learn robust and generalizable features.


Q2: The networking aspects and wireless technology details are not clearly described. What specific communication technologies are utilized?<br>
A2: The system employs a heterogeneous networking architecture. In near-shore and inland waterway scenarios, 4G/5G cellular networks can support high data rate services, while the QUIC protocol ensures efficient, reliable, and low-latency data transmission over these wireless channels. AIS regularly broadcasts essential navigation information, and in some situations, satellite uses RTK positioning to provide high-precision positioning and time synchronization.

<img width="3956" height="2220" alt="插图_01(1)" src="https://github.com/user-attachments/assets/f5972fc4-d15c-44fe-9321-027a255d154e" />

[1] Y. Lin, X. Ma, X. Chu, Y. Jin, Z. Yang, Y. Wang, and H. Mei, “LoRA Dropout as a sparsity regularizer for overfitting control,” arXiv preprint arXiv:2404.09610, 2024.



