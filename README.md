# lokirandomvideos.github.io
Hello I’m David and I like making videos:)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>David Hernandez | Roblox Creator</title>

<!-- Firebase SDKs -->
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-firestore-compat.js"></script>

<style>
:root {
  --bg: #0b1d0b;
  --card: #143214;
  --roblox-green: #00ff66;
  --roblox-blue: #00cfff;
  --text: #f5fff5;
}

* { box-sizing: border-box; font-family: "Segoe UI", system-ui, sans-serif; }

body {
  margin: 0;
  background: linear-gradient(180deg, #0a1a0a, var(--bg));
  color: var(--text);
}

.container { max-width: 1200px; margin: auto; padding: 30px; }

.card {
  background: linear-gradient(160deg, var(--card), #0d260d);
  border-radius: 24px;
  padding: 40px;
  box-shadow: 0 0 40px rgba(0,255,102,0.35);
}

h1 { font-size: 3rem; color: var(--roblox-green); text-shadow: 0 0 15px rgba(0,255,102,0.8); }
.subtitle { font-size: 1.3rem; color: var(--roblox-blue); }
.bio { margin-top: 20px; font-size: 1.1rem; }

.section { margin-top: 50px; }
.section h2 { color: var(--roblox-blue); margin-bottom: 15px; }

.video-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 20px;
}

.video-grid iframe { width: 100%; height: 520px; border-radius: 16px; border: none; }

.button {
  display: inline-block;
  margin-top: 20px;
  padding: 14px 30px;
  background: var(--roblox-green);
  color: #003300;
  font-weight: bold;
  border-radius: 14px;
  text-decoration: none;
}

.warning {
  background: rgba(255,255,0,0.15);
  border: 2px solid #ffee00;
  padding: 15px;
  border-radius: 12px;
  margin-bottom: 15px;
}

.comment-box { background: rgba(0,0,0,0.4); padding: 20px; border-radius: 16px; }
.comment-box input, .comment-box textarea {
  width: 100%; padding: 12px; margin-bottom: 12px; border-radius: 10px;
  border: none; background: #0b2a0b; color: white;
}

.comment-box button {
  background: var(--roblox-blue); border: none; padding: 12px 20px;
  border-radius: 12px; font-weight: bold; cursor: pointer;
}

.comment { background: rgba(0,0,0,0.6); padding: 12px; border-radius: 10px; margin-bottom: 10px; }

.footer { text-align: center; margin-top: 50px; opacity: 0.6; }
</style>
</head>

<body>
<div class="container">
  <div class="card">
    <h1>David Hernandez</h1>
    <div class="subtitle">🧱 Roblox Creator • 🎥 LokiRandomVideos</div>

    <p class="bio">Roblox content, random fun, and Shorts. Leave ideas below — comments are public & filtered.</p>

    <div class="section">
      <h2>Recent Shorts</h2>
      <div class="video-grid">
        <iframe src="https://www.youtube.com/shorts/uF9hkn80yLA" allowfullscreen></iframe>
        <iframe src="https://www.youtube.com/shorts/ZL_G12TPvPQ" allowfullscreen></iframe>
        <iframe src="https://www.youtube.com/shorts/57VaxFa4egA" allowfullscreen></iframe>
      </div>
    </div>

    <a class="button" href="https://www.youtube.com/@lokirandomvideos" target="_blank">Subscribe on YouTube</a>

    <div class="section">
      <h2>Public Feedback & Ideas</h2>
      <div class="warning">
        ⚠️ Comments are public. Bad words are filtered. Spam is blocked.
      </div>

      <div class="comment-box">
        <input id="username" placeholder="Roblox username (optional)" />
        <textarea id="message" rows="4" placeholder="Your idea or feedback"></textarea>
        <button onclick="sendComment()">Send</button>
      </div>

      <div id="comments"></div>
    </div>

    <div class="footer">© 2025 David Hernandez</div>
  </div>
</div>

<script>
// 🔴 STEP REQUIRED: Replace this Firebase config with YOUR OWN (free)
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT",
};

firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();

const bannedWords = ["badword1", "badword2", "badword3"];
function filterText(text) {
  let result = text;
  bannedWords.forEach(w => {
    const r = new RegExp(w, 'gi');
    result = result.replace(r, '***');
  });
  return result;
}

function sendComment() {
  const user = document.getElementById('username').value || 'Anonymous';
  let msg = document.getElementById('message').value;
  if (!msg) return;
  msg = filterText(msg);

  db.collection('comments').add({
    user,
    msg,
    time: firebase.firestore.FieldValue.serverTimestamp()
  });

  document.getElementById('message').value = '';
}

// Live comments
db.collection('comments').orderBy('time', 'desc').limit(50)
  .onSnapshot(snapshot => {
    const list = document.getElementById('comments');
    list.innerHTML = '';
    snapshot.forEach(doc => {
      const c = doc.data();
      const div = document.createElement('div');
      div.className = 'comment';
      div.innerHTML = `<strong>${c.user}</strong><br>${c.msg}`;
      list.appendChild(div);
    });
  });
</script>
</body>
</html>
