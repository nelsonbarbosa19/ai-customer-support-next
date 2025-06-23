# AI-Powered Customer Support Platform: (Next.js + Hybrid AI)

## 1. Goals
Real-time chat between customers and support agents (human + hybrid AI assistant).

- AI assistant that answers FAQs, analyzes basic financial questions, and can transfer to human agents
- Modern, responsive web interface for end customers
- Backend with MCP architecture for AI decoupling
- WebSockets for real-time interaction
- Scalability considered from the start

## 2. Core Features

### Frontend
- Simple or simulated login
- Real-time chat interface: messages, history, notifications
- Modular UI: Web Components + Tailwind
- Documented/tested components in Storybook

### Backend
- Next.js API (Serverless or API Routes)
- MCP architecture to connect:
  - **Model** (AI provider, e.g., OpenAI GPT or custom models)
  - **Context** (session, customer data, conversation history)
  - **Protocol** (WebSocket for chat, HTTP fallback)
- Simple authentication (JWT token)
- Logs and metrics for analysis

## 3. Key Technologies

| Layer              | Technology / Library                          |
|--------------------|-----------------------------------------------|
| Frontend           | Next.js + React + Web Components + Tailwind CSS + Storybook |
| Backend            | Next.js API Routes / Serverless Functions / Node.js |
| Communication      | WebSockets (e.g., Socket.IO or ws)            |
| AI                 | OpenAI GPT-4 (Chat completions) / Custom MCP API |
| Authentication     | JWT / Simplified OAuth              |
| Infrastructure     | Vercel / AWS Lambda / Cloudflare Workers      |

## 4. MCP Architecture Implementation

### Model:
- Interface to send prompts and receive AI responses (provider-agnostic)
- May include fallback logic, moderation, and post-processing

### Context:
- Maintains chat state, customer profile, banking context (e.g., balance, products, rules)
- Can use Redis for fast caching and persistence

### Protocol:
- Defines frontend communication:
  - WebSocket for bidirectional real-time exchange
  - REST API for fallback or non-real-time actions

## 5. Project Structure (Simplified)
### ai-customer-support-next:
- **/components**: Contains all reusable UI components built with Web Components
- **/pages**: Next.js page routes including login and chat interfaces
- **/api**: Backend API routes following MCP architecture
- **/mcp**: Core implementation of the Model-Context-Protocol pattern
- **/public**: Static files like images, fonts, and icons
- **/storybook**: Component documentation and testing environment
- **tailwind.config.js**: Tailwind CSS configuration file
