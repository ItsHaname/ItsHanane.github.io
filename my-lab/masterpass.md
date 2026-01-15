---
layout: default
title: Master Password - Technical Documentation
---

<style>
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

body {
  background: #0a0e1a;
  min-height: 100vh;
  margin: 0;
  font-family: 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 60px 40px;
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.4), rgba(0, 20, 40, 0.6));
}

/* Header Section */
.doc-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 50px 40px;
  background: linear-gradient(135deg, rgba(15, 23, 42, 0.95), rgba(30, 77, 123, 0.15));
  border-radius: 15px;
  border-left: 5px solid #3b82f6;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.3);
  animation: fadeIn 0.8s ease-out;
}

.doc-title {
  font-size: 2.8em;
  color: #e2e8f0;
  margin: 0 0 15px 0;
  font-weight: 700;
  letter-spacing: -0.5px;
}

.doc-subtitle {
  font-size: 1.3em;
  color: #94a3b8;
  margin: 0 0 25px 0;
  font-weight: 400;
}

.doc-meta {
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
  margin-top: 25px;
  padding-top: 25px;
  border-top: 1px solid rgba(59, 130, 246, 0.2);
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #cbd5e1;
  font-size: 0.95em;
}

.meta-label {
  color: #60a5fa;
  font-weight: 600;
}

/* Table of Contents */
.toc-section {
  background: rgba(15, 23, 42, 0.9);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 12px;
  padding: 30px;
  margin-bottom: 40px;
}

.toc-title {
  color: #3b82f6;
  font-size: 1.5em;
  margin: 0 0 20px 0;
  font-weight: 600;
}

.toc-list {
  list-style: none;
  margin: 0;
  padding: 0;
}

.toc-list li {
  padding: 10px 0;
  border-bottom: 1px solid rgba(59, 130, 246, 0.1);
}

.toc-list li:last-child {
  border-bottom: none;
}

.toc-list a {
  color: #cbd5e1;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 10px;
  transition: all 0.3s;
  padding-left: 20px;
}

.toc-list a:hover {
  color: #60a5fa;
  padding-left: 25px;
}

.toc-number {
  color: #60a5fa;
  font-weight: 600;
  min-width: 30px;
}

/* Content Sections */
.content-section {
  background: rgba(15, 23, 42, 0.9);
  border: 1px solid rgba(59, 130, 246, 0.2);
  border-radius: 12px;
  padding: 40px;
  margin-bottom: 30px;
  animation: fadeIn 1s ease-out;
}

.section-number {
  display: inline-block;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  padding: 5px 15px;
  border-radius: 20px;
  font-size: 0.9em;
  font-weight: 600;
  margin-bottom: 15px;
}

.content-section h2 {
  color: #e2e8f0;
  font-size: 2em;
  margin: 10px 0 25px 0;
  font-weight: 600;
  letter-spacing: -0.3px;
}

.content-section h3 {
  color: #60a5fa;
  font-size: 1.5em;
  margin: 30px 0 15px 0;
  font-weight: 600;
}

.content-section h4 {
  color: #93c5fd;
  font-size: 1.2em;
  margin: 25px 0 12px 0;
  font-weight: 600;
}

.content-section p {
  color: #cbd5e1;
  line-height: 1.9;
  margin-bottom: 18px;
  font-size: 1.05em;
}

.content-section ul, .content-section ol {
  color: #cbd5e1;
  line-height: 1.8;
  margin-bottom: 20px;
  padding-left: 25px;
}

.content-section li {
  margin-bottom: 12px;
}

.content-section strong {
  color: #e2e8f0;
  font-weight: 600;
}

/* Abstract/Summary Box */
.abstract-box {
  background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(37, 99, 235, 0.05));
  border-left: 4px solid #3b82f6;
  border-radius: 8px;
  padding: 25px;
  margin: 25px 0;
}

.abstract-title {
  color: #60a5fa;
  font-size: 1.1em;
  font-weight: 600;
  margin: 0 0 15px 0;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.abstract-box p {
  margin: 0 0 12px 0;
  font-size: 1.05em;
}

/* Technical Specifications */
.spec-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
  margin: 30px 0;
}

.spec-box {
  background: rgba(30, 77, 123, 0.1);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 10px;
  padding: 25px;
  transition: all 0.3s;
}

