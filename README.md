
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#10264b">
  <meta name="description" content="LeapStart employee attendance portal.">
  <title>LeapStart | Employee Attendance</title>

  <style>
    :root {
      --navy: #10264b;
      --blue: #2463eb;
      --light-blue: #edf4ff;
      --text: #202b3c;
      --muted: #657187;
      --border: #e3e8f0;
      --white: #ffffff;
      --background: #f5f7fb;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: var(--background);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background: var(--navy);
      color: white;
      padding: 19px 6%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 16px;
      flex-wrap: wrap;
    }

    .brand {
      font-size: 23px;
      font-weight: 800;
      letter-spacing: .4px;
    }

    .brand span {
      color: #8bb5ff;
    }

    .header-label {
      font-size: 13px;
      color: #e0e9fa;
    }

    main {
      width: 100%;
      max-width: 850px;
      margin: auto;
      padding: 48px 20px;
      flex: 1;
    }

    .intro {
      text-align: center;
      margin-bottom: 32px;
    }

    .eyebrow {
      color: var(--blue);
      font-size: 12px;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    h1 {
      color: var(--navy);
      font-size: clamp(29px, 5vw, 42px);
      margin: 13px 0;
    }

    .intro p {
      max-width: 570px;
      margin: 0 auto;
      line-height: 1.7;
      color: var(--muted);
      font-size: 15px;
    }

    .card {
      background: var(--white);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 32px;
      box-shadow: 0 12px 35px rgba(16, 38, 75, .06);
    }

    .icon {
      width: 64px;
      height: 64px;
      border-radius: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 18px;
      background: var(--light-blue);
      color: var(--blue);
      font-size: 31px;
    }

    h2 {
      text-align: center;
      color: var(--navy);
      font-size: 23px;
      margin: 0 0 12px;
    }

    .card-description {
      color: var(--muted);
      text-align: center;
      font-size: 14px;
      line-height: 1.7;
      margin: 0 auto 24px;
      max-width: 520px;
    }

    .steps {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin: 25px 0;
    }

    .step {
      background: #f7f9fc;
      border: 1px solid var(--border);
      padding: 16px 12px;
      border-radius: 12px;
      text-align: center;
    }

    .step-number {
      width: 29px;
      height: 29px;
      border-radius: 50%;
      background: #dce8ff;
      color: var(--blue);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 13px;
      font-weight: 700;
      margin: 0 auto 10px;
    }

    .step strong {
      display: block;
      font-size: 13px;
      margin-bottom: 5px;
    }

    .step small {
      color: var(--muted);
      font-size: 12px;
      line-height: 1.5;
    }

    .attendance-button {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      width: 100%;
      padding: 17px 20px;
      border-radius: 10px;
      background: var(--blue);
      color: white;
      font-weight: 700;
      font-size: 16px;
      text-decoration: none;
      text-align: center;
      transition: background .2s, transform .2s;
    }

    .attendance-button:hover {
      background: #174fc8;
      transform: translateY(-1px);
    }

    .notice {
      margin-top: 18px;
      background: #f5f8ff;
      border: 1px solid #dce7ff;
      padding: 14px;
      border-radius: 10px;
      font-size: 12px;
      line-height: 1.7;
      color: #425474;
    }

    .notice strong {
      color: var(--navy);
    }

    footer {
      text-align: center;
      padding: 22px 16px;
      color: var(--muted);
      font-size: 12px;
      border-top: 1px solid var(--border);
      background: white;
    }

    @media (max-width: 540px) {
      header {
        padding: 17px 20px;
      }

      .brand {
        font-size: 20px;
      }

      main {
        padding: 32px 15px;
      }

      .card {
        padding: 23px 18px;
      }

      .steps {
        grid-template-columns: 1fr;
      }

      .step {
        display: flex;
        align-items: center;
        text-align: left;
        gap: 12px;
        padding: 12px;
      }

      .step-number {
        flex-shrink: 0;
        margin: 0;
      }
    }
  </style>
</head>

<body>
  <header>
    <div class="brand">Leap<span>Start</span></div>
    <div class="header-label">Employee Portal</div>
  </header>

  <main>
    <section class="intro">
      <div class="eyebrow">Employee Services</div>
      <h1>Employee Attendance</h1>
      <p>
        Welcome to the LeapStart attendance portal.
        Record your daily attendance through the official attendance system.
      </p>
    </section>

    <section class="card">
      <div class="icon" aria-hidden="true">✓</div>

      <h2>Mark Your Attendance</h2>

      <p class="card-description">
        Open the attendance system and sign in using your company Google
        account. Your registered employee details will be displayed
        automatically.
      </p>

      <div class="steps">
        <div class="step">
          <div class="step-number">1</div>
          <div>
            <strong>Sign in</strong>
            <small>Use your registered company Google account.</small>
          </div>
        </div>

        <div class="step">
          <div class="step-number">2</div>
          <div>
            <strong>Allow location</strong>
            <small>Enable location permission when requested.</small>
          </div>
        </div>

        <div class="step">
          <div class="step-number">3</div>
          <div>
            <strong>Check in</strong>
            <small>Submit attendance and confirm the result.</small>
          </div>
        </div>
      </div>

      <a
        class="attendance-button"
        href="https://script.google.com/macros/s/AKfycbyQSIir9sTPtzlncX0Thktz8lJcYWu5x1DlThpbAjbIodGXBXxx9_Ap168WXSw4O_tq/exec"
        target="_blank"
        rel="noopener noreferrer"
      >
        Open Attendance System
        <span aria-hidden="true">→</span>
      </a>

      <div class="notice">
        <strong>Important:</strong> Mark your own attendance using your
        registered company account. If your account is not recognized or
        attendance cannot be recorded, contact your administrator.
      </div>
    </section>
  </main>

  <footer>
    © <span id="year"></span> LeapStart. Employee Attendance Portal.
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
