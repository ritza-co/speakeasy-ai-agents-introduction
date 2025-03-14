# What are AI Agents? An Introduction

AI agents are the next big step for AI's progress - autonomous AIs that can do work for you. They expand the capability of AI models by giving them agency. Unlike traditional software, AI agents can independently gather context, make informed decisions, and execute tasks without constant human supervision. 

AI agents that use Large Language Models (LLMs) let you automate complex workflows using natural language. You're likely already using such tools without realizing it. For instance, GitHub Copilot's new agent mode doesn't just suggest code - it independently iterates on its own output, infers additional tasks needed to complete the requested task, and even proactively fixes errors.

This article introduces AI agents, it's the first in a series designed to take you from understanding what AI agents are to building your own agentic applications:

- **What are AI Agents? an Introduction** 
- **Optimizing your OpenAPI for MCP Servers**
- **Real World Agent Use Cases**
- **The Architecture of Agentic Applications**
- **The Agentic Ecosystem: Frameworks and Tools**
-  **Integration with Agents**

Let's start by learning about LLM agents.

## What is an LLM Agent?

LLMs, like ChatGPT, are advanced AI systems capable of generating readable text based on input prompts. LLMs are trained using massive datasets and machine learning that recognizes patterns and relationships in the data. When provided with input, LLMs generate text sequentially, producing responses one word or phrase at a time. At each step, the LLM evaluates potential words or phrases, assigning each a likelihood of being next in the sequence, and selects the most probable option. This process typically produces a reasonable response.

AI agents that use LLMs are referred to as LLM agents. They add a layer to LLMs, extending their capabilities by adding autonomous decision-making and giving them action-taking abilities. They are like a digital assistant that you can talk to help you automate complex workflows without constant human supervision. 

## What can AI agents be used for?

An AI agent shouldn't be viewed as general-purpose tool. They're best suited for specific, clearly defined problems or to optimize distinct parts of a workflow. For example, an AI agent specifically optimized to automate deployment processes will outperform an agent tasked with handling numerous unrelated tasks. 

You'll find AI agents integrated into popular coding environments and IDEs such as VS Code, Cursor, JetBrains, Replit, and Windsurf. These AI agents enhance developer productivity by generating code snippets, refactoring code, providing detailed code documentation, fixing bugs, and recommending best practices based on project context. They can also be setup to interact with an external environment, for example they can be used to create GitHub actions to automate dependency audits in your project.

Beyond coding, AI agents like OpenAI's [Operator⁠](https://operator.chatgpt.com/) can browse the web to perform tasks for you. This let's you automate tasks such as filling out forms, ordering groceries, booking flights, and booking accommodation. Such agents streamline workflows and free up valuable time, enabling you to focus on tasks requiring human judgment and creativity.