.spec-box:hover {
  border-color: #60a5fa;
  box-shadow: 0 5px 20px rgba(59, 130, 246, 0.2);
}

.spec-label {
  color: #60a5fa;
  font-size: 0.9em;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  margin-bottom: 10px;
}

.spec-value {
  color: #e2e8f0;
  font-size: 1.1em;
  font-weight: 500;
}

/* Code Blocks - Professional Style */
.code-container {
  margin: 25px 0;
}

.code-header {
  background: #0f172a;
  color: #60a5fa;
  padding: 12px 20px;
  border-radius: 8px 8px 0 0;
  border: 1px solid #1e40af;
  border-bottom: none;
  font-family: 'Courier New', monospace;
  font-size: 0.9em;
  display: flex;
  align-items: center;
  gap: 10px;
}

.code-block {
  background: #0a0f1e;
  border: 1px solid #1e40af;
  border-radius: 0 0 8px 8px;
  padding: 25px;
  font-family: 'Courier New', monospace;
  color: #cbd5e1;
  overflow-x: auto;
  font-size: 0.95em;
  line-height: 1.7;
}

.code-block.standalone {
  border-radius: 8px;
}

.prompt {
  color: #10b981;
  font-weight: bold;
}

.comment {
  color: #64748b;
  font-style: italic;
}

.output {
  color: #93c5fd;
}

/* Professional Tables */
.data-table {
  width: 100%;
  border-collapse: collapse;
  margin: 25px 0;
  background: rgba(15, 23, 42, 0.6);
  border-radius: 8px;
  overflow: hidden;
}

.data-table thead {
  background: linear-gradient(135deg, rgba(59, 130, 246, 0.3), rgba(37, 99, 235, 0.2));
}

.data-table th {
  color: #e2e8f0;
  padding: 18px;
  text-align: left;
  font-weight: 600;
  font-size: 0.95em;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  border-bottom: 2px solid rgba(59, 130, 246, 0.4);
}

.data-table td {
  padding: 18px;
  border-bottom: 1px solid rgba(59, 130, 246, 0.15);
  color: #cbd5e1;
  font-size: 0.95em;
}

.data-table tbody tr:hover {
  background: rgba(59, 130, 246, 0.05);
}

.data-table tbody tr:last-child td {
  border-bottom: none;
}

/* Info Boxes - Professional Alerts */
.info-box {
  border-radius: 8px;
  padding: 20px 25px;
  margin: 25px 0;
  border-left: 4px solid;
  display: flex;
  gap: 15px;
}

.info-box.note {
  background: rgba(59, 130, 246, 0.08);
  border-color: #3b82f6;
}

.info-box.warning {
  background: rgba(251, 191, 36, 0.08);
  border-color: #fbbf24;
}

.info-box.important {
  background: rgba(239, 68, 68, 0.08);
  border-color: #ef4444;
}

.info-box.success {
  background: rgba(16, 185, 129, 0.08);
  border-color: #10b981;
}

.info-icon {
  font-size: 1.5em;
  flex-shrink: 0;
}

.info-content h4 {
  margin: 0 0 8px 0;
  font-size: 1.1em;
  font-weight: 600;
}

