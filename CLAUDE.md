# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Architecture

This is a comprehensive **Adaptive Cognitive Orchestrator (ACO)** knowledge base for implementing human-like, agentic voice agents using Google Cloud services. The repository contains specialized documentation, implementation guides, and technical blueprints organized by technology domains.

### Core Purpose
The ACO serves as a central cognitive engine for human-like conversational AI with:
- Natural turn-taking and emotional intelligence
- Agentic autonomy with complex reasoning capabilities  
- Goal-driven adaptation and proactive information seeking
- Long-term memory and context management
- Continuous learning and improvement mechanisms

## Knowledge Base Structure

### 📋 Core ACO Documentation
- `aoc-implementation-guide.md` - Comprehensive 20-week implementation roadmap
- `adaptive-cognitive-orchestrator-blueprint.md` - Technical architecture and system design
- `blueprint.txt` - Additional architectural specifications
- `aoc-flow.png` - Visual system architecture diagram

### 🛠️ Technology Domain Knowledge Bases
Each domain contains specialized documentation with its own `CLAUDE.md`:

#### `/freeswitch/` - Telecommunications Infrastructure
- **Purpose**: FreeSWITCH deployment on GKE for call routing and SIP trunking
- **Structure**: Dual-purpose (operational docs + source code)
- **Key Commands**: `kubectl`, `fs_cli`, `./bootstrap.sh && make`
- **Domain CLAUDE.md**: `freeswitch/CLAUDE.md`

#### `/gke/` - Kubernetes Engine Infrastructure
- **Purpose**: GKE deployment patterns, networking, and enterprise management
- **Tools**: Interactive CLI tools in Go, GitOps pipelines
- **Learning Path**: 12-week structured progression
- **Domain CLAUDE.md**: `gke/CLAUDE.md`

#### `/vertex/` - AI/ML Platform
- **Purpose**: Vertex AI integration, Gemini model deployment, MLOps pipelines
- **Focus**: Model training, evaluation frameworks, continuous learning
- **Domain CLAUDE.md**: `vertex/CLAUDE.md`

#### `/golang/` - Development Patterns
- **Purpose**: Go implementation patterns for GKE applications
- **Dependencies**: `cloud.google.com/go/*`, `github.com/spf13/cobra`

#### `/telenyx/` - Extended Telecommunications
- **Purpose**: Additional telecom system integration and deployment guides

### 📊 Implementation Phases
- `/tasks/phase-1/` - Foundation infrastructure implementation tasks

## Development Workflow

### 1. Architecture Research Phase
**For understanding ACO system design:**
```bash
# Start with core blueprint
cat aoc-implementation-guide.md
cat adaptive-cognitive-orchestrator-blueprint.md

# Review visual architecture
# Open aoc-flow.png for system interconnections
```

### 2. Technology-Specific Development
**Navigate to appropriate domain and follow domain-specific CLAUDE.md:**
```bash
# For infrastructure deployment
cd gke/ && cat CLAUDE.md
cd freeswitch/ && cat CLAUDE.md

# For AI/ML model development  
cd vertex/ && cat CLAUDE.md

# For application development
cd golang/ && cat CLAUDE.md
```

### 3. Implementation Commands

#### Infrastructure Setup (GKE + FreeSWITCH)
```bash
# GKE cluster operations
kubectl get pods -n telephony
kubectl logs freeswitch-0 -n telephony
gcloud container clusters get-credentials freeswitch-cluster

# FreeSWITCH operations
kubectl exec -it freeswitch-0 -n telephony -- fs_cli
fs_cli -x "status"
fs_cli -x "show calls"
```

#### AI/ML Development (Vertex AI)
```bash
# Deploy Gemini 2.5 Pro endpoint
gcloud ai endpoints create --region=us-central1

# MLOps pipeline management
# (Specific commands in vertex/CLAUDE.md)
```

#### Application Development (Go)
```bash
# Standard Go project structure for GKE apps
go mod init your-aoc-component
go mod tidy

# Core dependencies for ACO components
go get cloud.google.com/go/container
go get cloud.google.com/go/logging  
go get cloud.google.com/go/monitoring
go get github.com/spf13/cobra
```

