# 안녕하세요, AI 서비스 개발을 공부하는 백엔드/AI 개발자 김범규입니다.

LLM 애플리케이션을 단순히 호출하는 데서 끝내지 않고, **검색(RAG), 도구 호출, 상태 기반 워크플로우, 사용자 프로필 기반 추천**까지 연결해 실제 서비스 형태로 만드는 데 관심이 있습니다.  
최근에는 채용공고 검색 및 적합도 분석 에이전트인 [`job-fit-agent`](https://github.com/qwerty0911/job-fit-agent)를 만들며 LangGraph 기반 Agent workflow와 RAG 구조를 실습하고 있습니다.

## Focus

- **AI Agent / RAG**: LangGraph, LangChain, vector search, hybrid search, reranking, structured output
- **Backend**: FastAPI, Pydantic, REST API, streaming response, environment-based configuration
- **Frontend**: React 기반 챗봇 UI, API 연동, 프로필/검색 결과 패널 설계
- **Data / Infra**: PostgreSQL, pgvector, ChromaDB, Docker, Git

## Current Project

### [job-fit-agent](https://github.com/qwerty0911/job-fit-agent)

사용자 프로필과 이력서를 기반으로 채용공고를 검색하고, 특정 공고의 요구사항과 사용자의 경험이 얼마나 잘 맞는지 분석하는 AI 에이전트 프로젝트입니다.

주요 목표:

- 자연어 채팅 입력을 `채용공고 검색` / `채용공고 분석` 의도로 분류
- 검색 키워드가 있으면 해당 키워드로 공고 검색
- 검색 키워드가 없으면 사용자 프로필의 기술스택 기반으로 공고 검색
- 공고의 자격요건과 우대사항을 구조화하여 추출
- 자격요건을 질문으로 변환해 이력서/자기소개서 vector store에서 근거 검색
- 요구사항별 `충족 / 부분 충족 / 부족` 판단과 적합도 점수 제공

구상 중인 workflow:

```text
User Chat
→ Intent Router
→ Job Search Agent or Job Analysis Agent
→ Profile / Resume RAG
→ Fit Judge
→ Recommendation Response
```

## Tech Stack

### Languages

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)

### AI / LLM

![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![Hugging%20Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

- RAG 기반 질의응답 구조 설계
- Embedding / Vector Search / Hybrid Search
- BM25, RRF, Reranking, HyDE, Multi-Query 실습
- LangGraph 기반 state graph, conditional routing, tool calling workflow 실습
- Pydantic structured output을 활용한 intent/result schema 설계
- MCP, tool schema, long-term memory, checkpointer 개념 학습

### Backend

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Uvicorn](https://img.shields.io/badge/Uvicorn-499848?style=flat-square&logo=python&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)

- REST API 설계
- LLM API 연동
- Streaming response 설계
- `.env` / `.env.example` 기반 환경변수 관리
- Pydantic schema와 validator를 활용한 입력 검증

### Frontend

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=flat-square&logo=axios&logoColor=white)

- React 기반 챗봇 UI 구현
- 채팅 영역과 프로필/검색결과 패널을 분리한 2-column layout 구상
- API 연동 및 응답 상태 표시

### Database / Infra

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

- PostgreSQL / pgvector
- ChromaDB
- Docker / Docker Compose
- Jupyter Notebook 기반 실험 정리
- GitHub repository 관리 및 README 문서화

## Learning Notes

최근 집중하고 있는 주제입니다.

- **RAG 검색 품질**: `top-k`, precision/recall, ANN, HNSW, reranking
- **Query Transformation**: Multi-Query, HyDE, query rewriting
- **Agent Workflow**: LangGraph node/edge/state/reducer, handoff, approval branch
- **Tool Calling**: tool schema, Pydantic args schema, ToolEnvelope 패턴
- **Memory**: InMemorySaver, DB saver/checkpointer, long-term store 구분
- **MCP**: Host / Client / Server 구조와 tool 연결 프로토콜

## Direction

저는 AI 기능을 단순 데모로 끝내기보다, 사용자가 실제로 반복해서 쓸 수 있는 서비스 구조로 만드는 것에 관심이 있습니다.

현재는 아래 역량을 중심으로 포트폴리오를 쌓고 있습니다.

- RAG와 Agentic AI를 활용한 문제 해결
- FastAPI 기반 AI 백엔드 설계
- React 챗봇 UI와 백엔드 API 연결
- 사용자 프로필/이력서 기반 개인화 추천
- 검색 결과의 근거와 판단 이유를 설명하는 AI 서비스

## Education

- 가천대학교 컴퓨터공학과 졸업
- 신한 DS 국비교육 과정 수료 (2023)

## Experience

- 타이호인스트 근무 (2024)

## Certifications

- SQLD
- 정보처리기사

## Repository Topics

```text
python
fastapi
react
openai
langchain
langgraph
rag
llm
agentic-ai
chatbot
postgresql
pgvector
chromadb
docker
jupyter-notebook
```
