# model_000
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Elaborate - Login</title>
    <style>
      :root {
        --bg: #f5f4ef;
        --card: #fffdf9;
        --panel: #f6efe8;
        --primary: #1f2f2e;
        --primary-light: #2a3f3d;
        --text: #1d1d1d;
        --muted: #6d6a66;
        --line: #e7e0d6;
        --accent: #d9b38a;
        --accent-soft: #f4e0c8;
        --error: #d86650;
        --shadow: 0 20px 60px rgba(25, 23, 20, 0.08);
      }

      * {
        box-sizing: border-box;
      }

      html, body {
        margin: 0;
        height: 100%;
        font-family: Inter, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        background: radial-gradient(circle at top, #fffefb 0%, #f5f1ea 32%, #efe8df 100%);
        color: var(--text);
      }

      body {
        display: grid;
        place-items: center;
      }

      .page {
        width: min(1200px, 92vw);
        min-height: 760px;
        display: grid;
        grid-template-columns: 1.05fr 0.95fr;
        background: rgba(255,255,255,0.58);
        border: 1px solid rgba(75, 63, 52, 0.08);
        border-radius: 32px;
        box-shadow: var(--shadow);
        overflow: hidden;
        backdrop-filter: blur(8px);
      }

      .brand-panel {
        position: relative;
        background:
          linear-gradient(135deg, rgba(255,255,255,0.15), rgba(255,255,255,0.02)),
          linear-gradient(160deg, #f3e8dc 0%, #e9dcc8 35%, #d9b48c 100%);
        padding: 38px 48px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
      }

      .brand-panel::before {
        content: "";
        position: absolute;
        inset: 0;
        background:
          radial-gradient(circle at 15% 20%, rgba(255,255,255,0.5), transparent 25%),
          radial-gradient(circle at 80% 30%, rgba(121, 104, 85, 0.12), transparent 25%),
          radial-gradient(circle at 100% 100%, rgba(255,255,255,0.25), transparent 35%);
        pointer-events: none;
      }

      .topbar,
      .content,
      .footer-note {
        position: relative;
        z-index: 1;
      }

      .topbar {
        display: flex;
        align-items: center;
        justify-content: space-between;
      }

      .brand {
        display: flex;
        align-items: center;
        gap: 12px;
        font-weight: 700;
        letter-spacing: 0.02em;
        color: var(--primary);
      }

      .brand-mark {
        width: 26px;
        height: 26px;
        border-radius: 8px;
        background: linear-gradient(135deg, #2b3c3b 0%, #1b2d2d 100%);
        position: relative;
        box-shadow: inset 0 0 0 1px rgba(255,255,255,0.2);
      }

      .brand-mark::before {
        content: "";
        position: absolute;
        width: 12px;
        height: 12px;
        border-radius: 50%;
        background: rgba(255,255,255,0.9);
        left: 7px;
        top: 7px;
        box-shadow: 0 0 0 3px rgba(255,255,255,0.18);
      }

      .mini-tag {
        font-size: 12px;
        color: var(--primary-light);
        border: 1px solid rgba(31,47,46,0.15);
        background: rgba(255,255,255,0.28);
        padding: 8px 12px;
        border-radius: 999px;
      }

      .content {
        padding: 40px 0 20px;
      }

      .eyebrow {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        padding: 8px 14px;
        border-radius: 999px;
        background: rgba(255,255,255,0.15);
        border: 1px solid rgba(30,42,40,0.08);
        font-size: 12px;
        letter-spacing: 0.12em;
        text-transform: uppercase;
        color: var(--primary);
      }

      .eyebrow::before {
        content: "";
        width: 8px;
        height: 8px;
        background: rgba(30,42,40,0.5);
        border-radius: 50%;
      }

      h1 {
        margin: 18px 0 18px;
        font-size: clamp(2.5rem, 4vw, 4rem);
        line-height: 0.96;
        letter-spacing: -0.06em;
        color: var(--primary);
        max-width: 440px;
      }

      .subtext {
        max-width: 440px;
        font-size: 1.05rem;
        line-height: 1.7;
        color: rgba(29, 29, 29, 0.7);
      }

      .feature-list {
        list-style: none;
        padding: 0;
        margin: 28px 0 0;
        display: grid;
        gap: 14px;
      }

      .feature-list li {
        display: flex;
        align-items: center;
        gap: 12px;
        color: var(--primary-light);
        font-weight: 500;
      }

      .feature-list li::before {
        content: "✓";
        display: grid;
        place-items: center;
        width: 22px;
        height: 22px;
        border-radius: 50%;
        background: rgba(255,255,255,0.5);
        border: 1px solid rgba(31,47,46,0.12);
        font-size: 14px;
        font-weight: 700;
      }

      .footer-note {
        color: rgba(29, 29, 29, 0.72);
        font-size: 0.96rem;
      }

      .login-panel {
        background: rgba(255,255,255,0.7);
        padding: 40px 42px;
        display: flex;
        align-items: center;
        justify-content: center;
      }

      .login-card {
        width: min(100%, 430px);
        background: rgba(255, 255, 255, 0.56);
        border: 1px solid rgba(75, 63, 52, 0.08);
        border-radius: 26px;
        padding: 32px 28px 26px;
        box-shadow: 0 12px 30px rgba(23, 20, 17, 0.04);
      }

      .login-header {
        margin-bottom: 24px;
      }

      .login-header h2 {
        margin: 0;
        font-size: 2rem;
        letter-spacing: -0.05em;
        color: var(--primary);
      }

      .login-header p {
        margin: 8px 0 0;
        color: var(--muted);
        font-size: 0.96rem;
      }

      .social-btns {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 10px;
        margin-bottom: 18px;
      }

      .social-btn {
        border: 1px solid var(--line);
        background: rgba(255,255,255,0.5);
        border-radius: 12px;
        padding: 12px 14px;
        font-weight: 600;
        color: var(--primary);
        cursor: pointer;
        transition: 0.2s ease;
      }

      .social-btn:hover {
        transform: translateY(-1px);
        border-color: rgba(31,47,46,0.2);
      }

      .divider {
        display: flex;
        align-items: center;
        gap: 14px;
        color: var(--muted);
        font-size: 0.8rem;
        margin: 20px 0 18px;
      }

      .divider::before,
      .divider::after {
        content: "";
        height: 1px;
        flex: 1;
        background: var(--line);
      }

      form {
        display: grid;
        gap: 16px;
      }

      .field {
        display: grid;
        gap: 8px;
      }

      label {
        font-size: 0.82rem;
        font-weight: 600;
        color: var(--primary-light);
      }

      .input-wrap {
        position: relative;
      }

      input {
        width: 100%;
        border: 1px solid var(--line);
        background: rgba(255,255,255,0.8);
        border-radius: 12px;
        padding: 14px 16px;
        font-size: 1rem;
        color: var(--text);
        outline: none;
        transition: border-color 0.2s ease, box-shadow 0.2s ease;
      }

      input:focus {
        border-color: rgba(29, 65, 61, 0.55);
        box-shadow: 0 0 0 4px rgba(31,47,46,0.06);
      }

      .password-toggle {
        position: absolute;
        right: 12px;
        top: 50%;
        transform: translateY(-50%);
        border: none;
        background: transparent;
        color: var(--muted);
        cursor: pointer;
        font-size: 0.8rem;
        font-weight: 600;
      }

      .row {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 10px;
        margin-top: -4px;
      }

      .remember {
        display: inline-flex;
        align-items: center;
        gap: 8px;
        font-size: 0.9rem;
        color: var(--primary-light);
      }

      .remember input {
        width: 16px;
        height: 16px;
        accent-color: var(--primary);
      }

      .link {
        color: var(--primary);
        text-decoration: none;
        font-size: 0.9rem;
        font-weight: 600;
      }

      .primary-btn {
        margin-top: 6px;
        width: 100%;
        border: none;
        border-radius: 12px;
        background: linear-gradient(135deg, #213b39 0%, #182c2d 100%);
        color: #fff;
        padding: 15px 18px;
        font-size: 1rem;
        font-weight: 700;
        cursor: pointer;
        transition: transform 0.2s ease, box-shadow 0.2s ease;
        box-shadow: 0 10px 20px rgba(25, 42, 41, 0.18);
      }

      .primary-btn:hover {
        transform: translateY(-1px);
      }

      .meta {
        text-align: center;
        margin-top: 22px;
        color: var(--muted);
        font-size: 0.92rem;
      }

      .meta a {
        color: var(--primary);
        text-decoration: none;
        font-weight: 700;
      }

      @media (max-width: 900px) {
        .page {
          grid-template-columns: 1fr;
          min-height: auto;
        }

        .brand-panel {
          min-height: 420px;
        }

        .login-panel {
          padding-top: 18px;
        }
      }

      @media (max-width: 520px) {
        .brand-panel,
        .login-panel {
          padding-left: 22px;
          padding-right: 22px;
        }

        .social-btns {
          grid-template-columns: 1fr;
        }

        .row {
          flex-direction: column;
          align-items: flex-start;
        }
      }
    </style>
  </head>
  <body>
    <div class="page">
      <div class="brand-panel">
        <div class="topbar">
          <div class="brand">
            <span class="brand-mark" aria-hidden="true"></span>
            <span>elaborate</span>
          </div>
          <span class="mini-tag">Secure access</span>
        </div>

        <div class="content">
          <div class="eyebrow">Health clarity</div>
          <h1>Lab results, illuminated.</h1>
          <p class="subtext">
            Understand your testing insights with guided explanations, safer decisions,
            and clearer conversations with your care team.
          </p>

          <ul class="feature-list">
            <li>Context-rich result explanations</li>
            <li>Actionable next steps and guidance</li>
            <li>Simple, secure access to your records</li>
          </ul>
        </div>

        <div class="footer-note">
          Trusted by people wanting more clarity about what their results mean.
        </div>
      </div>

      <div class="login-panel">
        <div class="login-card">
          <div class="login-header">
            <h2>Welcome back</h2>
            <p>Sign in to access your health insights</p>
          </div>

          <div class="social-btns">
            <button class="social-btn" type="button">Google</button>
            <button class="social-btn" type="button">Apple</button>
          </div>

          <div class="divider">or continue with email</div>

          <form id="loginForm">
            <div class="field">
              <label for="email">Email</label>
              <div class="input-wrap">
                <input type="email" id="email" placeholder="you@example.com" required />
              </div>
            </div>

            <div class="field">
              <label for="password">Password</label>
              <div class="input-wrap">
                <input type="password" id="password" placeholder="Enter your password" required />
                <button type="button" class="password-toggle" id="togglePassword">Show</button>
              </div>
            </div>

            <div class="row">
              <label class="remember">
                <input type="checkbox" />
                Remember me
              </label>
              <a href="#" class="link">Forgot password?</a>
            </div>

            <button class="primary-btn" type="submit">Sign in</button>
          </form>

          <div class="meta">
            New here? <a href="#">Create account</a>
          </div>
        </div>
      </div>
    </div>

    <script>
      const togglePassword = document.getElementById('togglePassword');
      const passwordInput = document.getElementById('password');

      togglePassword.addEventListener('click', () => {
        const isPassword = passwordInput.type === 'password';
        passwordInput.type = isPassword ? 'text' : 'password';
        togglePassword.textContent = isPassword ? 'Hide' : 'Show';
      });

      document.getElementById('loginForm').addEventListener('submit', (e) => {
        e.preventDefault();
        const email = document.getElementById('email').value.trim();
        const password = document.getElementById('password').value.trim();

        if (!email || !password) {
          alert('Please enter your email and password.');
          return;
        }

        alert('Login submitted for: ' + email);
      });
    </script>
  </body>
</html>
