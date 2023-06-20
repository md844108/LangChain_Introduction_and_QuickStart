# LangChain_Introduction_and_QuickStart
## AIM: 
Understanding the LangChain Framework and doing practice on the LLM model and the Chat model
## Summary: 
### Introduction
LangChain is a framework for developing applications powered by language models. It enables applications that are:
Data-aware: connect a language model to other sources of data
Agentic: allow a language model to interact with its environment
The main value propositions of LangChain are:
     1. Components: abstractions for working with language models, along with a collection of implementations for each abstraction. Components are modular and 
        easy- to-use, whether you are using the rest of the LangChain framework or not<br/>
     2. Off-the-shelf chains: a structured assembly of components for accomplishing specific higher-level tasks
        Off-the-shelf chains make it easy to get started. For more complex applications and nuanced use-cases, components make it easy to customize existing chains 
        or build new ones.
### LLMs
The basic building block of LangChain is the LLM, which takes in text and generates more text.
### Chat models
Chat models are a variation on language models. While chat models use language models under the hood, the interface they expose is a bit different: rather than expose a "text in, text out" API, they expose an interface where "chat messages" are the inputs and outputs.
You can get chat completions by passing one or more messages to the chat model. The response will be a message. The types of messages currently supported in LangChain are AIMessage, HumanMessage, SystemMessage, and ChatMessage. ChatMessage takes in an arbitrary role parameter. Most of the time, you'll just be dealing with HumanMessage, AIMessage, and SystemMessage.
### Prompt templates
Most LLM applications do not pass user input directly into an LLM. Usually they will add the user input to a larger piece of text, called a prompt template, that provides additional context on the specific task at hand.
### Chains
Now that we've got a model and a prompt template, we'll want to combine the two. Chains give us a way to link (or chain) together multiple primitives, like models, prompts, and other chains.
The simplest and most common type of chain is an LLMChain, which passes an input first to a PromptTemplate and then to an LLM.
### Agents
Our first chain ran a predetermined sequence of steps. To handle complex workflows, we need to be able to dynamically choose actions based on inputs.
Agents do just this: they use a language model to determine which actions to take and in what order. Agents are given access to tools, and they repeatedly choose a tool, run the tool, and observe the output until they come up with a final answer.
To load an agent, you need to choose a(n):
LLM/Chat model: The language model powering the agent.
Tool(s): A function that performs a specific duty. This can be things like: Google Search, Database Lookup, Python REPL, other chains. For a list of predefined tools and their specifications, see the Tools documentation.
Agent name: A string that references a supported agent class. An agent class is largely parameterized by the prompt the language model uses to determine which action to take. Because this notebook focuses on the simplest, highest level API, this only covers using the standard supported agents.
### Memory
The chains and agents we've looked at so far have been stateless, but for many applications it's necessary to reference past interactions. This is clearly the case with a chatbot for example, where you want it to understand new messages in the context of past messages.
The Memory module gives you a way to maintain application state. The base Memory interface is simple: it lets you update state given the latest run inputs and outputs and it lets you modify (or contextualize) the next input using the stored state.


## References
  Introduction: https://python.langchain.com/docs/get_started/introduction<br/>
  QuickStart : https://python.langchain.com/docs/get_started/quickstart

## Requirement OpenAI key
Open OpenAI website(https://platform.openai.com/account/api-keys) and create key , It will use in code.
SerpAPI Key website(https://serpapi.com/manage-api-key) and create key , It will use in code.
## Install some pckages on which our dependency

        !pip install openai
        !pip install langchain
        !pip install google-search-results
 
## To Run Code 
        Here, I'm using Jupyter Notebook to write code so you can run code to select cell from above to down.