## Key Integration Points

### 1. Central ACO Hub Architecture
The system follows a hub-and-spoke model with the ACO as the central orchestrator:
- **Reasoning Engine**: Gemini 2.5 Pro on Vertex AI
- **Memory System**: Cloud Spanner (long-term) + Cloud Memorystore (short-term)
- **Telephony**: FreeSWITCH on GKE for SIP/RTP handling
- **API Gateway**: Apigee for external system integration
- **Monitoring**: Cloud Monitoring + BigQuery analytics

### 2. Data Flow Patterns
```
PSTN/WebRTC → FreeSWITCH → STT → ACO (Gemini) → TTS → FreeSWITCH → Audio Output
              ↓                    ↓
         Cloud Pub/Sub        Memory Systems
              ↓                    ↓
         Analytics           Context/History
```

### 3. Agentic Capabilities Implementation
- **Reasoning & Decision-Making**: Chain-of-thought prompting with Gemini
- **Goal-Driven Adaptation**: Dynamic strategy modification based on call state
- **Proactive Information Seeking**: Context-aware question generation
- **Tool Use**: API orchestration through Apigee gateway
- **Emotional Intelligence**: Custom models for sentiment and emotion analysis

## Service Level Objectives

### Technical Performance Targets
- **Response Latency**: <200ms end-to-end
- **Concurrent Calls**: 10,000+ per cluster
- **Availability**: 99.99% uptime SLA
- **Call Success Rate**: ≥99% (7-day window)
- **First Contact Resolution**: Target improvement through agentic capabilities

### Quality Metrics
- **Human-likeness Scores**: Conversation naturalness, emotional appropriateness
- **Agentic Performance**: Goal achievement rate, problem-solving efficacy
- **Customer Experience**: CSAT, NPS, escalation rates

## Implementation Phases Overview

### Phase 1: Foundation Infrastructure (Weeks 1-4)
- Deploy GKE cluster with FreeSWITCH
- Configure VPC, security, and monitoring
- Establish CI/CD pipelines

### Phase 2: Core ACO Engine (Weeks 5-8)  
- Deploy Gemini 2.5 Pro on Vertex AI
- Implement reasoning and memory systems
- Build tool use capabilities

### Phase 3: Agentic Capabilities (Weeks 9-12)
- Goal-driven adaptation
- Emotional intelligence modules
- Interruption management

### Phase 4: Quality & Monitoring (Weeks 13-16)
- KPI collection and visualization
- A/B testing framework
- MLOps pipelines

### Phase 5: Production Optimization (Weeks 17-20)
- Performance optimization
- Security hardening
- Production deployment

## Navigation Guidance

### For ACO System Design
- Start with `aoc-implementation-guide.md` for comprehensive roadmap
- Review `adaptive-cognitive-orchestrator-blueprint.md` for technical architecture
- Examine `aoc-flow.png` for visual system understanding

### For Technology-Specific Work
- **Infrastructure**: Use `gke/CLAUDE.md` and `freeswitch/CLAUDE.md`
- **AI/ML Development**: Use `vertex/CLAUDE.md`  
- **Application Development**: Use `golang/` patterns and `gke/implementation/`
- **Telecom Integration**: Use `freeswitch/` and `telenyx/` documentation

### For Implementation Tasks
- Follow phase-specific guidance in `/tasks/` directory
- Reference domain-specific CLAUDE.md files for detailed technical guidance
- Use integration patterns from core ACO documentation

## Security and Compliance

- **Zero-trust Architecture**: VPC Service Controls, Cloud IAM principle of least privilege
- **Encryption**: Cloud KMS for key management, encryption at rest and in transit
- **Compliance**: HIPAA, SOC2, ISO27001 requirements built into architecture
- **Monitoring**: Comprehensive audit logging with Cloud Audit Logs

This knowledge base enables complete lifecycle management of human-like, agentic voice agents from architectural design through production deployment and continuous optimization.