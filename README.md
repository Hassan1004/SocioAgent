# SocioAgent

### "Your personal on-chain agent across socials"

## 🚀 Overview

SocioAgent bridges the gap between Web2 and Web3, enabling seamless interaction between social media and blockchain. With SocioAgent, you can link your wallet to your Twitter account, perform transactions using social identities, share your portfolio, and monitor assets—all from a single platform.

## 🛑 The Problem

- We spend **1/10th of our day** on social media, but Web2 and Web3 remain disconnected.
- Managing multiple wallets, switching accounts, and navigating different blockchain ecosystems is inefficient.
- The constant need for manual identity management slows down Web3 adoption.

## 💡 Why SocioAgent?

- **Personal On-Chain Agent:** Link your wallet to your Twitter and automate on-chain interactions.
- **Cross-Chain Templates:** Create and share transaction templates across multiple chains.
- **Social ID Transactions:** Execute blockchain transactions directly via social identities.
- **Portfolio & Market Insights:** Track your portfolio, monitor coins, and access real-time insights.

## 🛠️ How to Use SocioAgent (End-User Flow)

SocioAgent offers a streamlined experience for interacting with the blockchain through your social media. Here's a typical user flow:

1.  **Install the Browser Extension:**
    *   Begin by installing the SocioAgent Chrome extension. This extension is your primary interface for interacting with the AI agent from social media platforms.
    *   The extension will display your linked Twitter ID and associated CDP wallet details (UUID and address).

2.  **Link Your Twitter Account & Wallet:**
    *   Upon first use (or if not yet linked), the extension helps you connect your Twitter account.
    *   Behind the scenes, SocioAgent securely generates a **CDP (Coinbase Developer Platform) Wallet** for you using **AgentKit**. This wallet is associated with your Twitter identity via a unique UUID.
    *   You can also link existing wallets for broader functionality.

3.  **Interact via the Extension on Social Media (e.g., X.com):**
    *   **Contextual Actions:** While browsing X.com, you can select text (e.g., another user's Twitter handle, a token name, an amount) and right-click to activate "AI action with SocioAgent."
    *   **Natural Language Commands:** The selected text, along with your command (e.g., "send 0.1 ETH to @selectedUser", "show me info about $TOKEN"), is sent to the SocioAgent AI backend.
    *   **Composing Tweets/Replies:** The AI can also help compose tweets or replies. For instance, if you want to post a payment link or a donation frame, the AI can generate the necessary `<emb ... emb>` tag, which the content script then renders as an interactive iframe.

4.  **AI Agent Processing & On-Chain Execution:**
    *   The backend AI agent, powered by OpenAI and Langchain, interprets your request.
    *   It utilizes **CDP AgentKit** and its associated tools to perform actions on the **Base-Sepolia** network using your linked CDP wallet.
    *   For actions on other supported chains like Flow or Starknet, it uses dedicated tools.
    *   **Examples:**
        *   "Send 0.01 ETH to @friendOnTwitter on Base": The agent resolves `@friendOnTwitter` to their wallet, then uses CDP AgentKit.
        *   "Create a donation template for my cause on Flow": The agent creates the template, uploads metadata to Pinata, and provides an embeddable tag.
        *   "What's the price of ETH?": The agent fetches and returns the current price.

5.  **View Templates & Manage Account (Web Dashboard):**
    *   Log in to the SocioAgent web dashboard using your UUID and CDP Wallet Address.
    *   Here, you can view your linked accounts, see generated templates (e.g., donation frames), and manage other settings.
    *   Shared templates (via `<emb ... emb>` tags) render as interactive components that others can use.

### Prerequisites

*   **Node.js:** Version 18.x or higher (includes npm/pnpm/yarn).
*   **MongoDB:** A running instance (local or cloud-hosted).
*   **Git:** For cloning the repository.
*   **API Keys:**
    *   OpenAI API Key
    *   Pinata JWT Key
    *   CoinMarketCap API Key
