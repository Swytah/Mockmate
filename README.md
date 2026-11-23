
# MockMate — AI-Powered Interview Preparation Platform

**Practice Interviews. Understand Your Performance. Improve with AI.**

MockMate is an AI-powered interview preparation platform that helps job seekers practise realistic interviews, receive personalized feedback, identify improvement areas and prepare better for future opportunities.

Instead of simply displaying interview questions, MockMate provides an interactive interview experience with an AI recruiter, question-wise evaluation, improvement notes and a post-interview assistant.

**Live Demo:** https://mockmate2026.lovable.app

---

## 1. Problem Statement

Many job seekers, especially fresh graduates and first-time applicants, struggle with interview preparation.

Common challenges include:

- Limited access to realistic mock interviews.
- Difficulty answering unexpected interview questions.
- Lack of structured feedback on interview performance.
- Not knowing how to improve weak answers.
- Difficulty understanding offer letters and interview-related information.
- Limited opportunities to practise without depending on another person.

Traditional preparation methods often provide questions and answers but do not offer a complete interactive practice and feedback experience.

## 2. Proposed Solution

MockMate provides an AI-powered mock interview environment where candidates can:

- Select an AI recruiter and personalize the interview experience.
- Upload their resume and offer letter.
- Choose a job role and experience level.
- Attend a structured 10-question mock interview.
- Receive AI-generated feedback on their answers.
- Review strengths and improvement areas.
- Get suggested answers through AI-generated notes.
- Take a mini test to reinforce learning.
- Ask follow-up questions about their interview or offer letter.

The goal is to make interview preparation more interactive, personalized and actionable.

---

## 3. Key Features

### 3.1 User Authentication

- User signup and login.
- Password strength validation.
- Google sign-in option.
- Remember me and forgot password options.

### 3.2 Recruiter Personalization

- Choose a female or male recruiter avatar.
- Enter candidate and recruiter names.
- Customize the interview experience.

### 3.3 Interview Setup

- Upload resume PDF.
- Upload offer letter PDF.
- Select a job role.
- Choose experience level.

**Available Job Roles:**

1. Software Engineer
2. Frontend Developer
3. Data Analyst
4. Product Manager
5. UI/UX Designer
6. Business Analyst
7. HR Executive
8. Marketing Associate

### 3.4 AI Mock Interview

- Structured interview containing exactly 10 questions.
- AI recruiter interaction.
- Candidate response capture.
- Live transcript display.
- Question-wise feedback.
- Interview progress tracking.

### 3.5 Deep Review & Notes

After the interview, candidates can review their performance.

The review includes:

- Questions asked.
- Candidate responses.
- AI-generated ratings.
- Confidence, communication and technical evaluation.
- Recruiter feedback.
- Improvement suggestions through Get Notes.

### 3.6 Self-Assessment

Candidates can provide their own assessment of their interview performance.

MockMate supports a comparison between:

- AI evaluation.
- Candidate self-assessment.

This helps candidates reflect on their perceived strengths and weaknesses.

### 3.7 Mini Test

A short knowledge-check activity follows the review.

It helps candidates check their understanding of the improvement concepts discussed during the review.

### 3.8 Ask Anything

Ask Anything is a conversational assistant that allows candidates to ask follow-up questions.

**Example questions:**

- Was my fourth interview answer correct?
- What should I do if I go blank during an interview?
- What does my offer letter say about my role?
- How can I improve my interview introduction?

Candidates can also attach an offer letter PDF for relevant questions.

### 3.9 Dashboard & Past Interviews

- Access previous interview attempts.
- View available interview scores.
- Retry the same job role.
- Practise a different role.
- Track interview preparation activity.

---

## 4. Complete User Journey

```text
Signup
  |
  v
Login
  |
  v
Recruiter & Candidate Selection
  |
  v
Interview Setup
(Resume + Offer Letter + Job Role)
  |
  v
Start Mock Interview
  |
  v
10 Interview Questions
  |
  v
Live Transcript & Feedback
  |
  v
Deep Review & Notes
  |
  v
Self-Assessment
  |
  v
Mini Test
  |
  v
Ask Anything
  |
  v
Dashboard
  |
  +----> Try Again
  |
  +----> Try New Role
```

---

## 5. Technology Stack

| Technology | Purpose |
|---|---|
| Lovable | Frontend development, application hosting and API integrations |
| Gemini API | AI intelligence, contextual responses, interview review and Ask Anything |
| Groq API | Fast AI inference for recruiter conversations |
| Mixpanel | Product analytics and user journey tracking |
| Jira | Product development and task management |
| Figma | UI/UX design and product prototyping |

### AI Integration Approach

**Gemini API — AI Intelligence**

Used to support:

- Interview question generation.
- Candidate answer evaluation.
- Deep Review and improvement notes.
- Mini Test evaluation.
- Ask Anything conversations.
- Contextual assistance using available interview and document information.

**Groq API — Fast AI Inference**

Used to support:

