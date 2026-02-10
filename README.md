# MailNexa – Intelligent Email Classification System
## Overview

MailNexa is a smart email analysis system that fetches Gmail messages, classifies them into meaningful categories, and assigns priority levels using a Hybrid AI approach (Rule-based + Machine Learning).

It helps users quickly identify important emails such as:

 1.Deadlines

 2.Academic notifications

 3.Job alerts

 4.Security messages

## Key Features


Gmail integration using OAuth2

Fetches recent emails (configurable time window – e.g., last 24 hours)

Automatic email categorization

Priority detection (HIGH / MEDIUM / LOW)

Hybrid classification:

Rule-based logic

Machine Learning fallback

Clean Chrome Extension inbox UI

Explainable classification (shows reason for classification)

## Email Categories
### Education & Learning


Academics (NPTEL, Coursera, Exams)

Coding Platforms (LeetCode, GitHub)

### Career & Work


Jobs & Internships

Interviews

Meetings

### Time-Sensitive


Deadlines

Finance / Transactions

### Information & Content


Newsletters

Announcements

### Other


Promotions

Events

Social Notifications

Security Alerts

System Emails

Normal (fallback)

## Tech Stack
### Backend

Python 3.11

FastAPI

Gmail API

### Machine Learning

Scikit-learn

TF-IDF Vectorizer

Logistic Regression

### Frontend

Chrome Extension (Manifest V3)

HTML, CSS, JavaScript

## Architecture Flow

Gmail API → Email Fetcher → Classification Pipeline
→ Hybrid Classifier (Rule + ML) → FastAPI → Chrome Extension UI

## Setup Steps

### 1. Enable Gmail API

Create project in Google Cloud → Enable Gmail API → Download OAuth credentials

Place file:

backend/credentials.json

### 2. Generate Token (One Time)
cd backend
python auth_once.py

### 3. Train ML Model
cd ml
python train_model.py

### 4. Run Backend
python -m uvicorn main:app --reload

### 5. Load Chrome Extension

Load the extension/ folder using Chrome → Load unpacked.

## API Endpoints

/ → Status

/emails → Classified emails

/emails/summary → Category & priority counts

## Future Enhancements

Learning from user priority overrides

Deadline date extraction

Smart importance scoring

Analytics dashboard
