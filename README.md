# Grantify

**AI-Powered Decentralized Grant Evaluation Platform**

🚀 **Live Demo**: [https://grantify-neon.vercel.app](https://grantify-neon.vercel.app)

Grantify revolutionizes grant funding through autonomous AI agent evaluation, combining blockchain transparency with intelligent decision-making. Five specialized AI agents collaborate to evaluate proposals across technical feasibility, ecosystem impact, team credibility, budget viability, and community sentiment.

> **Note**: This README focuses on the **production deployment**. For local development setup, see the [`local` branch](https://github.com/pryyyynz/agentdao/tree/local).

---

## 🌟 Features

- **Multi-Agent AI Evaluation** - 5 specialized AI agents provide comprehensive proposal analysis
- **Blockchain Integration** - Smart contracts on Ethereum for transparent fund management
- **Milestone-Based Funding** - Release funds incrementally based on deliverable completion
- **Real-Time Dashboard** - Track proposals, evaluations, and agent activity
- **IPFS Storage** - Decentralized storage for proposals and documentation
- **Email Notifications** - Automated updates for grant applicants

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         FRONTEND (Next.js)                       │
│  • Grant Submission  • Dashboard  • Agent Activity  • Admin     │
└────────────────────┬────────────────────────────────────────────┘
                     │
                     ├─────────────────────────────────────────┐
                     │                                         │
         ┌───────────▼──────────┐              ┌──────────────▼────────────┐
         │   PYTHON SERVICES     │              │   SMART CONTRACTS         │
         │   (FastAPI)           │              │   (Solidity/Hardhat)     │
         │                       │              │                           │
         │ • Technical Analysis  │              │ • GrantRegistry          │
         │ • Impact Assessment   │◄─────────────┤ • GrantTreasury          │
         │ • Due Diligence       │              │ • AgentVoting            │
         │ • Budget Analysis     │              │ • MilestoneRegistry      │
         │ • Community Sentiment │              │                           │
         └───────────┬───────────┘              └───────────────────────────┘
                     │
         ┌───────────▼──────────┐
         │    MCP SERVER         │
         │   (TypeScript)        │
         │                       │
         │ • Orchestrator        │
         │ • Agent Communication │
         │ • Workflow Management │
         └───────────┬───────────┘
                     │
         ┌───────────▼──────────┐
         │  TYPESCRIPT AGENTS    │
         │                       │
         │ • Blockchain Interact │
         │ • IPFS Integration    │
         │ • On-Chain Voting     │
         └───────────┬───────────┘
                     │
         ┌───────────▼──────────┐
         │    DATABASE           │
         │   (PostgreSQL)        │
         │                       │
         │ • Grants  • Evals     │
         │ • Users   • Logs      │
         └───────────────────────┘
```

---

## 🚀 Production Deployment

### Live Services

- **Frontend**: [https://grantify-neon.vercel.app](https://grantify-neon.vercel.app)
- **Python Backend**: [https://agentdao.onrender.com](https://agentdao.onrender.com)
- **MCP Server**: [https://agentdao-mcp-server.onrender.com](https://agentdao-mcp-server.onrender.com)
- **Database**: Supabase PostgreSQL
- **Blockchain**: Ethereum Sepolia Testnet

### Deployment Architecture

```
┌─────────────────┐
│  Vercel         │  Frontend (Next.js)
│  grantify-neon  │  https://grantify-neon.vercel.app
└────────┬────────┘
         │
         ├──────────────────────────────────┐
         │                                   │
┌────────▼────────┐              ┌──────────▼───────┐
│ Render          │              │ Ethereum         │
│ Python Services │              │ Sepolia Testnet  │
│ agentdao        │              │ Smart Contracts  │
└────────┬────────┘              └──────────────────┘
         │
┌────────▼────────┐
│ Render          │
│ MCP Server      │
│ agentdao-mcp    │
└────────┬────────┘
         │
┌────────▼────────┐
│ Supabase        │
│ PostgreSQL DB   │
└─────────────────┘
```

### Smart Contract Addresses (Sepolia)

```
GrantRegistry:  0x6d77f3a5dcad33cbEbf431Fee6F67E5930148D17
GrantTreasury:  0x71C74477ae190d7eeF762d01AC091D021a5AbAa6
AgentVoting:    0x19Fe9e5e12fc5C1657E299aC69878965367A294D
```

### Local Development Setup

**Want to run Grantify locally?** Switch to the `local` branch for full development setup:

```bash
git clone https://github.com/pryyyynz/agentdao.git
cd agentdao
git checkout local
```

See the [`local` branch README](https://github.com/pryyyynz/agentdao/tree/local) for:
- Local environment setup
- Database installation and migrations
- Smart contract deployment to local testnet
- Service configuration and API keys
- Development workflow

### Using the Production Platform

1. **Visit**: [https://grantify-neon.vercel.app](https://grantify-neon.vercel.app)
2. **Connect Wallet**: MetaMask on Sepolia testnet
3. **Submit Grant**: Complete the multi-step form
4. **Track Progress**: View agent evaluations in real-time
5. **Get Results**: Receive email notification with decision

---

## 📦 Project Structure

```
agentdao/
├── frontend/              # Next.js web application → [README](frontend/README.md)
├── python-services/       # FastAPI evaluation services → [README](python-services/README.md)
├── mcp-server/           # Model Context Protocol orchestrator → [README](mcp-server/README.md)
├── typescript-agents/    # Blockchain interaction agents
├── smart-contracts/      # Solidity contracts & deployment → [README](smart-contracts/README.md)
├── database/             # PostgreSQL schema & migrations → [README](database/README.md)
└── docs/                 # Additional documentation
```

---

## 🤖 AI Agents

### 1. **Technical Analyst**
Evaluates code quality, architecture, security, and technical feasibility.

### 2. **Impact Evaluator**
Assesses ecosystem impact, innovation, market fit, and long-term value.

### 3. **Due Diligence Officer**
Verifies team credentials, GitHub activity, wallet history, and red flags.

### 4. **Budget Analyst**
Reviews financial planning, cost estimates, and milestone breakdowns.

### 5. **Community Analyst**
Measures community support, engagement, and grassroots backing.

---

## 🔑 Production Configuration

### Key Environment Variables

The production deployment uses the following configuration:

**Frontend (Vercel)**:
```env
NEXT_PUBLIC_API_URL=https://agentdao.onrender.com
NEXT_PUBLIC_THIRDWEB_CLIENT_ID=[configured]
NEXT_PUBLIC_GRANT_REGISTRY_ADDRESS=0x6d77f3a5dcad33cbEbf431Fee6F67E5930148D17
NEXT_PUBLIC_GRANT_TREASURY_ADDRESS=0x71C74477ae190d7eeF762d01AC091D021a5AbAa6
NEXT_PUBLIC_AGENT_VOTING_ADDRESS=0x19Fe9e5e12fc5C1657E299aC69878965367A294D
```

**Backend (Render)**:
```env
DATABASE_URL=[Supabase PostgreSQL]
GROQ_API_KEY=[configured]
CORS_CUSTOM_ORIGINS=https://grantify-neon.vercel.app
RESEND_FROM_EMAIL=onboarding@resend.dev
MCP_SERVER_URL=https://agentdao-mcp-server.onrender.com
```

**MCP Server (Render)**:
```env
PYTHON_SERVICES_URL=https://agentdao.onrender.com
PYTHON_API_KEY=[configured]
```

For local development configuration, see the [`local` branch](https://github.com/pryyyynz/agentdao/tree/local).

---

## 🧪 Testing

**Production**: The live platform is fully tested and operational.

**Local Testing**: For running tests locally, see the [`local` branch](https://github.com/pryyyynz/agentdao/tree/local) which includes:
- Unit tests for all services
- Integration test suites
- Smart contract test scripts
- End-to-end testing guide

Production test coverage:
- ✅ Smart contract deployment and verification
- ✅ Multi-agent evaluation pipeline
- ✅ Blockchain voting mechanism
- ✅ Email notification system
- ✅ Milestone-based payments
- ✅ Admin controls and emergency procedures

---

## 📚 Documentation

### Component Guides

- **[Complete Setup Guide](SETUP.md)** - Step-by-step installation for the entire platform
- **[Frontend Documentation](frontend/README.md)** - Next.js application setup and usage
- **[Python Services Documentation](python-services/README.md)** - AI evaluation services API
- **[MCP Server Documentation](mcp-server/README.md)** - Orchestrator and agent coordination
- **[Smart Contracts Documentation](smart-contracts/README.md)** - Blockchain deployment and testing
- **[Database Documentation](database/README.md)** - Schema, migrations, and queries

### Quick Links

- [Architecture Overview](#🏗️-architecture)
- [AI Agents](#🤖-ai-agents)
- [Environment Variables](#🔑-environment-variables)
- [Testing Guide](#🧪-testing)

---

## 🆘 Support

- **Issues**: [GitHub Issues](https://github.com/pryyyynz/agentdao/issues)
- **Email**: dugboryeleprince@gmail.com

---

## 🎯 Roadmap

- [x] Multi-agent evaluation system
- [x] Smart contract deployment
- [x] Milestone-based funding
- [x] Email notifications
- [ ] Governance token integration
- [ ] Mobile application
- [ ] Multi-chain support
- [ ] Advanced analytics dashboard