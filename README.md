# 🤖 AI Customer Support Automation Platform

An AI-powered customer support automation platform built with **n8n** to automate ticket intake, AI-based ticket analysis, team assignment, SLA determination, customer communication, priority alerts, and Telegram-based ticket management.

---

## 📌 Project Overview

Customer support teams often handle large numbers of support requests manually. Categorizing tickets, determining priority, assigning them to the appropriate team, responding to customers, and tracking ticket status can become time-consuming and difficult to manage.

This project provides a modular **n8n-based AI Customer Support Automation Platform** that automates major stages of the support-ticket lifecycle.

The system uses **Telegram, n8n, Groq, Google Sheets, Gmail, and n8n Data Tables** to create an automated ticket-management workflow.

---

## 🎯 Objectives

The main objectives of the project are:

- Automate customer support ticket intake.
- Generate unique ticket IDs.
- Classify tickets using AI.
- Determine ticket priority, department, and sentiment.
- Generate an initial AI-based customer reply.
- Automatically assign tickets to support teams.
- Determine SLA based on ticket priority.
- Send customer ticket acknowledgements.
- Generate alerts for high-priority tickets.
- Provide Telegram-based ticket management.
- Allow customers to view, update, close, or escalate tickets.
- Maintain centralized ticket information in Google Sheets.

---

## 🏗️ System Architecture

The platform is divided into multiple independent n8n workflows.

```text
Customer
   │
   ▼
Telegram / Webhook
   │
   ▼
WF-0 — Multi-Channel Intake
   │
   ▼
WF-1 — Ticket Intake
   │
   ▼
WF-2 — AI Ticket Analysis
   │
   ▼
WF-3 — Auto Assignment & SLA
   │
   ├──────────────► WF-5 — High Priority Alert
   │
   ▼
WF-4 — Customer Communication
   │
   ▼
Customer

              ┌──────────────────────┐
              │   Google Sheets      │
              │   Support Tickets    │
              └──────────▲───────────┘
                         │
                         │
              WF-6 — Telegram Button Handler
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
       View           Update          Close
                         │
                         ▼
                    Talk to Human
