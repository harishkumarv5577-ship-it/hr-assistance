# ResumeAI: AI-Powered Interview Assistant

ResumeAI is a web application that helps with the hiring process using AI. It reads a candidate's resume, checks how well the candidate fits a job description, generates interview questions based on the resume, runs the interview, and gives feedback on the answers.

Built with Next.js, TypeScript, Google Genkit (Gemini) and Firebase.

## Features

- **Resume parsing:** extracts text and key details from an uploaded or pasted resume
- **Skill extraction:** identifies skills from the resume and from the candidate's interview answers
- **Job suitability check:** compares the resume against a job description
- **AI question generation:** generates 10-15 interview questions based on the candidate's resume
- **Automated interview:** asks the questions one by one and records the candidate's responses
- **Interview feedback:** analyses the responses and produces a performance summary
- **Interview history:** saves past interviews so results can be reviewed later
- **Authentication:** sign-in with Firebase
- **Light and dark theme**

## Tech Stack

| Area | Technology |
| --- | --- |
| Framework | Next.js 15 (App Router), React 18 |
| Language | TypeScript |
| Styling | Tailwind CSS, shadcn/ui, Radix UI |
| AI | Google Genkit with Gemini |
| Backend and database | Firebase (Authentication, Firestore) |
| Forms and validation | React Hook Form, Zod |
| Charts and icons | Recharts, Lucide React |

## How It Works

1. The user signs in and starts a new interview from the dashboard.
2. The user adds a resume and a job description.
3. AI flows extract the resume text and skills, then check suitability for the role.
4. The app generates interview questions and runs the interview.
5. The answers are analysed and a feedback report is saved to the interview history.

The AI logic lives in `src/ai/flows/`, with one Genkit flow per task: resume text extraction, skill extraction, suitability check, question generation, and feedback generation.

## Project Structure

```
src/
  ai/            Genkit setup and AI flows (Gemini)
  app/           Pages and routes (dashboard, interview, history, settings, login)
  components/    UI components and interview step components
  firebase/      Firebase setup, auth and Firestore hooks
  hooks/         Custom React hooks
  lib/           Utilities
docs/            App blueprint and backend schema
firestore.rules  Firestore security rules
```

## Getting Started

### Prerequisites

- Node.js 18 or later
- A Gemini API key from [Google AI Studio](https://aistudio.google.com/)
- A Firebase project (Authentication and Firestore enabled)

### Installation

```bash
git clone https://github.com/harishkumarv5577-ship-it/hr-assistance.git
cd hr-assistance
npm install
```

### Environment variables

Create a file named `.env` in the project root:

```
GEMINI_API_KEY=your_gemini_api_key_here
```

Add your own Firebase configuration in `src/firebase/config.ts`.

Never commit your `.env` file or share your API key.

### Run the app

```bash
npm run dev
```

Open [http://localhost:9002](http://localhost:9002) in your browser.

To test the AI flows on their own with the Genkit developer UI:

```bash
npm run genkit:dev
```

## Available Scripts

| Command | What it does |
| --- | --- |
| `npm run dev` | Starts the development server on port 9002 |
| `npm run build` | Creates a production build |
| `npm run start` | Runs the production build |
| `npm run genkit:dev` | Starts the Genkit developer UI |
| `npm run lint` | Runs the linter |
| `npm run typecheck` | Checks TypeScript types |

## Author

**V Harish Kumar**
B.Tech Computer Science and Engineering, Vel Tech Rangarajan Dr. Sagunthala R&D Institute of Science and Technology
[LinkedIn](https://www.linkedin.com/in/harish-kumar-19361b445)
