# lokirandomvideos.github.io
Hello I’m David and I like making videos
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>David Hernandez | YouTube Creator</title>

<style>
:root {
  --bg: #0b0b12;
  --card: #141428;
  --neon: #ff004c;
  --neon2: #00e5ff;
  --text: #f2f2f2;
}

* {
  box-sizing: border-box;
  font-family: "Segoe UI", system-ui, sans-serif;
}

body {
  margin: 0;
  min-height: 100vh;
  background: radial-gradient(circle at top, #1b1b3a, var(--bg));
  color: var(--text);
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  max-width: 900px;
  width: 90%;
  padding: 40px;
}

.card {
  background: linear-gradient(145deg, var(--card), #0e0e1f);
  border-radius: 20px;
  padding: 40px;
  box-shadow: 0 0 30px rgba(255, 0, 76, 0.25);
  animation: float 6s ease-in-out infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

h1 {
  font-size: 3rem;
  margin: 0;
  color: var(--neon);
  text-shadow: 0 0 15px rgba(255, 0, 76, 0.6);
}

.subtitle {
  font-size: 1.2rem;
  margin-bottom: 25px;
  color: #cfcfff;
}

.bio {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 30px;
}

.section {
  margin-top: 30px;
}

.section h2 {
  color: var(--neon2);
  margin-bottom: 15px;
  text-shadow: 0 0 10px rgba(0, 229, 255, 0.4);
}

.skills {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.skill {
  background: rgba(255,255,255,0.05);
  padding: 12px 18px;
  border-radius: 999px;
  border: 1px solid rgba(0,229,255,0.4);
  box-shadow: 0 0 10px rgba(0,229,255,0.2);
}

.buttons {
  margin-top: 35px;
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
}

.button {
  text-decoration: none;
  padding: 14px 26px;
  border-radius: 999px;
  font-weight: bold;
  letter-spacing: 0.5px;
  transition: transform 0.2s, box-shadow 0.2s;
}

.youtube {
  background: var(--neon);
  color: white;
  box-shadow: 0 0 20px rgba(255,0,76,0.6);
}

.youtube:hover {
  transform: scale(1.05);
  box-shadow: 0 0 35px rgba(255,0,76,0.9);
}

.footer {
  text-align: center;
  margin-top: 40px;
  opacity: 0.6;
  font-size: 0.9rem;
}
</style>
</head>

<body>
  <div class="container">
    <div class="card">
      <h1>David Hernandez</h1>
      <div class="subtitle">🎥 YouTube Creator</div>

      <p class="bio">
        I love to make random content and turn ideas into entertaining videos.
        From gaming to creative edits, I enjoy experimenting and having fun
        while creating.
      </p>

      <div class="section">
        <h2>Skills</h2>
        <div class="skills">
          <div class="skill">Roblox</div>
          <div class="skill">Video Editing</div>
        </div>
      </div>

      <div class="buttons">
        <a class="button youtube" href="#" target="_blank">
          Visit My YouTube Channel
        </a>
      </div>

      <div class="footer">
        © 2025 David Hernandez • Made with creativity
      </div>
    </div>
  </div>
</body>
</html>