.info-box.note .info-icon,
.info-box.note h4 { color: #60a5fa; }

.info-box.warning .info-icon,
.info-box.warning h4 { color: #fbbf24; }

.info-box.important .info-icon,
.info-box.important h4 { color: #ef4444; }

.info-box.success .info-icon,
.info-box.success h4 { color: #10b981; }

.info-content p {
  margin: 0;
  color: #cbd5e1;
  line-height: 1.7;
}

/* Step-by-step Process */
.process-steps {
  margin: 30px 0;
}

.process-step {
  display: flex;
  gap: 20px;
  margin-bottom: 30px;
  padding: 25px;
  background: rgba(30, 77, 123, 0.08);
  border-radius: 10px;
  border-left: 3px solid #3b82f6;
}

.step-indicator {
  flex-shrink: 0;
  width: 45px;
  height: 45px;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.3em;
  font-weight: 700;
  box-shadow: 0 4px 15px rgba(59, 130, 246, 0.3);
}

.step-content h4 {
  margin: 0 0 12px 0;
  color: #e2e8f0;
  font-size: 1.2em;
}

.step-content p {
  margin: 0;
  color: #cbd5e1;
  line-height: 1.7;
}

/* Footer Navigation */
.doc-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 60px;
  padding-top: 40px;
  border-top: 2px solid rgba(59, 130, 246, 0.2);
}

.footer-link {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 15px 30px;
  background: rgba(59, 130, 246, 0.15);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 8px;
  color: #60a5fa;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s;
}

.footer-link:hover {
  background: rgba(59, 130, 246, 0.25);
  border-color: #60a5fa;
  transform: translateY(-2px);
  box-shadow: 0 5px 20px rgba(59, 130, 246, 0.2);
}

/* Responsive Design */
@media (max-width: 768px) {
  .container {
    padding: 30px 20px;
  }
  
  .doc-title {
    font-size: 2em;
  }
  
  .content-section {
    padding: 25px;
  }
  
  .doc-footer {
    flex-direction: column;
    gap: 15px;
  }
  
  .spec-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="container">
  
  <!-- Document Header -->
  <header class="doc-header">
    <h1 class="doc-title">Master Password</h1>
    <p class="doc-subtitle">Algorithmic Password Management System</p>
    <div class="doc-meta">
      <div class="meta-item">
        <span class="meta-label">Platform:</span>
        <span>Arch Linux</span>
      </div>
      <div class="meta-item">
        <span class="meta-label">Version:</span>
        <span>2.6</span>
      </div>
      <div class="meta-item">
        <span class="meta-label">Category:</span>
        <span>Security & Authentication</span>
      </div>
    </div>
  </header>

  <!-- Table of Contents -->
  <nav class="toc-section">
    <h2 class="toc-title">📑 Table of Contents</h2>
    <ol class="toc-list">
      <li><a href="#overview"><span class="toc-number">1.</span> Executive Overview</a></li>
      <li><a href="#architecture"><span class="toc-number">2.</span> System Architecture</a></li>
      <li><a href="#installation"><span class="toc-number">3.</span> Installation & Configuration</a></li>
      <li><a href="#implementation"><span class="toc-number">4.</span> Implementation Guide</a></li>
      <li><a href="#advanced"><span class="toc-number">5.</span> Advanced Features</a></li>
      <li><a href="#security"><span class="toc-number">6.</span> Security Analysis</a></li>
      <li><a href="#integration"><span class="toc-number">7.</span> System Integration</a></li>
      <li><a href="#conclusion"><span class="toc-number">8.</span> Conclusion & Best Practices</a></li>
    </ol>
  </nav>

  <!-- Section 1: Executive Overview -->
  <section id="overview" class="content-section">
    <span class="section-number">SECTION 1</span>
    <h2>Executive Overview</h2>
    
   <div class="abstract-box">
      <h3 class="abstract-title">Abstract</h3>
      <p>Master Password represents a paradigm shift in password management by implementing a <strong>stateless, algorithmic approach</strong> to credential generation. Unlike traditional password managers that rely on encrypted databases, Master Password derives passwords deterministically using cryptographic algorithms, eliminating the need for storage, synchronization, and backup mechanisms.</p>
    </div>

  <h3>1.1 Problem Statement</h3>
    <p>Traditional password management solutions face several critical challenges:</p>
    <ul>
      <li><strong>Single Point of Failure:</strong> Encrypted password databases represent a vulnerable target for attackers</li>
      <li><strong>Synchronization Complexity:</strong> Multi-device access requires complex sync mechanisms</li>
      <li><strong>Backup Dependency:</strong> Loss of the database results in irretrievable credentials</li>
      <li><strong>Trust Requirements:</strong> Users must trust third-party cloud providers with encrypted data</li>
    </ul>

   <h3>1.2 Solution Architecture</h3>
    <p>Master Password addresses these challenges through a stateless generation model:</p>
    
   <div class="spec-grid">
      <div class="spec-box">
        <div class="spec-label">Generation Method</div>
        <div class="spec-value">Deterministic Algorithm</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">Storage Requirement</div>
        <div class="spec-value">Zero Bytes</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">Synchronization</div>
        <div class="spec-value">Not Required</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">Platform Support</div>
        <div class="spec-value">Cross-Platform</div>
      </div>
    </div>

   <h3>1.3 Core Advantages</h3>
    <div class="spec-grid">
      <div class="spec-box">
        <div class="spec-label">✓ Zero Storage</div>
        <div class="spec-value">No database to lose or compromise</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">✓ Portability</div>
        <div class="spec-value">Works on any device instantly</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">✓ Privacy</div>
        <div class="spec-value">No cloud synchronization required</div>
      </div>
      <div class="spec-box">
        <div class="spec-label">✓ Open Source</div>
        <div class="spec-value">Transparent, auditable codebase</div>
      </div>
    </div>

  <div class="info-box important">
      <div class="info-icon">⚠️</div>
      <div class="info-content">
        <h4>Critical Requirement</h4>
        <p>The master password and full name must be memorized with absolute precision. Any variation in input parameters will generate different passwords. This system prioritizes security over password recovery convenience.</p>
      </div>
    </div>
  </section>

  <!-- Section 2: System Architecture -->
  <section id="architecture" class="content-section">
    <span class="section-number">SECTION 2</span>
    <h2>System Architecture</h2>

   <h3>2.1 Cryptographic Foundation</h3>
    <p>Master Password employs the <strong>scrypt</strong> key derivation function (KDF), specifically designed to be computationally intensive and memory-hard, providing robust protection against brute-force attacks.</p>

   <div class="abstract-box">
      <h3 class="abstract-title">Algorithm Components</h3>
      <p><strong>Input Parameters:</strong></p>
      <ul>
        <li>User's full name (identifier)</li>
        <li>Master password (secret)</li>
        <li>Site name (context)</li>
        <li>Counter value (versioning)</li>
      </ul>
      <p><strong>Output:</strong> Deterministic, cryptographically-secure password</p>
    </div>

  <h3>2.2 Generation Process</h3>
    <p>The password generation follows a multi-stage cryptographic pipeline:</p>

   <div class="code-container">
      <div class="code-header">🔐 Cryptographic Pipeline</div>
      <div class="code-block">
Master Key = scrypt(master_password, "com.lyndir.masterpassword" + user_name)
Site Key = HMAC-SHA256(Master Key, site_name + counter)
Password = Template_Encoding(Site Key, password_type)</div>
    </div>

  <h3>2.3 Technical Specifications</h3>
    <table class="data-table">
      <thead>
        <tr>
          <th>Component</th>
          <th>Specification</th>
          <th>Purpose</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>KDF Algorithm</strong></td>
          <td>scrypt (N=32768, r=8, p=2)</td>
          <td>Master key derivation</td>
        </tr>
        <tr>
          <td><strong>MAC Algorithm</strong></td>
          <td>HMAC-SHA256</td>
          <td>Site-specific key generation</td>
        </tr>
        <tr>
          <td><strong>Key Length</strong></td>
          <td>512 bits (64 bytes)</td>
          <td>Cryptographic strength</td>
        </tr>
        <tr>
          <td><strong>Encoding</strong></td>
          <td>Template-based</td>
          <td>Password format control</td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- Section 3: Installation & Configuration -->
  <section id="installation" class="content-section">
    <span class="section-number">SECTION 3</span>
    <h2>Installation & Configuration</h2>

  <h3>3.1 Prerequisites</h3>
    <p>Required system components:</p>
    <ul>
      <li>Arch Linux (or derivatives)</li>
      <li>AUR helper (yay, paru, or manual makepkg)</li>
      <li>Base development tools</li>
    </ul>

  <h3>3.2 Installation Process</h3>
    
   <div class="process-steps">
      <div class="process-step">
        <div class="step-indicator">1</div>
        <div class="step-content">
          <h4>Install from AUR</h4>
          <div class="code-container">
            <div class="code-block standalone">
<span class="prompt"># Using yay (recommended)</span>
yay -S masterpassword

<span class="prompt"># Using paru</span>
paru -S masterpassword

<span class="prompt"># Manual installation</span>
git clone https://aur.archlinux.org/masterpassword.git
cd masterpassword
makepkg -si</div>
          </div>
        </div>
      </div>

   <div class="process-step">
        <div class="step-indicator">2</div>
        <div class="step-content">
          <h4>Verify Installation</h4>
          <div class="code-container">
            <div class="code-block standalone">
<span class="prompt">$ mpw --version</span>
<span class="output">Master Password v2.6 - Algorithm v3</span></div>
          </div>
        </div>
      </div>

  <div class="process-step">
        <div class="step-indicator">3</div>
        <div class="step-content">
          <h4>Configure User Profile</h4>
          <div class="code-container">
            <div class="code-block standalone">
<span class="prompt"># Create configuration directory</span>
mkdir -p ~/.config/mpw

<span class="prompt"># Edit configuration file</span>
nano ~/.config/mpw/mpw.conf</div>
          </div>
        </div>
      </div>
    </div>

   <h3>3.3 Configuration File Structure</h3>
    <div class="code-container">
      <div class="code-header">📝 ~/.config/mpw/mpw.conf</div>
      <div class="code-block">
<span class="comment"># User identification</span>
fullName=Your Full Name

<span class="comment"># Default password type (long, maximum, medium, basic, short, pin)</span>
defaultType=long

<span class="comment"># Default counter value</span>
defaultCounter=1</div>
    </div>

   <div class="info-box success">
      <div class="info-icon">✓</div>
      <div class="info-content">
        <h4>Configuration Complete</h4>
        <p>Master Password is now configured for command-line usage. The system will use these defaults when parameters are not explicitly specified.</p>
      </div>
    </div>
  </section>

  <!-- Section 4: Implementation Guide -->
  <section id="implementation" class="content-section">
    <span class="section-number">SECTION 4</span>
    <h2>Implementation Guide</h2>

   <h3>4.1 Basic Usage Pattern</h3>
    
   <h4>Interactive Mode</h4>
    <p>Recommended for initial usage and testing:</p>
    <div class="code-container">
      <div class="code-block standalone">
<span class="prompt">$ mpw</span>
<span class="output">Your full name: </span>John Doe
<span class="output">Your master password: </span>••••••••••••••••
<span class="output">Site name: </span>github.com
<span class="output">
[ github.com ]: Xoja2*HufpDuvu</span></div>
    </div>

  <h4>Command-Line Mode</h4>
    <p>Optimized for automation and scripting:</p>
    <div class="code-container">
      <div class="code-block standalone">
<span class="prompt">$ mpw -u "John Doe" github.com</span>
<span class="output">Your master password: </span>••••••••••••••••
<span class="output">Xoja2*HufpDuvu</span></div>
    </div>

  <h3>4.2 System Integration</h3>
    
   <h4>Clipboard Integration</h4>
    <p>For X11 environments:</p>
    <div class="code-container">
      <div class="code-block standalone">
<span class="prompt"># Copy to clipboard (X11)</span>
mpw -u "John Doe" github.com | xclip -selection clipboard

<span class="prompt"># Copy to clipboard (Wayland)</span>
mpw -u "John Doe" github.com | wl-copy</div>
    </div>

   <h4>Shell Alias Configuration</h4>
    <div class="code-container">
      <div class="code-header">📝 ~/.bashrc or ~/.zshrc</div>
      <div class="code-block">
<span class="comment"># Master Password alias</span>
alias mpw-clip='mpw -u "John Doe" "$1" | xclip -sel c && echo "✓ Password copied"'

<span class="comment"># Usage</span>
<span class="prompt">$ mpw-clip github.com</span>
<span class="output">✓ Password copied to clipboard</span></div>
    </div>

  <div class="info-box note">
      <div class="info-icon">💡</div>
      <div class="info-content">
        <h4>Security Note</h4>
        <p>Always clear clipboard history after use. Consider implementing automatic clipboard clearing after 30 seconds for enhanced security.</p>
      </div>
    </div>
  </section>

  <!-- Section 5: Advanced Features -->
  <section id="advanced" class="content-section">
    <span class="section-number">SECTION 5</span>
    <h2>Advanced Features</h2>

  <h3>5.1 Password Type Templates</h3>
    <p>Master Password supports multiple output formats optimized for different use cases:</p>

   <table class="data-table">
      <thead>
        <tr>
          <th>Type</th>
          <th>Flag</th>
          <th>Pattern</th>
          <th>Example Output</th>
          <th>Use Case</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Maximum</strong></td>
          <td><code>-t x</code></td>
          <td>20 chars, all types</td>
          <td>w!3*Jugr1@Foli7%Huha</td>
          <td>High-security accounts</td>
        </tr>
        <tr>
          <td><strong>Long</strong></td>
          <td><code>-t l</code></td>
          <td>CvcvnoCvc (default)</td>
