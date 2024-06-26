# Model Overview

Arctic is a dense-MoE Hybrid transformer architecture pre-trained from scratch by the Snowflake AI Research Team. We are releasing model checkpoints for both the base and instruct-tuned versions of Arctic under an Apache-2.0 license. This means you can use them freely in your own research, prototypes, and products. Please see our blog [Snowflake Arctic: The Best LLM for Enterprise AI — Efficiently Intelligent, Truly Open](https://www.snowflake.com/blog/arctic-open-efficient-foundation-language-models-snowflake) for more information on Arctic and links to other relevant resources such as our series of cookbooks covering topics around training your own custom MoE models, how to produce high-quality training data, and much more.

- **Inputs:** Models input text only.
- **Output:** Models generate text and code only.
- **Model Architecture:** Arctic combines a 10B dense transformer model with a residual 128x3.66B MoE MLP resulting in 480B total and 17B active parameters chosen using a top-2 gating. For more details about Arctic's model Architecture, training process, data, etc. [see our series of cookbooks](https://www.snowflake.com/en/data-cloud/arctic/cookbook/).
- **License:** Apache-2.0.
- **Model developers:** Snowflake AI Research Team.

## Training Data
Snowflake Arctic was pretrained on 3.5 trillion tokens of data from publicly available sources. The fine-tuning data includes publicly available instruction datasets.

## Evaluation Results

| Metric                                   | Value  |
|------------------------------------------|--------|
| MMLU                                     | 67.3   |
| GSM8k                                    | 74.2   |
| Spider                                   | 78.9   |
| IFEval                                   | 52.4   |
| Coding - HumanEval+ & MBPP+ -            | 64.3   |

# Inference samples
Inference type|Python sample (Notebook)|CLI with YAML
|--|--|--|
Real time|<a href="https://aka.ms/azureml-infer-online-sdk-text-generation-dolly" target="_blank">text-generation-online-endpoint.ipynb</a>|<a href="https://aka.ms/azureml-infer-online-cli-text-generation-dolly" target="_blank">text-generation-online-endpoint.sh</a>
Batch |<a href="https://aka.ms/azureml-infer-batch-sdk-text-generation" target="_blank">text-generation-batch-endpoint.ipynb</a>| coming soon

# Sample Inputs and Outputs (for real-time inference)
### Sample Input
```json
{
  "input_data": {
    "input_string": [
      {
        "role": "user",
        "content": "I am going to Paris, what should I see?"
      },
      {
        "role": "assistant",
        "content": "Paris, the capital of France, is known for its stunning architecture, art museums, historical landmarks, and romantic atmosphere. Here are some of the top attractions to see in Paris:\n\n1. The Eiffel Tower: The iconic Eiffel Tower is one of the most recognizable landmarks in the world and offers breathtaking views of the city.\n2. The Louvre Museum: The Louvre is one of the world's largest and most famous museums, housing an impressive collection of art and artifacts, including the Mona Lisa.\n3. Notre-Dame Cathedral: This beautiful cathedral is one of the most famous landmarks in Paris and is known for its Gothic architecture and stunning stained glass windows.\n\nThese are just a few of the many attractions that Paris has to offer. With so much to see and do, it's no wonder that Paris is one of the most popular tourist destinations in the world."
      },
      {
        "role": "user",
        "content": "What is so great about #1?"
      }
    ],
    "parameters": {
      "temperature": 0.6,
      "top_p": 0.9,
      "do_sample": true,
      "max_new_tokens": 200
    }
  }
}
```
### Sample Output
```json
{
  "output": " The Eiffel Tower is an iconic landmark and an engineering marvel. It was built in 1889 and stands at 1,083 feet (330 meters) tall. There are several reasons why the Eiffel Tower is so great:\n\n1. Historical significance: The tower was built for the 1889 World's Fair and was initially intended to be a temporary structure. However, it quickly became a symbol of Paris and was never dismantled.\n2. Architectural beauty: The Eiffel Tower's intricate lattice design and its elegant silhouette make it one of the most recognizable structures in the world.\n3. Engineering marvel: When it was built, the Eiffel Tower was the tallest man-made structure in the world. Its design and construction pushed the boundaries of engineering at the time.\n4. Panoramic views: Visitors can take"
}
```
