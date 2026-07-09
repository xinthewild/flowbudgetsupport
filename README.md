<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Flow — Support</title>
<style>
  :root{
    --bg:#faf9f7;
    --card:#ffffff;
    --text:#1c1c1e;
    --muted:#6b6b6f;
    --accent:#8a6d3b;
    --accent-light:#f2e9dc;
    --border:#e6e2da;
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
    background:var(--bg);
    color:var(--text);
    line-height:1.6;
  }
  .wrap{max-width:720px;margin:0 auto;padding:48px 24px 80px;}
  header{margin-bottom:40px;}
  header h1{font-size:2rem;margin:0 0 8px;}
  header p{color:var(--muted);margin:0;}
  .card{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:12px;
    padding:28px;
    margin-bottom:24px;
  }
  h2{font-size:1.15rem;margin:0 0 14px;display:flex;align-items:center;gap:8px;}
  ol,ul{margin:0;padding-left:20px;color:var(--text);}
  li{margin-bottom:6px;}
  a{color:var(--accent);text-decoration:none;}
  a:hover{text-decoration:underline;}
  .email-box{
    background:var(--accent-light);
    border-radius:8px;
    padding:12px 16px;
    font-weight:600;
    display:inline-block;
    margin-top:8px;
  }
  form{display:flex;flex-direction:column;gap:14px;}
  label{font-size:0.9rem;font-weight:600;color:var(--text);}
  input, textarea{
    width:100%;
    padding:12px 14px;
    border:1px solid var(--border);
    border-radius:8px;
    font-size:1rem;
    font-family:inherit;
    background:#fff;
    color:var(--text);
  }
  textarea{min-height:140px;resize:vertical;}
  button{
    background:var(--accent);
    color:#fff;
    border:none;
    padding:14px 20px;
    border-radius:8px;
    font-size:1rem;
    font-weight:600;
    cursor:pointer;
    margin-top:4px;
  }
  button:hover{opacity:0.9;}
  .note{font-size:0.85rem;color:var(--muted);margin-top:10px;}
  .status{margin-top:14px;font-size:0.9rem;font-weight:600;}
  .status.success{color:#2e7d32;}
  .status.error{color:#c62828;}
  footer{margin-top:40px;color:var(--muted);font-size:0.85rem;text-align:center;}
</style>
</head>
<body>
<div class="wrap">

  <header>
    <h1>Flow — Support 👋</h1>
    <p>Need help? If you're having issues with Flow, we're here for you. Send us a message below or email us directly — we'll respond as soon as possible.</p>
    <div class="email-box">✉️ <a href="mailto:kai.x626@icloud.com">kai.x626@icloud.com</a></div>
  </header>

  <div class="card">
    <h2>📝 Contact Us</h2>
    <form id="supportForm">
      <div>
        <label for="name">Your Name</label>
        <input type="text" id="name" name="name" required placeholder="Jane Doe">
      </div>
      <div>
        <label for="email">Your Email</label>
        <input type="email" id="email" name="email" required placeholder="jane@example.com">
      </div>
      <div>
        <label for="message">Tell us about your issue or question</label>
        <textarea id="message" name="message" required placeholder="What happened? What were you trying to do? Device model / OS version if relevant..."></textarea>
      </div>
      <button type="submit">Send Message</button>
      <div id="formStatus" class="status"></div>
      <p class="note">Clicking "Send Message" will open your email app with a pre-filled message addressed to kai.x626@icloud.com. If your device doesn't open an email app automatically, please email us directly at the address above.</p>
    </form>
  </div>

  <div class="card">
    <h2>🛠 Common Issues</h2>
    <ol>
      <li>
        <strong>App not loading or crashing</strong><br>
        Try: closing and reopening the app, updating to the latest version, restarting your device.
        If the issue continues, email us with your device model, iOS/Android version, and a screenshot or screen recording.
      </li>
      <li>
        <strong>Data not syncing</strong><br>
        Make sure you're logged into the same account and have a stable internet connection, then pull down to refresh or restart the app.
      </li>
      <li>
        <strong>Categories or features not working</strong><br>
        Tell us exactly what you were doing and send a screenshot if possible. We fix bugs quickly and push updates regularly.
      </li>
    </ol>
  </div>

  <div class="card">
    <h2>💡 Feature Requests</h2>
    <p>We build Flow with user feedback. If you want something added, email us with "Feature Request" in the subject line. We read everything.</p>
  </div>

  <div class="card">
    <h2>🔐 Privacy Questions</h2>
    <p>We take privacy seriously. Read our full policy here: <a href="https://xinthewild.github.io" target="_blank" rel="noopener">xinthewild.github.io</a></p>
  </div>

  <div class="card">
    <h2>📩 Contact</h2>
    <p>For all support requests: <a href="mailto:kai.x626@icloud.com">kai.x626@icloud.com</a></p>
    <p>Typical response time: 24–72 hours</p>
  </div>

  <div class="card">
    <h2>🧠 Tip</h2>
    <p>When reporting a bug, include what you were trying to do, what happened instead, and screenshots if possible. This helps us fix things faster.</p>
  </div>

  <footer>
    Flow Support &middot; kai.x626@icloud.com
  </footer>

</div>

<script>
document.getElementById('supportForm').addEventListener('submit', function(e){
  e.preventDefault();
  const name = document.getElementById('name').value.trim();
  const email = document.getElementById('email').value.trim();
  const message = document.getElementById('message').value.trim();
  const status = document.getElementById('formStatus');

  if(!name || !email || !message){
    status.textContent = 'Please fill in all fields.';
    status.className = 'status error';
    return;
  }

  const subject = encodeURIComponent('Flow Support Request from ' + name);
  const body = encodeURIComponent(
    'Name: ' + name + '\n' +
    'Email: ' + email + '\n\n' +
    'Message:\n' + message
  );

  window.location.href = 'mailto:kai.x626@icloud.com?subject=' + subject + '&body=' + body;

  status.textContent = 'Opening your email app... if nothing happens, please email kai.x626@icloud.com directly.';
  status.className = 'status success';
});
</script>

</body>
</html>
