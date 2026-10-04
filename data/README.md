# SalesGenie: AI-Powered Sales Assistant

SalesGenie is an AI-powered sales assistant built for **Oak & Ember Interiors**, a home and office furniture retailer.

The project helps sales teams process inbound customer inquiries faster and more consistently. It reduces manual work by extracting customer requirements, qualifying leads, recommending suitable catalog products, preparing CRM-ready records, and generating weekly sales insights.

## Problem Statement

Sales representatives currently spend significant time reading customer emails, identifying requirements, checking product availability, recommending products, updating CRM data, and preparing weekly reports.

This manual process can lead to delayed responses, inconsistent lead qualification, duplicate data entry, missing information, and inaccurate product recommendations.

## Project Goal

Build a workflow that processes customer inquiries and helps the sales team respond with accurate, catalog-grounded recommendations.

## Core Capabilities

- Ingest and analyze customer inquiries
- Extract customer name, email, company, product interest, budget, quantity, urgency, and requirements
- Identify whether an input is a sales inquiry, product question, spam message, or weekly-summary request
- Classify valid sales leads as **Hot**, **Warm**, or **Cold**
- Recommend 1–3 relevant in-stock products from the official product catalog
- Prevent invented product names, prices, features, colors, or stock status
- Create CRM-ready lead records
- Generate weekly sales insights, including lead count, lead-tier breakdown, top categories, and average budget

## Extended Capabilities

- CRM auto-update using Google Sheets or CSV output
- Competitive positioning when customers mention competitors such as IKEA
- Personalized response drafting for valid sales inquiries

## Architecture

SalesGenie uses a sequential workflow with early routing:

```text
Customer Inquiry
   ↓
Intake and Data Extraction
   ↓
Request Routing
   ├── Spam → Mark invalid; no recommendation
   ├── Product Question → Answer using catalog data
   ├── Weekly Summary → Generate sales report
   └── Sales Inquiry
         ↓
       Lead Qualification
         ↓
       Catalog Filtering and Product Recommendation
         ↓
       CRM Record and Response Draft
         ↓
       Evaluation and Observability TraceThis folder contains the product catalog, CRM sample, and evaluation inputs.
