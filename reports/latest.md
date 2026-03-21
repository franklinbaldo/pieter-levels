# Monetization Scan Report - 2026-03-21

## Overview
This report outlines potential fast, simple monetization strategies for Franklin's existing infrastructure, following the Pieter Levels playbook (simple, direct monetization, no over-engineering).

## Core Assets Identified

1.  **Causaganha (Court Data)**
    *   **What it is:** A massive, consolidated data lake of judicial communications from 91 Brazilian courts. Uses UUIDv5 for national-level deduplication of texts and lawyers.
    *   **Current State:** Fully automated pipeline scraping DJEN, creating embeddings, and storing in DuckDB/Parquet on Internet Archive.
    *   **Monetization Idea (Data Product/API):** The structured, deduplicated data (especially lawyer-party links and classified outcomes) is highly valuable to law firms and legaltechs.
        *   *Action:* Package specific datasets (e.g., "Top litigating lawyers per state", "Outcome probabilities by judge/court") as one-off purchases or offer a simple API with a monthly subscription for real-time access to the parsed Parquet data.

2.  **Baliza (PNCP Bids Data)**
    *   **What it is:** A bulletproof CLI for extracting Brazilian public procurement (PNCP) data into DuckDB/Parquet.
    *   **Current State:** Core extraction, gap detection, and Parquet export are functional.
    *   **Monetization Idea (B2B SaaS/API):** Companies selling to the government need this data.
        *   *Action:* Create a paid API endpoint or a paid daily/weekly data dump service providing clean, structured PNCP data. Companies will pay to avoid dealing with the unstable PNCP API themselves.

3.  **Egregora (Content Generation)**
    *   **What it is:** An AI tool that converts WhatsApp chat histories into contextual, memory-aware blog posts with author profiles and media handling. Runs locally.
    *   **Current State:** Fully functional CLI using Pydantic-AI and DuckDB, generating MkDocs sites.
    *   **Monetization Idea (B2C Paid Desktop App / One-Time Service):** People love nostalgia and preserving memories (couples, families, close friends).
        *   *Action:* Wrap Egregora into an easy-to-use Electron/Tauri desktop app and sell it for a one-time fee (e.g., $29). Alternatively, offer a hosted "Chat to Book/Blog" service where users upload their ZIP and pay for the generation.

4.  **Verne (Agent Orchestration UI)**
    *   **What it is:** A static, client-side React/Vite interface for managing Google Jules API sessions and sources.
    *   **Current State:** Functional PWA.
    *   **Monetization Idea (SaaS / Pro Features):**
        *   *Action:* Since it brings a UI to an API, offer a "Pro" version of Verne that includes pre-built workflows, advanced prompt management, or team collaboration features behind a paywall.

5.  **Franklin's Blogs (franklinbaldo.github.io, etc.)**
    *   **What it is:** Personal/technical blogs.
    *   **Monetization Idea (Affiliate/Sponsorship):**
        *   *Action:* Inject relevant affiliate links (e.g., hosting, AI tools, books) or accept sponsored posts, leveraging the "build in public" audience.

## Next Steps / Quick Wins
1.  **Causaganha Data Dump:** Extract a valuable subset of Causaganha data (e.g., aggregated statistics) and put it on Gumroad.
2.  **Egregora Hosted Service:** Set up a simple landing page offering "WhatsApp to Memory Book" as a paid service.
3.  **Baliza API:** Expose the Baliza Parquet files via a simple, authenticated API (e.g., using a lightweight FastAPI wrapper + Stripe).
