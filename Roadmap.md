# **Business Plan Team Chelsea**
# **Product:** AI-Powered Group Dynamics & Performance Analysis Tool
<img src="https://sdmntprwestus.oaiusercontent.com/files/00000000-2d58-6230-b835-9d3859572105/raw?se=2025-05-09T22%3A43%3A56Z&sp=r&sv=2024-08-04&sr=b&scid=00000000-0000-0000-0000-000000000000&skoid=7399a3a4-0259-4d43-bcd6-a56ceeb4c28b&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-05-09T20%3A25%3A34Z&ske=2025-05-10T20%3A25%3A34Z&sks=b&skv=2024-08-04&sig=KWybgtsFO20EfG3Dqu1x/5jKo07Hwcqe97rcBI6tt3Y%3D" alt="chelsea logo" width="200"/>

## **Date:** March 27, 2025

## Sprint 1: Upload & Transcription Pipeline

### Frontend Tasks
- Built initial UI scaffold with `Home`, `UploadPage`, and `NavBar` components  
- Developed `FileUploader` component for uploading MP3 files  
- Implemented loading/progress placeholder for user feedback  

### Backend Tasks
- Created `/upload` endpoint using `Multer` to handle file input  
- Integrated AssemblyAI to:  
  - Upload and transcribe audio  
  - Poll for transcription status  
  - Store structured output: `utterances`, full text, speaker labels  
- Assigned UUIDs for temporary transcript storage  

### Infrastructure Tasks
- Set up local development environment  
- Added temporary file storage system (`/data/meetings` directory)  

### ✅ Deliverable
User can upload an `.mp3` file and receive a speaker-labeled transcript with a “Transcript Ready!” confirmation  


## Sprint 2: Feedback Generation via OpenAI

### Backend Tasks
- Created `openai.js` for prompt construction  
- Built `analyzer.js` to organize structured speaker data from transcript  
- Designed two prompt flows:  
  - Per-speaker feedback (e.g., clarity, tone, verbosity, empathy)  
  - Team-level summary (e.g., balance, interruptions, tone)  

### Frontend Tasks
- Built `ReportPage` layout to display results  
- Developed `FeedbackCard` and `PulseScoreCard` components  
- Called `/report/:id` endpoint to fetch and render structured feedback  

### *(Optional)*
- Began development of `pulseScore.js` (0–100 scale scoring model)  

### ✅ Deliverable
Full feedback display for a single uploaded meeting with speaker and team insights  


## Sprint 3: Polish & Optional Features

### Frontend Tasks
- Built `HistoryPage` for accessing past meetings  
- Implemented `SpeakerEditor` component (editable speaker names)  
- Added persistent storage using `lowdb` or `localStorage` fallback  

### Backend Tasks
- Developed `/history/:teamId` or local JSON file cache for past meetings  
- Created `/update-speakers/:id` endpoint to enable manual relabeling  
- Finalized `pulseScore` logic and integrated color coding for insight cards  

### UI Polish
- Designed empty states, tooltips, and error fallback views  
- Enhanced visual hierarchy and UX clarity  

### ✅ Deliverable
Polished MVP with save/load capability, speaker editing, and robust UX

## Future Sprint: Visualizations & Progress Tracking

### Frontend Tasks
- Developed `ChartContainer.js` with:  
  - Bar chart for % speaking time  
  - Line chart for sentiment over time (if available)  
  - *(Optional)* Radar chart for team traits  
- Created `ProgressBar` component  
- Added polling logic via `statusPoller.js` to display upload–transcribe–analyze status  

### Backend Tasks
- Implemented `/status/:id` endpoint to return progress updates  
- Extended backend to store speaking times per user  

### ✅ Deliverable
Users can track live progress and visualize meeting data with charts  

---

## Other Potential Future Features

### Stretch Goals
- Integrate emotion recognition from audio (e.g., Hume AI)  
- Build Google Meet / Zoom integrations  
- Develop real-time assistant that joins meetings live  
- Add Slack/Email delivery of insights  
- Implement user authentication and multi-team support  
