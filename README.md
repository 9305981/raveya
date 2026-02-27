# Rayeva AI Systems Assignment  
## Module 1 – AI Auto-Category & Tag Generator

### Role
Full Stack / AI Intern  
Focus: Applied AI for Sustainable Commerce  

---

## Overview

This module automatically classifies sustainable products using AI.

It performs:

- Primary category assignment
- Sub-category suggestion
- SEO tag generation (5–10 tags)
- Sustainability filter selection
- Structured JSON output
- Database storage
- Prompt and response logging

The system follows clean architecture principles with clear separation of AI logic and business logic.

---

## Architecture

Client → FastAPI Route → Service Layer → AI Layer → OpenAI  
                                                 ↓  
                                            SQLite Database  

### Layer Responsibilities

Routes  
Handles API requests and error responses.

Service Layer  
Contains business logic and database operations.

AI Layer  
Handles prompt generation and OpenAI interaction.

Models  
Defines database schema.

Schemas  
Validates input structure using Pydantic.

---

## AI Prompt Design

The AI is instructed to:

- Select one primary category from a predefined list
- Suggest a relevant sub-category
- Generate 5–10 SEO tags
- Choose sustainability filters from a fixed list
- Return strictly structured JSON only

Temperature is set to 0 to ensure deterministic output.

---

## Example Structured JSON Output

```json
{
  "primary_category": "Food & Beverage",
  "sub_category": "Reusable Drinkware",
  "seo_tags": [
    "bamboo cup",
    "eco coffee mug",
    "plastic-free drinkware",
    "reusable coffee cup",
    "compostable cup"
  ],
  "sustainability_filters": [
    "plastic-free",
    "compostable",
    "eco-friendly"
  ]
}