[Microsoft Copilot Agents](https://support.microsoft.com/en-us/topic/introducing-copilot-agents-943e563d-602d-40fa-bdd1-dbc83f582466) bring AI Agents to Microsoft 365. These AI agents enhance the capabilities of Microsoft 365 Copilot by connecting to your Microsoft 365 organization’s knowledge and data sources. They assist users in performing a variety of tasks and automating repetitive tasks.

AI agents have the potential to play a significant role in fields beyond coding, tech, and personal tasks such as in healthcare. AI agents could assist clinicians by rapidly reviewing patient records, suggesting diagnoses, and propose treatment plans.

Here at Speakeasy we create SDKs for your API's using OpenAPI, which provides a structured format (JSON or YAML) for describing RESTful APIs. 
The quality of your SDK depends on the quality of your OpenAPI spec. Our AI agent Speakeasy Suggest,  which is available through the [Speakeasy CLI](https://www.speakeasy.com/docs/speakeasy-cli/suggest/README) or as a [Github workflow](https://www.speakeasy.com/docs/workflow-reference), is a tool for automatically improving OpenAPI specs. It automatically suggests fixes, applies them, and outputs the modified spec.

## How agents work

AI agents operate by integrating Large Language Models (LLMs) with structured data sources, APIs, and external services to autonomously perform tasks and workflows. To function reliably, agents require clearly defined prompts, structured tool definitions, and well-designed data abstraction layers. These elements ensure agents behave predictably and align closely with user expectations.

Technically, this involves:

- Defining precise instructions (prompts) to guide the agent's decision-making.
- Using structured JSON schemas or tool definitions to standardize interactions with APIs and external systems.
- Implementing robust data abstraction layers or middleware to handle diverse data formats and protocols consistently.
- Leveraging orchestration frameworks to coordinate multiple agent tasks and manage complex workflows seamlessly.

A key standard frequently used in building AI agents is the **OpenAPI Specification**. OpenAPI clearly defines available API endpoints, authentication methods, required parameters, data schemas, and expected responses. Agents utilize these definitions to reliably interact with external services, significantly reducing ambiguity and improving consistency.

Agents themselves vary significantly in complexity, from simple single-purpose tools (like automatic code documentation) to sophisticated multi-agent systems capable of orchestrating complex workflows across numerous services and domains. Regardless of complexity, careful infrastructure preparation and a standardized approach to data abstraction are critical to building effective, production-ready AI agents.

## AI agents vs chatbots

While AI agents and chatbots both utilize AI technology, they differ significantly in complexity and capabilities. Chatbots typically follow predefined scripts or decision trees to handle simple, repetitive interactions, making them suitable for straightforward customer inquiries and basic tasks. In contrast, AI agents leverage advanced language models and integrated APIs to autonomously perform complex workflows and tasks. They can interpret context, make informed decisions, and carry out actions, such as sending emails, without continuous human intervention. Thus, AI agents excel in scenarios requiring deeper reasoning, broader integration with external systems, and greater autonomy.

## Is an AI Agent just an LLM with RAG?

Retrieval-Augmented Generation (RAG) is a technique that combines large language models (LLMs) with external knowledge sources. When using RAG, an LLM retrieves relevant information from a knowledge base or database to generate informed responses, reducing incorrect or "hallucinated" information.

However, an LLM with RAG alone does not constitute an AI agent. An AI agent requires the ability to autonomously act, execute tasks, integrate with APIs, and perform workflow orchestration. RAG primarily enhances the accuracy of responses by pulling relevant external data but does not provide the autonomous decision-making or action-taking capabilities that define AI agents.

In short, while RAG can significantly improve LLM responses, transforming an LLM into an AI agent involves adding layers of structured task execution, decision-making logic, and seamless integrations beyond just information retrieval.

## Are reasoning models AI agents?

No. Reasoning models such as **o3** and **R1** are specialized Large Language Models (LLMs) designed to solve complex problems by decomposing them into smaller, sequential steps—a process often called "chain-of-thought" reasoning. Although powerful for logical deduction, these models lack native capabilities for autonomous action, interaction with external APIs, or workflow orchestration.

In other words, while reasoning models excel at systematically analyzing problems and generating structured solutions, they’re fundamentally passive. They rely entirely on external infrastructure or additional layers to interact with systems or execute tasks beyond producing text outputs. AI agents, by contrast, are explicitly designed with integrated tools and APIs, allowing them to autonomously execute decisions and actions in real-world environments.

Thus, although reasoning models form the cognitive backbone for some agents, by themselves, they do not constitute fully autonomous AI agents.

## AI Agent frameworks

Building an AI agent from scratch can be complicated. To simplify development, frameworks like **LangChain**, **Haystack**, **CrewAI**, and **GooseAI** provide structured environments, tools, and abstractions that allow developers to quickly build and deploy effective agents.

Frameworks like **LangChain** and **Haystack** excel at connecting Large Language Models (LLMs) to APIs and external data sources using standardized interfaces like OpenAPI. LangChain enables rapid prototyping by abstracting complex API interactions, though it relies heavily on community-driven modules and sometimes suffers from inconsistent documentation. **Haystack**, initially designed for search and Retrieval-Augmented Generation (RAG), provides a more structured, production-ready experience. Its modular pipelines clearly outline each component’s role, improving reliability and reducing the need for community-driven workarounds.

Frameworks like **CrewAI** and **GooseAI** focus specifically on **multi-agent architectures**, enabling multiple specialized agents to collaboratively handle complex tasks. With these frameworks, developers can easily build systems where agents communicate and coordinate workflows, each focusing on clearly defined responsibilities.

In contrast, no-code tools such as **Zapier’s AI Agent Builder** let non-technical users create agents through visual interfaces, without writing any code. While these solutions simplify initial development, they offer less flexibility for custom logic or highly tailored scenarios.

Choosing between these frameworks depends on your requirements—LangChain and Haystack provide robust, code-based solutions ideal for detailed integrations and precise control, while no-code options like Zapier’s AI Agent builder are suitable for straightforward automation tasks with less technical complexity.

## What are MCP Servers?

When applications integrate LLMs, these models often require external context—such as user data, real-world information, or data from other systems. The **Model Context Protocol (MCP)**, introduced by Anthropic, provides a standardized method for reliably providing structured context to LLMs.

MCP defines clear standards for structuring requests and responses between LLMs and external tools or APIs. It leverages formats such as **OpenAPI**, simplifying how AI agents interpret APIs, endpoints, authentication methods, and expected data formats.

MCP servers can be hosted locally on your machine or deployed externally, providing flexibility for developers. Applications currently supporting MCP integrations include:

- **Claude desktop app**
- **Cursor**
- **Cline**

Each client provides varying levels of integration and capabilities when connecting with MCP servers.

With MCP gaining popularity, integrating your APIs using standardized protocols is increasingly important for delivering an optimal developer experience—especially as AI agents become central to modern development workflows. Here at Speakeasy, our generated TypeScript SDKs include MCP integrations allowing you to seamlessly expose your APIs to AI agents. To learn more, see our blog post: [Model Context Protocol: TypeScript SDKs for the Agentic AI Ecosystem](https://www.speakeasy.com/post/release-model-context-protocol).

You can also take a look at our tutorial [Building a Model Context Protocol (MCP) server for Discord](https://www.speakeasy.com/post/build-a-mcp-server-tutorial), which demonstrates how to set up an MCP server locally, enabling Claude to interact directly with Discord, read messages, and even automate responses.

## Issues and limitations of AI Agents

One big mistake that's often made is assuming the AI Agent and LLM knows how to handle your data, especially if it's a lot of data, or if it's secure data. It's common to paste all sorts of data into chats and assume it's going to be safe and it's going to be well handled.

The overarching limitation of AI agents is their dependence on careful integration, precise prompting, and thorough validation to ensure reliability. Rather than relying solely on the raw capabilities of LLMs, successful deployment involves meticulous design, structured data handling, and robust safeguards.  

Because the term "agent" covers a wide range of applications, misconceptions about their capabilities and limitations are common. One frequent misconception is the overestimation of their capabilities, believing agents can solve all problems without robust, carefully designed application logic.

Many developers begin experimenting with AI agents using simplistic examples, like basic "weather agents." While easy to build, these demos often fail to highlight the true potential of agents and are frequently seen as unconvincing by experienced developers.

Another critical misconception is that AI agents inherently improve or become more knowledgeable without explicit updates or interventions. In reality, effective AI agents require careful planning, targeted training, ongoing refinement, and thoughtful integration with appropriate data and tools to deliver tangible value in production environments. Understanding and addressing these limitations ensures AI agents are built to solve real-world problems effectively, rather than being viewed as an all-purpose "silver bullet.".

### Achieving Deterministic Output

One significant challenge with deploying AI agents, especially in production environments, is ensuring deterministic and consistent outputs. Large language models (LLMs) may produce varying outputs even with identical inputs, complicating reliability in mission-critical applications. Companies often struggle with this unpredictability, requiring advanced prompting techniques and structured logic to improve consistency.

### Handling Diverse Data Sources and Protocols

Many companies assume their existing APIs—originally designed for web apps, mobile apps, or other integrations—will seamlessly integrate with LLMs without modification. In practice, this often leads to confusion and agent hallucinations, as the models struggle to handle multiple data formats and protocols simultaneously. For example, combining OpenAPI, SQL, GraphQL, and JSON specs within a single agent can overwhelm the model, causing unpredictable outputs.

To avoid these issues, it's essential to build a unified abstraction layer tailored specifically for LLM integration rather than expecting models to directly handle various protocols and data types simultaneously. By standardizing data access and clearly defining API interactions—preferably using OpenAPI as a common, understandable format—developers can greatly enhance agent reliability and minimize confusion.

### Ensuring Security and Compliance

Security and compliance are critical concerns when deploying AI agents, particularly those interacting with sensitive data or external users. Enterprises have stringent data governance requirements, and ensuring AI agents comply with these can be challenging. Effective deployment requires rigorous security frameworks, ongoing monitoring, and clear governance protocols to protect sensitive information. 

If a task in can have potential security or compliance concerns, it may be a good idea to  prevent AI Agents from automatically doing this task and let the user take control. The OpenAI Operator agent uses this strategy.  It is trained to ask the user to take control for tasks that require login, payment details, or when solving CAPTCHAs.

### Overcoming Hallucination and Unreliable Outputs

LLMs can sometimes produce "hallucinations"—incorrect or entirely fabricated information. This poses substantial risks, especially in high-stakes scenarios like healthcare or financial services. Developers must implement comprehensive validation mechanisms, including human oversight and automated fact-checking tools, to mitigate these risks. It's also important to handle errors well to make the AI Agent user friendly.

## Conclusion

AI agents have significant potential to enhance productivity and automate numerous tasks across many industries and workflows. However, achieving this potential requires overcoming real-world challenges. Developers must carefully craft prompts, clearly define tools and APIs, and implement robust data abstraction layers to ensure agents deliver deterministic, reliable results.

Although some companies pursue ambitious general-purpose agents—such as [Devin](https://www.cognition.ai/introducing-devin),  which claims to be the first AI software engineer—this broad approach isn't yet viable due to the unreliable output of AI agents and LLM limitations. Devin's approach of doing everything for you will not work without intervention, for now. More realistically, AI agents will augment developer workflows by automating targeted tasks, allowing developers to focus on higher-value problem-solving activities rather than repetitive tasks.

Multi-agent systems capable of parallel, coordinated operation are also emerging, but most still require significant refinement before becoming fully production-ready. These systems represent exciting future possibilities, particularly for complex, collaborative workflows.

The AI agent ecosystem is rapidly evolving, with new developments such as OpenAPI integrations, Anthropic’s MCP, and locally hosted models promising greater security, performance, and ease of integration. As these tools mature, AI agents will increasingly integrate into everyday developer workflows, augmenting human skills and productivity rather than replacing developers altogether.

Ultimately, the future of AI agents is bright: better tooling, improved models—including locally hosted models—and clear, standardized integrations promise to make AI more reliable, secure, and practical for everyday use.

In the next article of this series, we'll explore how you can optimize your OpenAPI specification specifically for MCP Servers, to further enhance AI agent reliability and performance.