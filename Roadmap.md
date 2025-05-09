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