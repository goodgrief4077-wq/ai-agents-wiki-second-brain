# Skill catalog

One row per skill, sorted by name. Columns: `skill` is the folder name to install; `use when` is the trigger; `source` is where to get it (`this repo: skills/<name>/` = already here, `owner/repo` = public GitHub project, `own (not published yet)` = generic skill from the maintainer, not yet added here). Search with grep, never read the whole file.

| skill | use when | source |
|---|---|---|
| 1password | Use to set up and use the 1Password CLI, including sign-in and app integration | openclaw/openclaw |
| agent-conventions | Use when about to act and you want shared operating conventions for an agent working for one person | this repo: skills/agent-conventions/ |
| agent-teams | Use when designing a multi-agent setup with specialist agents instead of one generalist | own (not published yet) |
| agentdb-advanced | Use when you need AgentDB QUIC sync, multiple databases, custom distance metrics or hybrid search | ruvnet/agentic-flow |
| agentdb-learning | Use when training learning plugins on AgentDB with RL algorithms such as Q-Learning, SARSA or Actor-Critic | ruvnet/agentic-flow |
| agentdb-memory-patterns | Use when giving agents persistent session and long-term memory on AgentDB | ruvnet/agentic-flow |
| agentdb-optimization | Use when tuning AgentDB memory use and speed with quantization, HNSW indexing and caching | ruvnet/agentic-flow |
| agentdb-vector-search | Use when you need semantic vector search and retrieval on AgentDB | ruvnet/agentic-flow |
| anti-slop-agentic-engineering | Use when running many AI agents and you want to avoid technical debt and low-quality output | own (not published yet) |
| apple-notes | Use to create, view, search and edit Apple Notes on macOS through the memo CLI | NousResearch/hermes-agent |
| apple-reminders | Use to list, add, complete and delete Apple Reminders through remindctl | NousResearch/hermes-agent |
| arxiv | Use to search and fetch academic papers from arXiv with its free API | NousResearch/hermes-agent |
| ascii-art | Use to make ASCII art with pyfiglet, cowsay, boxes and image-to-ASCII tools | NousResearch/hermes-agent |
| audiocraft-audio-generation | Use for text-to-music and text-to-sound generation with AudioCraft | Orchestra-Research/AI-Research-SKILLs |
| autoplan | Use to run the CEO, design and engineering plan reviews in sequence with automatic decisions | garrytan/gstack |
| axolotl | Use for fine-tuning LLMs with Axolotl: YAML configs, LoRA/QLoRA, DPO | Orchestra-Research/AI-Research-SKILLs |
| benchmark | Use to catch performance regressions: baseline page load, web vitals and resource sizes | garrytan/gstack |
| blocker-breaker | Use when many tasks are pending and you want blockers found and either fixed or turned into exact questions | own (not published yet) |
| blogwatcher | Use to watch blogs and RSS/Atom feeds for new posts | openclaw/openclaw |
| blucli | Use to discover and control BluOS players: playback, grouping and volume | openclaw/openclaw |
| brainstorming | Use before creative work (new features, components, behavior changes) to explore intent and requirements | obra/superpowers |
| browse | Use for fast headless-browser QA: open a URL, interact, screenshot and verify page state | garrytan/gstack |
| browser-automation | Use for browser automation with AI-friendly snapshots in claude-flow agents | ruvnet/claude-flow |
| camsnap | Use to grab frames or clips from RTSP/ONVIF cameras | openclaw/openclaw |
| canary | Use after a deploy to watch the live app for console errors and regressions | garrytan/gstack |
| careful | Use to get a warning before destructive commands such as rm -rf, force-push or DROP TABLE | garrytan/gstack |
| chroma | Use for an open-source embedding database with Chroma | Orchestra-Research/AI-Research-SKILLs |
| claude-code | Use to delegate coding tasks to Claude Code as a sub-agent | NousResearch/hermes-agent |
| clean-check | Use before running a downloaded file or program: hash check, antivirus lookup and optional sandbox | own (not published yet) |
| cleanup | Use for a step-by-step walkthrough of open items, one at a time, with a recommendation each | this repo: skills/cleanup/ |
| clip | Use for zero-shot image classification and image-text matching with CLIP | Orchestra-Research/AI-Research-SKILLs |
| cloud-models | Use when you want to list or switch between available Ollama cloud models | own (not published yet) |
| code-structure | Use when several workflows repeat the same logic and you must split orchestration from a shared service layer | own (not published yet) |
| codebase-inspection | Use to count lines and break down languages and comment ratio of a codebase with pygount | NousResearch/hermes-agent |
| codex | Use for an independent code review, adversarial challenge or consult via the OpenAI Codex CLI | garrytan/gstack |
| coding-agent | Use to hand coding tasks to Goose, OpenCode, Codex, Claude Code or Pi as background processes | openclaw/openclaw |
| coding-agent-setup | Use when installing local coding agents (Goose, Aider, Continue) or building a custom LangGraph coding agent | own (not published yet) |
| context-audit | Use when agent context files (memory, tools, instructions) have grown stale, long or duplicated and need a lean-up | own (not published yet) |
| crawl4ai | Use when you need fast async web crawling of many pages or docs into clean Markdown for RAG | own (not published yet) |
| cso | Use for a security audit: OWASP Top 10, STRIDE threat model, secrets and dependency checks | garrytan/gstack |
| design-consultation | Use when a product needs a full design system: aesthetic, type, colour, layout, spacing and motion | garrytan/gstack |
| design-review | Use for a designer-eye QA of a live site that finds and fixes visual and spacing problems | garrytan/gstack |
| desktop | Use to turn what was just done (research, guide, doc, build) into a Markdown file on the desktop | this repo: skills/desktop/ |
| diagram | Use when you need an architecture diagram, flowchart or network diagram made with draw.io | own (not published yet) |
| dispatching-parallel-agents | Use when two or more independent tasks can be worked in parallel without shared state | obra/superpowers |
| distributed-llm-pretraining-torchtitan | Use for distributed LLM pretraining with torchtitan and 4D parallelism | Orchestra-Research/AI-Research-SKILLs |
| document-release | Use after shipping to bring README, architecture and contributing docs in line with the diff | garrytan/gstack |
| dspy | Use to build and auto-optimize LLM programs declaratively with DSPy | Orchestra-Research/AI-Research-SKILLs |
| eighty-twenty-planning | Use before starting a project: spend most effort on planning, review and gap-finding, then execute | own (not published yet) |
| engineering | Use when writing or reviewing Python code and you want one consistent stack and set of conventions | own (not published yet) |
| evaluating-llms-harness | Use to benchmark LLMs on 60+ academic suites with lm-evaluation-harness | Orchestra-Research/AI-Research-SKILLs |
| excalidraw | Use to draw hand-drawn style diagrams as Excalidraw JSON files | NousResearch/hermes-agent |
| executing-plans | Use when you have a written plan to carry out in a separate session with review checkpoints | obra/superpowers |
| executor | Use when plans or ideas are already written and you want them carried out, not re-planned | own (not published yet) |
| faiss | Use for dense-vector similarity search and clustering with FAISS | Orchestra-Research/AI-Research-SKILLs |
| findmy | Use to track Apple devices and AirTags through FindMy on macOS | NousResearch/hermes-agent |
| fine-tuning-with-trl | Use to fine-tune LLMs with TRL: SFT, DPO and RL methods | Orchestra-Research/AI-Research-SKILLs |
| finishing-a-development-branch | Use when work is finished and tests pass and you must choose how to integrate it | obra/superpowers |
| firecrawl | Use when you need to scrape, crawl or map a website into LLM-ready Markdown or JSON with Firecrawl | own (not published yet) |
| freeze | Use while debugging to block edits outside one chosen directory for the session | garrytan/gstack |
| gemini | Use for one-shot questions, summaries and generation with the Gemini CLI | openclaw/openclaw |
| gguf-quantization | Use for GGUF files and llama.cpp quantization for CPU/GPU inference | Orchestra-Research/AI-Research-SKILLs |
| gif-search | Use to search and download GIFs from Tenor with curl | NousResearch/hermes-agent |
| gifgrep | Use to search GIF providers, download results and extract stills | openclaw/openclaw |
| github | Use for GitHub work through the gh CLI: issues, PRs, CI runs, reviews and API queries | openclaw/openclaw |
| github-auth | Use to set up GitHub authentication for an agent with git or the gh CLI | NousResearch/hermes-agent |
| github-code-review | Use for multi-agent GitHub code review with swarm coordination | ruvnet/claude-flow |
| github-issues | Use to create, triage, label, assign and close GitHub issues | NousResearch/hermes-agent |
| github-multi-repo | Use when coordinating, syncing and organizing work across several GitHub repositories | ruvnet/claude-flow |
| github-pr-workflow | Use for the whole pull request lifecycle: branch, commit, open PR, watch CI and fix failures | NousResearch/hermes-agent |
| github-project-management | Use for GitHub issue tracking, project boards and sprint planning with swarms | ruvnet/claude-flow |
| github-release-management | Use for automated versioning, testing, deployment and rollback of GitHub releases | ruvnet/claude-flow |
| github-repo-management | Use to clone, create, fork and configure GitHub repos, remotes, secrets and releases | NousResearch/hermes-agent |
| github-workflow-automation | Use to design GitHub Actions workflows and CI/CD pipelines with agent help | ruvnet/claude-flow |
| google-workspace | Use for Gmail, Calendar, Drive, Contacts, Sheets and Docs access from Python with OAuth2 | NousResearch/hermes-agent |
| goplaces | Use for Google Places lookups: text search, place details and reviews | openclaw/openclaw |
| greploop | Use to iterate on a pull request until the Greptile reviewer gives a clean score | greptileai/skills |
| grpo-rl-training | Use for GRPO reinforcement-learning fine-tuning with TRL | Orchestra-Research/AI-Research-SKILLs |
| gstack-upgrade | Use when you need to upgrade the gstack skill pack to its latest version | garrytan/gstack |
| guard | Use for full safety mode: destructive-command warnings plus directory-scoped edits | garrytan/gstack |
| guidance | Use to constrain LLM output with regex and grammars for valid structured text | Orchestra-Research/AI-Research-SKILLs |
| handoff | Use when handing work to a fresh agent or session so it can continue | this repo: skills/handoff/ |
| himalaya | Use to list, read, write, reply to and search email over IMAP/SMTP with himalaya | NousResearch/hermes-agent |
| hitl-protocol | Use before any irreversible action or scope expansion: stop, show, explain, wait for approval | own (not published yet) |
| hooks-automation | Use to automate formatting, coordination and learning around agent operations with hooks | ruvnet/claude-flow |
| huggingface-accelerate | Use to add distributed training to a PyTorch script with Hugging Face Accelerate | Orchestra-Research/AI-Research-SKILLs |
| huggingface-tokenizers | Use for fast Hugging Face tokenizers in research and production | Orchestra-Research/AI-Research-SKILLs |
| hybrid-orchestrator | Use when routing tasks across LangGraph, CrewAI, AutoGen or Dify and managing handoffs between them | own (not published yet) |
| imessage | Use to send and receive iMessage/SMS through the imsg CLI on macOS | NousResearch/hermes-agent |
| imsg | Use to read and send iMessage/SMS from the command line on macOS | openclaw/openclaw |
| instructor | Use to extract validated structured data from LLM replies with Pydantic and retries | Orchestra-Research/AI-Research-SKILLs |
| investigate | Use when debugging needs a root-cause-first process: investigate, analyze, hypothesize, implement | garrytan/gstack |
| jina-reader | Use when you need one URL as clean Markdown quickly, with no install and no key (r.jina.ai prefix) | own (not published yet) |
| jupyter-live-kernel | Use for stateful, iterative Python in a live Jupyter kernel | NousResearch/hermes-agent |
| lambda-labs-gpu-cloud | Use for reserved or on-demand GPU cloud instances on Lambda Labs | Orchestra-Research/AI-Research-SKILLs |
| land-and-deploy | Use after a PR exists to merge it, wait for CI and deploy, and verify production health | garrytan/gstack |
| linear | Use to manage Linear issues, projects and teams through the GraphQL API | NousResearch/hermes-agent |
| llama-cpp | Use to run LLM inference on CPU, Apple Silicon or consumer GPUs with llama.cpp | Orchestra-Research/AI-Research-SKILLs |
| llava | Use for visual instruction tuning and image chat with LLaVA | Orchestra-Research/AI-Research-SKILLs |
| long-running-agent | Use when building autonomous agents that run for hours with a planner, generator and evaluator loop | own (not published yet) |
| markitdown | Use when converting PDF, Word, Excel, PowerPoint or other files to Markdown for reading | own (not published yet) |
| mcporter | Use to list, configure, authenticate and call MCP servers and tools from the command line | openclaw/openclaw |
| memory-manager | Use when an agent needs compression-risk detection, snapshots of context and local semantic memory search | own (not published yet) |
| merge | Use when merging or de-duplicating configs, lists or data and conflicts must be resolved and validated | own (not published yet) |
| ml-paper-writing | Use when drafting ML papers for NeurIPS, ICML, ICLR, ACL or AAAI | Orchestra-Research/AI-Research-SKILLs |
| modal-serverless-gpu | Use to run ML workloads on serverless GPUs with Modal | Orchestra-Research/AI-Research-SKILLs |
| model-usage | Use to summarize local per-model cost and usage for Codex or Claude with CodexBar | openclaw/openclaw |
| n8n-builder | Use when building n8n automation workflows through its API | own (not published yet) |
| nano-banana-pro | Use to generate or edit images with Gemini 3 Pro Image (Nano Banana Pro) | openclaw/openclaw |
| nano-pdf | Use to edit PDFs with plain-language instructions using nano-pdf | openclaw/openclaw |
| nemo-curator | Use for GPU-accelerated data curation for LLM training with NeMo Curator | Orchestra-Research/AI-Research-SKILLs |
| notebooklm | Use for full programmatic control of Google NotebookLM: notebooks, sources and generated artifacts | teng-lin/notebooklm-py |
| notion | Use to create and manage Notion pages, databases and blocks through the API | openclaw/openclaw |
| ocr-and-documents | Use to extract text from PDFs and scanned documents (OCR and local text) | NousResearch/hermes-agent |
| office-hours | Use to pressure-test a startup idea with six forcing questions, or to shape a side project | garrytan/gstack |
| openai-image-gen | Use to batch-generate images with the OpenAI Images API and view them in a gallery | openclaw/openclaw |
| openai-whisper | Use for local speech-to-text with the Whisper CLI and no API key | openclaw/openclaw |
| openai-whisper-api | Use to transcribe audio through the OpenAI Whisper API | openclaw/openclaw |
| opencode | Use to delegate coding tasks to the OpenCode CLI agent | NousResearch/hermes-agent |
| openhue | Use to control Philips Hue lights and scenes with the OpenHue CLI | openclaw/openclaw |
| optimizing-attention-flash | Use to speed up transformer attention and cut memory with Flash Attention | Orchestra-Research/AI-Research-SKILLs |
| oracle | Use for good practice with the oracle CLI: prompt and file bundling, engines and sessions | openclaw/openclaw |
| outlines | Use to guarantee valid JSON/XML/code structure during generation with Outlines | Orchestra-Research/AI-Research-SKILLs |
| pair | Use to pair a builder agent with a reviewer agent and set the review rules | this repo: skills/pair/ |
| pair-programming | Use for AI pair programming in driver, navigator or switch modes with live verification | ruvnet/claude-flow |
| paper-search | Use to search, download and read academic papers from 20+ open sources | openags/paper-search-mcp |
| parallel-cli | Use for agent-native web search, extraction and deep research with the Parallel CLI | NousResearch/hermes-agent |
| peekaboo | Use to capture and automate the macOS UI with Peekaboo | openclaw/openclaw |
| peft-fine-tuning | Use for parameter-efficient fine-tuning (LoRA, QLoRA and more) with PEFT | Orchestra-Research/AI-Research-SKILLs |
| pinecone | Use for a managed vector database with Pinecone | Orchestra-Research/AI-Research-SKILLs |
| plan-ceo-review | Use to rethink a plan in founder mode: challenge premises and expand scope where it helps | garrytan/gstack |
| plan-design-review | Use to rate a plan on design dimensions 0-10 and revise it until each is strong | garrytan/gstack |
| plan-eng-review | Use to lock an execution plan: architecture, data flow, edge cases, tests and performance | garrytan/gstack |
| polymarket | Use to query Polymarket prediction markets: prices, order books and history | NousResearch/hermes-agent |
| pr-prep | Use when preparing a clean pull request: clear description, tested commands, before/after, one-line summary | own (not published yet) |
| prompt-architect | Use when you need a well-structured prompt built with a known framework (RACE, RTF and similar) | own (not published yet) |
| pytorch-fsdp | Use for Fully Sharded Data Parallel training with PyTorch FSDP | Orchestra-Research/AI-Research-SKILLs |
| pytorch-lightning | Use for PyTorch Lightning training with a Trainer and distributed strategies | Orchestra-Research/AI-Research-SKILLs |
| qa | Use to QA a web app and iteratively fix the bugs found, committing each fix | garrytan/gstack |
| qa-only | Use for report-only web QA that yields a health score, screenshots and repro steps without fixes | garrytan/gstack |
| qdrant-vector-search | Use for high-performance vector similarity search for RAG with Qdrant | Orchestra-Research/AI-Research-SKILLs |
| qmd | Use when you need local search over notes or docs with BM25, vectors and reranking, or as an MCP server | tobi/qmd |
| reasoningbank-agentdb | Use when adding ReasoningBank adaptive learning and trajectory tracking on top of AgentDB | ruvnet/agentic-flow |
| reasoningbank-intelligence | Use when building agents that learn strategies from past results with ReasoningBank | ruvnet/agentic-flow |
| receiving-code-review | Use when you receive code review feedback and must weigh it rigorously before applying | obra/superpowers |
| requesting-code-review | Use when finishing a task or feature and you want it reviewed against requirements before merging | obra/superpowers |
| retro | Use for a weekly engineering retrospective from commit history, work patterns and quality metrics | garrytan/gstack |
| review | Use for a pre-landing PR review of the diff for safety, trust-boundary and structural issues | garrytan/gstack |
| sag | Use for ElevenLabs text-to-speech with a say-style command line | openclaw/openclaw |
| scrapegraphai | Use when extracting structured data from web pages with natural-language prompts and LLMs, including local models | own (not published yet) |
| segment-anything-model | Use for zero-shot image segmentation with Segment Anything | Orchestra-Research/AI-Research-SKILLs |
| self-audit | Use for a candid weekly self-review of skills, scheduled jobs and the gap between plans and delivery | own (not published yet) |
| serving-llms-vllm | Use to serve LLMs at high throughput with vLLM | Orchestra-Research/AI-Research-SKILLs |
| session-logs | Use to search and analyze your own past session logs with jq | openclaw/openclaw |
| setup-browser-cookies | Use to import cookies from your real browser into the headless browser session | garrytan/gstack |
| setup-deploy | Use to detect your deploy platform and configure settings for the land-and-deploy flow | garrytan/gstack |
| sherpa-onnx-tts | Use for offline local text-to-speech with sherpa-onnx | openclaw/openclaw |
| ship | Use to ship a branch: merge base, run tests, review, bump version, update changelog, push and open a PR | garrytan/gstack |
| simpo-training | Use for reference-free preference optimization (SimPO) for alignment | Orchestra-Research/AI-Research-SKILLs |
| skill-catalog | Use when looking for an existing agent skill for a task and you want to find, pick and plug it in | this repo: skills/skill-catalog/ |
| skill-shelf | Use when you wonder whether a skill exists for a task and want to find and load it from a shelf | this repo: skills/skill-shelf/ |
| skill-stack-onboard | Use to onboard a large skill pack or plugin: inspect, install, park, toggle and verify | this repo: skills/skill-stack-onboard/ |
| skill-upkeep | Use for a periodic review of all skills: find gaps, add, update and archive them | own (not published yet) |
| slim-agent-instructions | Use when an AGENTS.md or CLAUDE.md is too long and should be split into lean modular files | this repo: skills/slim-agent-instructions/ |
| slime-rl-training | Use for LLM post-training with RL using slime (Megatron plus SGLang) | Orchestra-Research/AI-Research-SKILLs |
| songsee | Use to make spectrograms and feature panels from audio files | openclaw/openclaw |
| sonoscli | Use to discover and control Sonos speakers: play, volume, grouping | openclaw/openclaw |
| sparc-methodology | Use for the SPARC method: specification, pseudocode, architecture, refinement, completion | ruvnet/claude-flow |
| sparse-autoencoder-training | Use to train and analyze sparse autoencoders with SAELens | Orchestra-Research/AI-Research-SKILLs |
| spotify-player | Use for terminal Spotify playback and search | openclaw/openclaw |
| stable-diffusion-image-generation | Use for text-to-image generation with Stable Diffusion through Diffusers | Orchestra-Research/AI-Research-SKILLs |
| stream-chain | Use to chain multi-agent steps with stream-JSON pipelines and data transforms | ruvnet/claude-flow |
| subagent-driven-development | Use when executing a plan of independent tasks with fresh subagents in the current session | obra/superpowers |
| summarize | Use to summarize or pull text and transcripts from URLs, podcasts and local files | openclaw/openclaw |
| swarm-advanced | Use for advanced swarm patterns for research, development, testing and distributed work | ruvnet/claude-flow |
| swarm-orchestration | Use when scaling past one agent with swarms, dynamic topology and parallel task execution | ruvnet/agentic-flow |
| systematic-debugging | Use when facing any bug, failing test or odd behavior, before proposing a fix | obra/superpowers |
| tensorrt-llm | Use to maximize NVIDIA LLM inference throughput with TensorRT-LLM | Orchestra-Research/AI-Research-SKILLs |
| test-driven-development | Use when implementing a feature or bugfix and tests should be written first | obra/superpowers |
| things-mac | Use to manage Things 3 projects and to-dos from the command line on macOS | openclaw/openclaw |
| thumbnail-gen | Use when you need three thumbnail variants for a video generated with Stable Diffusion | own (not published yet) |
| tmux | Use to drive interactive CLIs in tmux by sending keys and reading pane output | openclaw/openclaw |
| unfreeze | Use to lift the directory limit set by freeze and allow edits everywhere again | garrytan/gstack |
| unsloth | Use for fast, low-memory LLM fine-tuning with Unsloth | Orchestra-Research/AI-Research-SKILLs |
| using-git-worktrees | Use when feature work needs isolation from the current workspace via git worktrees | obra/superpowers |
| using-superpowers | Use at the start of any conversation to learn how to find and invoke skills | obra/superpowers |
| utilization-audit | Use when you suspect available tools and services are underused and want a ranked list of fixes | own (not published yet) |
| value-brainstorm | Use when you want tailored ideas for how an agent can help, based on the user context and goals | own (not published yet) |
| verification-before-completion | Use before claiming work is complete: run the checks and confirm the output first | obra/superpowers |
| verification-quality | Use for truth scoring, code quality checks and automatic rollback below an accuracy threshold | ruvnet/claude-flow |
| verify-before-declare | Use before claiming work is done: independently test the result instead of trusting that it was written | own (not published yet) |
| video-frames | Use to extract frames or short clips from video with ffmpeg | openclaw/openclaw |
| wacli | Use to send WhatsApp messages or search and sync WhatsApp history with wacli | openclaw/openclaw |
| weather | Use for current weather and forecasts via wttr.in or Open-Meteo | openclaw/openclaw |
| weekly-synthesis | Use for a weekly review of what moved, what is stuck, key numbers and next focus | own (not published yet) |
| weights-and-biases | Use to track ML experiments and training runs with Weights & Biases | Orchestra-Research/AI-Research-SKILLs |
| whisper | Use for speech recognition, transcription and translation with Whisper | Orchestra-Research/AI-Research-SKILLs |
| windows-uninstall | Use when removing Windows software completely, including leftovers, registry entries and startup items | own (not published yet) |
| work-review | Use to review actual work done across repos and projects over a day or week | this repo: skills/work-review/ |
| workflow-automation-audit | Use when you want recurring tasks scanned for automation potential and ranked by time saved | own (not published yet) |
| writing-plans | Use when you have a spec for a multi-step task and need a written plan before coding | obra/superpowers |
| writing-skills | Use when creating, editing or testing skills before they are deployed | obra/superpowers |
| xitter | Use to post and read on X (Twitter) with the x-cli client | NousResearch/hermes-agent |
| xurl | Use to make authenticated X (Twitter) API requests: post, search and manage from the CLI | openclaw/openclaw |
| youtube-data-api | Use when you need structured YouTube data (channels, videos, search, statistics) from the official Data API | own (not published yet) |
| youtube-transcript-api | Use when you need timestamped YouTube transcripts for LLMs, RAG or summaries | own (not published yet) |
| yt-dlp | Use when scraping YouTube metadata, comments or transcripts, or downloading media, with yt-dlp | own (not published yet) |
| yt-scraper | Use when building video-to-text datasets from YouTube with yt-dlp, transcripts and the Data API | own (not published yet) |
| yt-to-skill | Use when you want a video turned into a new skill or an update to an existing skill | own (not published yet) |

## Counts

- Rows: 209
- By source type:
  - own: 39
  - Orchestra-Research/AI-Research-SKILLs: 38
  - openclaw/openclaw: 34
  - garrytan/gstack: 27
  - NousResearch/hermes-agent: 23
  - obra/superpowers: 14
  - ruvnet/claude-flow: 12
  - this repo: 10
  - ruvnet/agentic-flow: 8
  - greptileai/skills: 1
  - teng-lin/notebooklm-py: 1
  - openags/paper-search-mcp: 1
  - tobi/qmd: 1
