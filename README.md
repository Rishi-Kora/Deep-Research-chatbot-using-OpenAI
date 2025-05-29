# Deep Research Chatbot using OpenAI

This repository contains a Jupyter notebook demonstrating a fully automated "Deep Research" agent built with the OpenAI Agents SDK. The agent can plan web searches, summarize findings, compose a cohesive report, and email the results—all with minimal user intervention.

## Features

* **Automated Planning & Search**: Uses a Planner agent to break down research queries into targeted web searches and a Search agent to retrieve concise summaries.
* **Report Generation**: Leverages a Writer agent to synthesize search summaries into a structured, 2-3 paragraph report under 300 words.
* **Email Delivery**: Implements an Email agent powered by SendGrid to automatically send the generated report to a specified recipient.
* **Traceability**: Integrates OpenAI’s `trace` utility for end-to-end visibility into each step of the agent’s decision-making.

## Notebook Structure

1. **Setup & Imports**: Load environment variables, import SDK components, and configure API clients.
2. **Agent Definitions**:

   * `search_agent`: Summarizes web search results.
   * `planner_agent`: Plans a series of targeted searches based on the user’s query.
   * `writer_agent`: Drafts the final research report.
   * `email_agent`: Composes and sends the report via SendGrid.
3. **Planning & Execution Functions**:

   * `plan_searches()`: Generates a search plan.
   * `perform_searches()`: Executes searches and collects summaries.
4. **Report & Email Functions**:

   * `write_report()`: Generates the report from search summaries.
   * `send_email()`: Sends the report as an email.
5. **Execution Example**: Runs a full research cycle on a sample query, e.g., "Latest AI Agent frameworks in 2025."
6. **Tracing**: View detailed run logs on the [OpenAI Traces dashboard](https://platform.openai.com/traces).

## Prerequisites

* Python 3.8+
* An OpenAI API key with Agents SDK access
* A SendGrid API key for email delivery

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Rishi-Kora/Deep-Research-chatbot-using-OpenAI.git
   cd Deep-Research-chatbot-using-OpenAI
   ```
2. Install dependencies:

   ```bash
   pip install agents-sdk python-dotenv pydantic sendgrid
   ```
3. Copy `.env.example` to `.env` and fill in your API keys:

   ```env
   OPENAI_API_KEY=your_openai_key
   SENDGRID_API_KEY=your_sendgrid_key
   EMAIL_SENDER=your_verified_sendgrid_sender@example.com
   EMAIL_RECIPIENT=recipient@example.com
   ```

## Usage

1. Open the Jupyter notebook:

   ```bash
   jupyter notebook Deep_research_using_OpenAI.ipynb
   ```
2. Update the `query` variable in the final cell with your own research topic.
3. Run all cells. The notebook will:

   * Plan and execute web searches
   * Generate a concise research report
   * Email the report

## License

This project is licensed under the [MIT License](LICENSE).