- Fast AI recruiter responses.
- Conversational interaction during mock interviews.
- A more responsive interview experience.

Both API keys are configured in Lovable project secrets.

## 5.1 API Verification - Tested with Postman

I personally verified both AI APIs in Postman before connecting them to MockMate.

**Groq API - Tested Successfully**
- Endpoint: `https://api.groq.com/openai/v1/chat/completions`
- Model Used: `openai/gpt-oss-20b`
- Header: `Authorization: Bearer <GROQ_API_KEY>`
- Result: `200 OK` - Riya's interview question received successfully

**Gemini API - Tested Successfully**
- Endpoint: `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent`
- Result: `200 OK`

### Errors I Fixed During Testing

| Error | What It Meant | How I Fixed It |
| --- | --- | --- |
| 401 | API Key was wrong / Bearer missing | Added `Bearer` before key in Authorization header |
| 404 | Model does not exist | Changed deprecated model `llama-3.3-70b-versatile` to `openai/gpt-oss-20b` |
| 503 | Server busy / Model overloaded | Retried request, changed to less busy model |

**Screenshots:**
Postman test screenshots for Groq 200 OK and Gemini API testing are added in this repository.

## 6. Product Analytics — Mixpanel

Mixpanel is integrated with MockMate using the project token configured through Lovable.

The current analytics implementation tracks three core events:

| Event | Purpose |
|---|---|
| Mock Interview Started | Tracks users starting an interview |
| Question Answered | Tracks users submitting interview answers |
| Feedback Viewed | Tracks users viewing interview feedback |

### Analytics Reports

**Report 1: Unique Mock Interview and Question Activity**

A linear report comparing unique users across the three tracked events over the last 30 days.

**Report 2: Mock Interview Completion Funnel**

Tracks the journey:

Mock Interview Started → Question Answered → Feedback Viewed

The displayed Mixpanel funnel reports:

- 1 user.
- 100% displayed conversion.

This is an initial observation from a very small sample, not a reliable conversion benchmark.

**Report 3: User Journey Flow**

A 12-step flow report used to visualize user progression and repeated question-answer activity.

---

## 7. Project Management — Jira

Jira is used to manage MockMate's product development activities.

### Workflow

Idea → To Do → In Progress → Done

### Project Progress Snapshot

Based on the Jira workspace screenshot:

| Status | Work Items |
|---|---:|
| Done | 6 |
| In Progress | 1 |
| To Do | 1 |
| Idea | 5 |
| Total | 13 |

### Recent Activity

- 6 completed in the last 7 days.
- 13 updated in the last 7 days.
- 13 created in the last 7 days.
- 0 due soon in the next 7 days.

Jira helps organize requirements, prioritize features, track implementation and manage improvements.

---

## 8. Product Documentation

The following documents support MockMate's product planning, design and development:

| Document | Description |
|---|---|
| Problem & User Research | User problems, research observations and product opportunity |
| Product Requirements Document (PRD) | Product scope, requirements and functionality |
| User Journey & Flow | End-to-end user experience |
| System Architecture | Application components and integrations |
| AI Prompt Design | Prompt structures for AI-powered features |
| API Integration | Gemini, Groq and Mixpanel integration |
| Product Analytics | Mixpanel reports and funnel analysis |
| Jira Sprint Report | Work items and development progress |
| Product Roadmap | Now, Next and Later priorities |
| GTM Strategy | Target audience and user acquisition strategy |
| Metrics & KPIs | Product success measurement framework |
| Security & Privacy | Data protection and API security considerations |

---

## 9. Future Improvements

Potential future enhancements include:

- Expanded Mixpanel event tracking.
- More detailed interview performance analytics.
- Personalized question difficulty.
- Improved speech and communication analysis.
- Multilingual interview support.
- Personalized learning recommendations.
- Advanced performance comparison across interview attempts.

These are proposed improvements and are not all part of the current implementation.

---

## 10. Security & Privacy Considerations

MockMate works with candidate information, resumes, offer letters and interview responses.

Important considerations include:

- Protecting API credentials through secure configuration.
- Avoiding exposure of sensitive user information.
- Restricting access to uploaded documents.
- Handling candidate information responsibly.
- Avoiding unnecessary personal information in analytics.
- Defining document retention and deletion policies.

---

## 11. Project Outcome

MockMate brings together interview practice, AI-powered evaluation, personalized improvement suggestions and contextual assistance in one application.

The project demonstrates practical product management activities, including:

- Identifying a user problem.
- Defining product requirements.
- Designing the user journey.
- Prioritizing product features.
- Integrating AI services.
- Implementing product analytics.
- Tracking development through Jira.
- Planning future product improvements.

---

## 12. Project Links

- **Live Application:** https://mockmate2026.lovable.app
- **Design Tool:** Figma
- **Development Platform:** Lovable
- **Analytics:** Mixpanel
- **Project Management:** Jira

---

**MockMate — Helping candidates practise smarter, understand their gaps and prepare with confidence.**
