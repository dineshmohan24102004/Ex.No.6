# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date:11/4/2025
# Register no.212222040039
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

## Python for Multi-AI Tool Integration and Automation
## Introduction
Developing Python code compatible with multiple AI tools is essential for enhancing automation and insight generation. Integrating diverse AI APIs enables streamlined data collection, output comparison, and actionable analysis within a unified framework. This approach improves efficiency by automating interactions with various AI models, reducing manual overhead and enabling rapid experimentation.
Such integration proves particularly valuable in scenarios like AI-powered chatbots, where combining strengths of different models can enhance customer support capabilities. Additionally, employing a multi-AI integration strategy supports robust experimental setups by facilitating comprehensive performance evaluation and insight derivation.
Ultimately, this methodology aims to simplify complex workflows by providing a cohesive Python interface that orchestrates multiple AI services seamlessly.
## Designing the Python Code for Multi-API Integration
The Python code architecture for integrating multiple AI tools begins with utilizing robust libraries such as requests for RESTful API communication or official SDKs provided by AI service vendors. Authentication is managed securely through API keys or OAuth tokens, stored safely using environment variables and accessed via configuration files to prevent exposure.
To handle API interactions efficiently, the design supports both asynchronous calls—using Python’s asyncio module or libraries like aiohttp—and sequential requests depending on the required workflow, thus optimizing response times and throughput.
Responses from each AI service are stored in structured data formats such as dictionaries or custom classes, which encapsulate metadata and output content, easing later comparison and analysis. Error handling includes retry mechanisms for transient failures, and rate limiting is addressed by implementing backoff strategies to comply with each API’s usage policies.
## Implementation Details and Code Example
The Python implementation automates interaction with multiple AI APIs by abstracting request sending, response parsing, and result aggregation into modular functions. This structure ensures compatibility across APIs with differing endpoints and response formats.
Below is a simplified example demonstrating integration with two AI services: OpenAI’s GPT and a hypothetical sentiment analysis API. The send_request function handles HTTP POST requests with appropriate headers and payloads. Responses are parsed using JSON decoding tailored to each API's output schema, and results are stored in a dictionary for easy comparison.
```
\*
import requests
import os def send_request(url, headers, payload):
response = requests.post(url, headers=headers, json=payload)
response.raise_for_status()
return response.json()
 # OpenAI GPT API call openai_url = "https://api.openai.com/v1/chat/completions"
 openai_headers = {"Authorization": f"Bearer {os.getenv('OPENAI_API_KEY')}"}
 openai_payload = { "model": "gpt-4", "messages": [{"role": "user", "content": "Explain AI integration in Python"}] }
 gpt_response = send_request(openai_url, openai_headers, openai_payload)
gpt_output = gpt_response["choices"][0]["message"]["content"]
# Sentiment Analysis API call sentiment_url = "https://api.sentiment.example/analyze" sentiment_headers = {"Authorization": f"Bearer {os.getenv('SENTIMENT_API_KEY')}"}
sentiment_payload = {"text": gpt_output}
sentiment_response = send_request(sentiment_url, sentiment_headers, sentiment_payload)
sentiment_score = sentiment_response["results"]["sentiment_score"]
# Aggregated results results = { "gpt_output": gpt_output, "sentiment_score": sentiment_score }
\*
```
This approach highlights handling different API authentication schemes, request formats, and parsing logic within a unified framework, facilitating extensibility to additional AI tools and automated comparative analysis.
## Comparing Outputs from Different AI Tools
Effective comparison of outputs generated by multiple AI tools requires standardized methodologies to evaluate and interpret their responses. One foundational technique is semantic similarity measurement, which quantifies how closely the meanings of texts align, using metrics such as cosine similarity on vector embeddings. Keyword extraction further aids comparison by identifying salient terms within outputs, enabling thematic alignment and topic coverage analysis.
To ensure consistent evaluation, normalizing output formats is critical—this includes stripping extraneous metadata, unifying text casing, and standardizing punctuation. Ranking algorithms can then be applied to prioritize responses based on relevance, coherence, or confidence scores.
Finally, summarization or visualization techniques, such as heatmaps or side-by-side tables, facilitate intuitive examination of differences, supporting more informed decisions in multi-tool environments.
## Generating Actionable Insights from AI Interactions
Translating analyzed data and comparative outputs into actionable insights involves interpreting variations in AI model responses to identify the best-performing tool for specific tasks. Strategies include benchmarking metrics such as response relevance, accuracy, and sentiment alignment. By examining these factors, developers can pinpoint strengths and weaknesses across models.
For example, in optimizing an AI-powered chatbot, insights derived from comparative analysis may guide adjustments in prompt design or model selection to enhance response quality. Similarly, identifying patterns in customer support workflows can inform automation priorities, reducing response time and increasing user satisfaction.
These insights empower data-driven decisions that improve system effectiveness and user experience through targeted refinement of AI interactions.
3
## Scenario-Based Example: AI-Powered Customer Support Chatbot
This case study demonstrates the developed Python code applied to an AI-powered chatbot designed to support retail customer inquiries. The solution integrates multiple AI tools: one for natural language understanding and generation, another for sentiment analysis, and a third for product recommendation. The Python code orchestrates API calls concurrently, collects and compares outputs to ensure comprehensive response quality.
Example prompts include inquiries about order status, product features, and return policies. Typical outputs are synthesized chatbot replies coupled with sentiment scores to gauge customer satisfaction. Comparative analysis highlights strengths, such as more empathetic language from the natural language model, while identifying areas for improvement like response latency.
Images illustrating the system architecture, sample conversation flows, and comparative performance charts complement this study, guiding iterative enhancements toward more efficient and user-friendly customer interaction.

# Result: The corresponding Prompt is executed successfully.
