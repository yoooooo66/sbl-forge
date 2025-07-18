<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>SBL Forge App Mockup</title>
  <style>
    :root {
      --bg-dark: #181818;
      --card-dark: #222;
      --primary-red: #D7263D;
      --accent-metal: #A0A0A0;
      --badge-bg: linear-gradient(90deg, #D7263D 0%, #A0A0A0 100%);
      --text-bold: 'Bebas Neue', 'Montserrat', Arial, sans-serif;
    }
    html, body {
      background: var(--bg-dark);
      color: #fff;
      font-family: 'Montserrat', Arial, sans-serif;
      margin: 0;
      padding: 0;
      min-height: 100vh;
    }
    .app-container {
      max-width: 390px;
      margin: 0 auto;
      background: var(--bg-dark);
      border-radius: 32px;
      box-shadow: 0 0 24px rgba(0,0,0,0.7);
      overflow: hidden;
      border: 2px solid var(--card-dark);
    }
    .header {
      background: var(--card-dark);
      padding: 20px 16px 0 16px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .app-title {
      font-size: 2.2rem;
      font-family: var(--text-bold);
      color: var(--primary-red);
      letter-spacing: 2px;
      font-weight: bold;
      text-transform: uppercase;
    }
    .avatar {
      width: 38px; height: 38px;
      border-radius: 50%;
      border: 2px solid var(--primary-red);
      background: var(--accent-metal);
      margin-right: 12px;
    }
    .dashboard {
      padding: 18px 16px;
      background: var(--bg-dark);
    }
    .summary-card {
      background: var(--card-dark);
      border-radius: 20px;
      box-shadow: 0 2px 10px #0006;
      padding: 18px;
      margin-bottom: 22px;
    }
    .summary-title {
      font-family: var(--text-bold);
      font-size: 1.3rem;
      color: var(--accent-metal);
      margin-bottom: 6px;
      text-transform: uppercase;
    }
    .summary-stats {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    .stat-value {
      font-size: 2.2rem;
      color: var(--primary-red);
      font-family: var(--text-bold);
      font-weight: bold;
      margin-right: 8px;
    }
    .stat-label {
      color: var(--accent-metal);
      font-size: 1.1rem;
      font-weight: 500;
    }
    .actions {
      display: flex;
      gap: 12px;
      margin-bottom: 12px;
    }
    .btn {
      background: var(--primary-red);
      color: #fff;
      font-family: var(--text-bold);
      font-weight: bold;
      border: none;
      border-radius: 16px;
      padding: 10px 20px;
      font-size: 1.1rem;
      cursor: pointer;
      box-shadow: 0 2px 12px #d7263d44;
      transition: background 0.2s;
    }
    .btn-secondary {
      background: var(--accent-metal);
      color: #222;
    }
    .quote-section {
      margin: 18px 0 0 0;
      padding: 14px 18px;
      background: var(--card-dark);
      border-left: 6px solid var(--primary-red);
      border-radius: 12px;
      font-style: italic;
      font-size: 1.15rem;
      color: var(--accent-metal);
      position: relative;
    }
    .quote-section:after {
      content: '';
      position: absolute;
      bottom: 6px; left: 18px;
      width: 60px; height: 3px;
      background: var(--primary-red);
      border-radius: 2px;
    }
    .section-title {
      font-family: var(--text-bold);
      color: var(--primary-red);
      font-size: 1.25rem;
      margin-top: 30px;
      margin-bottom: 10px;
      text-transform: uppercase;
      letter-spacing: 1px;
    }
    .workout-builder, .exercise-library, .progress-tracker,
    .ai-coach, .leaderboard, .achievements {
      background: var(--card-dark);
      border-radius: 18px;
      margin-bottom: 20px;
      padding: 18px 14px;
      box-shadow: 0 2px 10px #0003;
    }
    .input, .select {
      width: 100%; padding: 10px 12px;
      border: 2px solid var(--primary-red);
      border-radius: 10px;
      background: #111;
      color: #fff;
      margin-bottom: 10px;
      font-size: 1rem;
    }
    .exercises-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
    }
    .exercise-item {
      background: #111;
      border-radius: 10px;
      padding: 8px;
      text-align: center;
      color: var(--accent-metal);
      box-shadow: 0 1px 4px #d7263d22;
      font-size: 0.93rem;
    }
    .exercise-icon {
      font-size: 1.6rem;
      color: var(--primary-red);
      margin-bottom: 4px;
      display: block;
    }
    .progress-photo-row {
      display: flex;
      gap: 8px;
      margin-bottom: 10px;
    }
    .progress-photo {
      width: 48px; height: 72px;
      background: #222;
      border-radius: 6px;
      border: 2px solid var(--accent-metal);
      object-fit: cover;
    }
    .progress-graph {
      width: 100%;
      height: 48px;
      background: linear-gradient(90deg, var(--primary-red), var(--accent-metal));
      border-radius: 10px;
      margin-bottom: 10px;
    }
    .achievement-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
    .badge {
      background: var(--badge-bg);
      color: #222;
      font-family: var(--text-bold);
      font-size: 0.95rem;
      padding: 8px 14px;
      border-radius: 12px;
      font-weight: bold;
      box-shadow: 0 2px 8px #d7263d44;
      margin-bottom: 6px;
    }
    .badge.locked {
      opacity: 0.4;
      background: #222;
      color: var(--accent-metal);
      border: 2px dashed var(--accent-metal);
    }
    .coach-chat {
      background: #111;
      border-radius: 10px;
      padding: 10px;
      margin-bottom: 8px;
      color: #fff;
      border: 1px solid var(--primary-red);
      box-shadow: 0 1px 6px #d7263d33;
    }
    .leaderboard-list {
      list-style: none;
      padding: 0;
      margin: 0;
    }
    .leaderboard-item {
      display: flex;
      align-items: center;
      padding: 8px 0;
      border-bottom: 1px solid #333;
    }
    .leaderboard-rank {
      font-size: 1.1rem;
      font-family: var(--text-bold);
      color: var(--primary-red);
      font-weight: bold;
      margin-right: 12px;
      width: 26px;
      text-align: center;
    }
    .leaderboard-avatar {
      width: 32px; height: 32px;
      border-radius: 50%;
      margin-right: 8px;
      border: 2px solid var(--accent-metal);
    }
    .leaderboard-name {
      flex: 1;
      color: var(--accent-metal);
      font-weight: 500;
      font-size: 1.05rem;
    }
    .leaderboard-pr {
      color: #fff;
      font-size: 0.95rem;
      font-weight: bold;
      margin-left: 8px;
    }
    .challenge-card {
      background: #111;
      color: var(--accent-metal);
      border-radius: 10px;
      padding: 8px 12px;
      margin-top: 8px;
      margin-bottom: 8px;
      font-size: 0.98rem;
      box-shadow: 0 1px 6px #d7263d22;
    }
    .motivational-banner {
      background: var(--primary-red);
      color: #fff;
      font-family: var(--text-bold);
      font-size: 1.17rem;
      text-align: center;
      padding: 10px 0;
      border-radius: 10px;
      margin-bottom: 8px;
      font-style: italic;
      box-shadow: 0 2px 10px #d7263d66;
    }
    .streak-counter {
      font-family: var(--text-bold);
      color: var(--primary-red);
      font-size: 1.3rem;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
    }
    .streak-icon {
      font-size: 1.4rem;
      margin-right: 8px;
      color: var(--primary-red);
    }
  </style>
</head>
<body>
  <div class="app-container">
    <!-- Header -->
    <div class="header">
      <div class="app-title">SBL Forge</div>
      <img class="avatar" src="https://i.imgur.com/9b3hJHO.png" alt="User Avatar" />
    </div>

    <!-- Dashboard -->
    <div class="dashboard">
      <div class="summary-card">
        <div class="summary-title">Today's PR</div>
        <div class="summary-stats">
          <span class="stat-value">315</span>
          <span class="stat-label">Bench Press (lbs)</span>
        </div>
        <div class="summary-stats">
          <span class="stat-value">455</span>
          <span class="stat-label">Deadlift (lbs)</span>
        </div>
      </div>
      <div class="actions">
        <button class="btn">Start Workout</button>
        <button class="btn btn-secondary">Add Photo</button>
        <button class="btn btn-secondary">Leaderboard</button>
      </div>
      <div class="quote-section">
        “Strength comes from struggle. Forge ahead.”
      </div>
    </div>

    <!-- Custom Workout Builder -->
    <div class="workout-builder">
      <div class="section-title">Custom Workout Builder</div>
      <input class="input" type="text" placeholder="Search exercise..." />
      <div class="exercises-grid">
        <div class="exercise-item"><span class="exercise-icon">🏋️‍♂️</span> Bench Press</div>
        <div class="exercise-item"><span class="exercise-icon">💪</span> Biceps Curl</div>
        <div class="exercise-item"><span class="exercise-icon">🦵</span> Squat</div>
        <div class="exercise-item"><span class="exercise-icon">🏋️</span> Deadlift</div>
        <div class="exercise-item"><span class="exercise-icon">🏃‍♂️</span> Lunges</div>
        <div class="exercise-item"><span class="exercise-icon">🧘</span> Plank</div>
      </div>
      <input class="input" type="text" placeholder="Sets x Reps x Weight" />
      <button class="btn" style="margin-top:10px;">Save as Template</button>
    </div>

    <!-- Exercise Video Library -->
    <div class="exercise-library">
      <div class="section-title">Exercise Video Library</div>
      <input class="input" type="text" placeholder="Search or filter..." />
      <div class="exercises-grid">
        <div class="exercise-item"><span class="exercise-icon">▶️</span> Bench Press</div>
        <div class="exercise-item"><span class="exercise-icon">▶️</span> Squat</div>
        <div class="exercise-item"><span class="exercise-icon">▶️</span> Deadlift</div>
      </div>
      <button class="btn btn-secondary" style="margin-top:10px;">Add to Workout</button>
    </div>

    <!-- Progress Tracker -->
    <div class="progress-tracker">
      <div class="section-title">Progress Tracker</div>
      <div class="progress-photo-row">
        <img class="progress-photo" src="https://i.imgur.com/hTftU9n.png" alt="Progress 1"/>
        <img class="progress-photo" src="https://i.imgur.com/hTftU9n.png" alt="Progress 2"/>
        <img class="progress-photo" src="https://i.imgur.com/hTftU9n.png" alt="Progress 3"/>
      </div>
      <div class="progress-graph"></div>
      <div style="color:var(--accent-metal);margin-bottom:6px;">Bench PR: 315 lbs &nbsp; | &nbsp; Deadlift PR: 455 lbs</div>
      <div class="achievement-badges">
        <div class="badge">Iron Will</div>
        <div class="badge">PR Crusher</div>
        <div class="badge locked">Consistency King</div>
        <div class="badge">Body Transformation</div>
      </div>
    </div>

    <!-- AI Coach -->
    <div class="ai-coach">
      <div class="section-title">AI Coach</div>
      <div class="coach-chat">
        <strong>Coach:</strong> Increase deadlift by 5 lbs next session. Focus on hip drive. Recovery: add 10 min stretching.
      </div>
      <input class="input" type="text" placeholder="Ask the Forge Coach..." />
      <button class="btn" style="margin-top:8px;">Send</button>
      <div class="actions" style="margin-top:8px;">
        <button class="btn btn-secondary">Analyze My Workout</button>
        <button class="btn btn-secondary">Suggest Progression</button>
        <button class="btn btn-secondary">Review My Photos</button>
      </div>
    </div>

    <!-- Leaderboard / Community Challenge -->
    <div class="leaderboard">
      <div class="section-title">Leaderboard</div>
      <ul class="leaderboard-list">
        <li class="leaderboard-item">
          <span class="leaderboard-rank">1</span>
          <img class="leaderboard-avatar" src="https://i.imgur.com/9JwVb4b.png" alt="User 1"/>
          <span class="leaderboard-name">Alex S.</span>
          <span class="leaderboard-pr">Bench: 355</span>
        </li>
        <li class="leaderboard-item" style="background:rgba(215,38,61,0.2);border-radius:8px;">
          <span class="leaderboard-rank">2</span>
          <img class="leaderboard-avatar" src="https://i.imgur.com/9JwVb4b.png" alt="User 2"/>
          <span class="leaderboard-name">You</span>
          <span class="leaderboard-pr" style="color:var(--primary-red);">Bench: 315</span>
        </li>
        <li class="leaderboard-item">
          <span class="leaderboard-rank">3</span>
          <img class="leaderboard-avatar" src="https://i.imgur.com/9JwVb4b.png" alt="User 3"/>
          <span class="leaderboard-name">Maria L.</span>
          <span class="leaderboard-pr">Bench: 295</span>
        </li>
      </ul>
      <div class="challenge-card">
        <strong>Community Challenge:</strong> 10,000 lbs lifted this week.  
        <button class="btn btn-secondary" style="margin-top:5px;">Join</button>
      </div>
      <div class="motivational-banner">
        "Rise Above. Forge Your Path."
      </div>
    </div>

    <!-- Gamified Achievements -->
    <div class="achievements">
      <div class="section-title">Achievements</div>
      <div class="achievement-badges">
        <div class="badge">Iron Will</div>
        <div class="badge">PR Crusher</div>
        <div class="badge">Body Transformation</div>
        <div class="badge locked">Consistency King</div>
        <div class="badge locked">Challenge Champion</div>
      </div>
      <div class="streak-counter">
        <span class="streak-icon">🔥</span> 7-day Streak!
      </div>
    </div>
    
    <div class="quote-section" style="margin-bottom:18px;">
      “Strength is forged, not given.” — SBL Forge
    </div>
  </div>
</body>
</html>
