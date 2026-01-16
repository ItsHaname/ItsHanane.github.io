---
layout: default
title: System Maintenance
nav: lab
---

<style>
/* Arrière-plan binaire global */
body {
  background-color: #0a0e1a;
  background-image: 
    linear-gradient(rgba(10, 14, 26, 0.9), rgba(10, 14, 26, 0.9)),
    url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100' height='100' viewBox='0 0 100 100'%3E%3Ctext x='10' y='30' fill='rgba(59, 130, 246, 0.05)' font-family='monospace' font-size='12'%3E01101%3C/text%3E%3Ctext x='50' y='70' fill='rgba(59, 130, 246, 0.05)' font-family='monospace' font-size='12'%3E10101%3C/text%3E%3Ctext x='80' y='20' fill='rgba(59, 130, 246, 0.05)' font-family='monospace' font-size='12'%3E01%3C/text%3E%3Ctext x='30' y='90' fill='rgba(59, 130, 246, 0.05)' font-family='monospace' font-size='12'%3E110%3C/text%3E%3C/svg%3E");
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes pulse {
  0%, 100% { box-shadow: 0 0 20px rgba(59, 130, 246, 0.3); }
  50% { box-shadow: 0 0 30px rgba(59, 130, 246, 0.6); }
}

.article-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 40px 20px;
  animation: fadeIn 0.8s ease-out;
}

.article-header {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px;
  background: rgba(15, 23, 42, 0.85);
  border: 2px solid #3b82f6;
  border-radius: 20px;
  position: relative;
  overflow: hidden;
}

.article-header::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.1), transparent);
  animation: scan 3s infinite;
}

@keyframes scan {
  0% { left: -100%; }
  100% { left: 100%; }
}

.badge-number {
  display: inline-block;
  width: 60px;
  height: 60px;
  line-height: 60px;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  border-radius: 50%;
  color: white;
  font-size: 2em;
  font-weight: bold;
  margin-bottom: 20px;
  box-shadow: 0 0 20px rgba(59, 130, 246, 0.5);
}

.article-title {
  font-size: 3em;
  color: #60a5fa;
  margin: 20px 0;
  font-weight: 900;
  letter-spacing: 3px;
  text-shadow: 0 0 20px rgba(96, 165, 250, 0.5);
}

.article-subtitle {
  color: #94a3b8;
  font-size: 1.2em;
  line-height: 1.6;
  max-width: 700px;
  margin: 0 auto;
}

.status-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 10px 20px;
  background: rgba(59, 130, 246, 0.1);
  border: 1px solid #3b82f6;
  border-radius: 20px;
  color: #60a5fa;
  font-size: 0.9em;
  margin-top: 20px;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #3b82f6;
  border-radius: 50%;
  animation: pulse 2s infinite;
}

.content-section {
  background: rgba(15, 23, 42, 0.7);
  border: 1px solid rgba(59, 130, 246, 0.3);
  border-radius: 15px;
  padding: 40px;
  margin: 30px 0;
}

.content-section h2 {
  color: #3b82f6;
  font-size: 2em;
  margin-bottom: 20px;
  padding-bottom: 15px;
  border-bottom: 2px solid rgba(59, 130, 246, 0.3);
}

.content-section h3 {
  color: #60a5fa;
  font-size: 1.5em;
  margin: 30px 0 15px 0;
}

.content-section p {
  color: #cbd5e1;
  line-height: 1.8;
  margin: 15px 0;
  font-size: 1.05em;
}

.code-block {
  background: rgba(10, 14, 26, 0.8);
  border: 1px solid #1e40af;
  border-radius: 10px;
  padding: 25px;
  margin: 20px 0;
  overflow-x: auto;
}

.code-block pre {
  margin: 0;
  color: #60a5fa;
  font-family: 'Courier New', monospace;
  font-size: 1.1em;
  line-height: 1.8;
}

.code-block code {
  color: #60a5fa;
  font-size: 1.1em;
}

.command-line {
  color: #3b82f6;
  font-family: 'Courier New', monospace;
  background: rgba(10, 14, 26, 0.6);
  padding: 5px 10px;
  border-radius: 4px;
  font-size: 1.05em;
}

.info-box {
  background: rgba(59, 130, 246, 0.1);
  border-left: 4px solid #3b82f6;
  padding: 20px;
  margin: 20px 0;
  border-radius: 5px;
}

.info-box strong {
  color: #60a5fa;
}

.warning-box {
  background: rgba(239, 68, 68, 0.1);
  border-left: 4px solid #ef4444;
  padding: 20px;
  margin: 20px 0;
  border-radius: 5px;
}

.warning-box strong {
  color: #f87171;
}

.step-list {
  counter-reset: step-counter;
  list-style: none;
  padding: 0;
}

.step-list li {
  counter-increment: step-counter;
  margin: 30px 0;
  padding-left: 60px;
  position: relative;
}

.step-list li::before {
  content: counter(step-counter);
  position: absolute;
  left: 0;
  top: 0;
  width: 40px;
  height: 40px;
  line-height: 40px;
  text-align: center;
  background: linear-gradient(135deg, #3b82f6, #2563eb);
  color: white;
  border-radius: 50%;
  font-weight: bold;
  box-shadow: 0 0 15px rgba(59, 130, 246, 0.4);
}

.key-points {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin: 30px 0;
}

.key-point {
  background: rgba(15, 23, 42, 0.6);
  border: 1px solid #1e40af;
  border-radius: 10px;
  padding: 20px;
  transition: all 0.3s;
}

.key-point:hover {
  border-color: #3b82f6;
  box-shadow: 0 5px 20px rgba(59, 130, 246, 0.3);
  transform: translateY(-5px);
}

.key-point h4 {
  color: #3b82f6;
  margin: 0 0 10px 0;
}

.key-point p {
  color: #94a3b8;
  margin: 0;
  font-size: 0.95em;
}

.script-container {
  background: rgba(10, 14, 26, 0.9);
  border: 2px solid #3b82f6;
  border-radius: 15px;
  padding: 30px;
  margin: 30px 0;
  box-shadow: 0 0 30px rgba(59, 130, 246, 0.2);
}

.script-header {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 20px;
  padding-bottom: 15px;
  border-bottom: 1px solid rgba(59, 130, 246, 0.3);
}

.script-icon {
  color: #3b82f6;
  font-size: 1.5em;
}

.script-title {
  color: #60a5fa;
  font-size: 1.3em;
  margin: 0;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
  background: rgba(15, 23, 42, 0.6);
  border-radius: 10px;
  overflow: hidden;
}

table th {
  background: rgba(59, 130, 246, 0.2);
  color: #60a5fa;
  padding: 15px;
  text-align: left;
  font-weight: 600;
}

table td {
  padding: 15px;
  color: #cbd5e1;
  border-bottom: 1px solid rgba(59, 130, 246, 0.1);
}

table tr:last-child td {
  border-bottom: none;
}

.article-footer {
  text-align: center;
  margin-top: 60px;
  padding: 30px;
  background: rgba(15, 23, 42, 0.5);
  border-radius: 15px;
  border-top: 2px solid rgba(59, 130, 246, 0.3);
}

.article-meta {
  color: #64748b;
  font-size: 0.9em;
}

.back-link {
  display: inline-block;
  margin-top: 20px;
  padding: 12px 30px;
  background: rgba(59, 130, 246, 0.1);
  border: 1px solid #3b82f6;
  border-radius: 25px;
  color: #60a5fa;
  text-decoration: none;
  transition: all 0.3s;
}

.back-link:hover {
  background: #3b82f6;
  color: white;
  box-shadow: 0 5px 20px rgba(59, 130, 246, 0.4);
}

@media (max-width: 768px) {
  .article-title { font-size: 2em; }
  .content-section { padding: 25px; }
  .step-list li { padding-left: 50px; }
  .key-points { grid-template-columns: 1fr; }
  .code-block pre { font-size: 1em; }
}
</style>

<div class="article-container">
  <div class="article-header">
    <div class="badge-number">2</div>
    <h1 class="article-title">SYSTEM MAINTENANCE</h1>
    <p class="article-subtitle">Essential commands and practices to keep your Arch system healthy and running smoothly without breaking things.</p>
    <div class="status-badge">
      <span class="status-dot"></span>
      <span>ARCH LINUX LAB SERIES</span>
    </div>
  </div>

  <div class="content-section">
    <h2>Why Regular Maintenance</h2>
    <p>Arch Linux follows a rolling release model, receiving constant updates. Unlike Ubuntu or Fedora with scheduled releases, Arch requires regular maintenance to stay clean and performant. A weekly 15-minute routine prevents file accumulation and keeps your system stable.</p>
    
  <div class="key-points">
      <div class="key-point">
        <h4>Clean System</h4>
        <p>Remove unused packages and cached files</p>
      </div>
      <div class="key-point">
        <h4>Optimal Performance</h4>
        <p>Keep disk space free and services running</p>
      </div>
      <div class="key-point">
        <h4>Prevent Issues</h4>
        <p>Catch problems before they become critical</p>
      </div>
    </div>
  </div>

  <div class="content-section">
    <h2>Weekly Routine in 9 Steps</h2>
    
   <ul class="step-list">
      <li>
        <h3>Check Arch News</h3>
        <p>Always visit <span class="command-line">archlinux.org/news</span> before updating. Some updates require manual intervention. This step can save you hours of troubleshooting.</p>
      </li>
      
   <li>
        <h3>Update System</h3>
        <div class="code-block">
<pre><code># With pacman
sudo pacman -Syu

# With yay (AUR helper)
yay -Syu</code></pre>
        </div>
        <div class="info-box">
          <strong>Important:</strong> Always reboot after kernel updates to use the latest version.
        </div>
      </li>
      
  <li>
        <h3>Clean Package Cache</h3>
        <div class="code-block">
<pre><code># Keep last 3 versions of each package
sudo paccache -r

# Remove all versions of uninstalled packages
sudo paccache -ruk0</code></pre>
        </div>
        <p>This typically frees between 500 MB to 2 GB of disk space on my system.</p>
      </li>
      
  <li>
        <h3>Remove Orphan Packages</h3>
        <div class="code-block">
<pre><code># List orphan packages
pacman -Qtdq

# Remove orphan packages
sudo pacman -Qtdq | sudo pacman -Rns -</code></pre>
        </div>
        <p>Orphan packages are dependencies no longer needed by any installed package.</p>
      </li>
      
  <li>
        <h3>Manage Configuration Files</h3>
        <div class="code-block">
<pre><code># Find .pacnew and .pacsave files
sudo find /etc -name "*.pacnew" -o -name "*.pacsave"

# Merge interactively
sudo DIFFPROG=vimdiff pacdiff

# or with meld (graphical)
sudo DIFFPROG=meld pacdiff</code></pre>
        </div>
        <p>When pacman updates a package you've modified, it creates these backup files that need merging.</p>
      </li>
      
   <li>
        <h3>Clean Systemd Journals</h3>
        <div class="code-block">
<pre><code># Check current size
journalctl --disk-usage

# Keep only last 2 weeks
sudo journalctl --vacuum-time=2weeks</code></pre>
        </div>
      </li>
      
   <li>
        <h3>Check Failed Services</h3>
        <div class="code-block">
<pre><code># List failed services
systemctl --failed

# Investigate specific service
journalctl -u service-name</code></pre>
        </div>
      </li>
      
   <li>
        <h3>Clean User Cache</h3>
        <div class="code-block">
<pre><code># Check cache usage
du -sh ~/.cache/*

# Clean thumbnails
rm -rf ~/.cache/thumbnails/*

# Clean yay/paru cache
yay -Sc</code></pre>
        </div>
      </li>
      
  <li>
        <h3>Check Disk Space</h3>
        <div class="code-block">
<pre><code># Overview
df -h

# Detailed analysis (install ncdu if needed)
ncdu /</code></pre>
        </div>
      </li>
    </ul>
  </div>

  <div class="content-section">
    <h2>Automation Script</h2>
    
<div class="script-container">
      <div class="script-header">
        <span class="script-icon">#!/bin/bash</span>
        <h3 class="script-title">arch-maintenance.sh</h3>
      </div>
      
 <div class="code-block">
<pre><code>#!/bin/bash

echo "═══════════════════════════════════════════"
echo "  Arch Linux Weekly Maintenance"
echo "═══════════════════════════════════════════"
echo ""

read -p "Have you checked archlinux.org/news? (y/n) " -n 1 -r
echo ""
if [[ ! $REPLY =~ ^[Yy]$ ]]; then
    echo "Please check news before continuing."
    exit 1
fi

echo "→ Updating system..."
yay -Syu

echo ""
echo "→ Cleaning package cache..."
sudo paccache -r
sudo paccache -ruk0

echo ""
echo "→ Searching for orphan packages..."
orphans=$(pacman -Qtdq)
if [ -n "$orphans" ]; then
    echo "$orphans"
    read -p "Remove these packages? (y/n) " -n 1 -r
    echo ""
    if [[ $REPLY =~ ^[Yy]$ ]]; then
        sudo pacman -Qtdq | sudo pacman -Rns -
    fi
else
    echo "✓ No orphan packages found"
fi

echo ""
echo "→ Searching for .pacnew/.pacsave files..."
pacnew_files=$(sudo find /etc -name "*.pacnew" -o -name "*.pacsave" 2>/dev/null)
if [ -n "$pacnew_files" ]; then
    echo "$pacnew_files"
    echo "Use 'sudo pacdiff' to merge them"
else
    echo "✓ No configuration files to merge"
fi

echo ""
echo "→ Cleaning systemd journals..."
echo "Current size: $(journalctl --disk-usage | grep -oP '\d+\.\d+[GM]')"
sudo journalctl --vacuum-time=2weeks

echo ""
echo "→ Checking services..."
failed=$(systemctl --failed --no-pager --no-legend)
if [ -n "$failed" ]; then
    echo "⚠ Failed services:"
    echo "$failed"
else
    echo "✓ All services running correctly"
fi

echo ""
echo "→ Disk space:"
df -h / /home | grep -v tmpfs

echo ""
echo "═══════════════════════════════════════════"
echo "  Maintenance Complete"
echo "═══════════════════════════════════════════"</code></pre>
  </div>
    </div>
    
  <div class="info-box">
      <strong>Installation:</strong>
      <div class="code-block" style="margin-top: 10px;">
<pre><code># Create the file
nano ~/Scripts/arch-maintenance.sh

# Make executable
chmod +x ~/Scripts/arch-maintenance.sh

# Run it
~/Scripts/arch-maintenance.sh</code></pre>
  </div>
    </div>
  </div>

  <div class="content-section">
    <h2>Monthly Tasks</h2>
    <p>In addition to weekly maintenance, perform these tasks monthly:</p>
    
   <div class="key-points">
      <div class="key-point">
        <h4>Update Mirrorlist</h4>
        <p>Use reflector for fastest servers</p>
      </div>
      <div class="key-point">
        <h4>Firmware Updates</h4>
        <p>Run fwupdmgr update</p>
      </div>
      <div class="key-point">
        <h4>Full Backup</h4>
        <p>Complete system snapshot with Timeshift</p>
      </div>
      <div class="key-point">
        <h4>Refresh GPG Keys</h4>
        <p>Keep package signing keys current</p>
      </div>
    </div>
  </div>

  <div class="content-section">
    <h2>Critical Rules</h2>
    
   <div class="warning-box">
      <strong>Never Do:</strong>
      <table>
        <tr>
          <td><span class="command-line">pacman -Sy package</span></td>
          <td>Always use <span class="command-line">-Syu</span> for full updates</td>
        </tr>
        <tr>
          <td>Ignore Arch news</td>
          <td>Some updates require manual intervention</td>
        </tr>
        <tr>
          <td>Force conflicting updates</td>
          <td>Understand conflicts before proceeding</td>
        </tr>
        <tr>
          <td>Skip backups</td>
          <td>Always have bootable USB ready</td>
        </tr>
      </table>
    </div>
  </div>

  <div class="content-section">
    <h2>Quick Reference</h2>
    <div class="code-block">
<pre><code># Complete update
sudo pacman -Syu

# System cleanup
sudo paccache -r && sudo paccache -ruk0
sudo pacman -Qtdq | sudo pacman -Rns -
sudo journalctl --vacuum-time=2weeks

# System checks
systemctl --failed
df -h
pacman -Qdt</code></pre>
    </div>
  </div>

  <div class="content-section">
    <h2>Conclusion</h2>
    <p>This 15-minute weekly routine keeps my Arch Linux system stable and performant. Since adopting this discipline, I haven't had any major issues requiring reinstallation.</p>
    
  <p>Arch's advantage is transparency and total control over your system. Regular maintenance investment pays off with long-term stability and performance.</p>
  </div>

  <div class="article-footer">
    <p class="article-meta">ARCH LINUX LAB SERIES — ARTICLE 2/5</p>
    <p class="article-meta">Published January 16, 2026</p>
    <a href="/my-lab/" class="back-link">← BACK TO LAB</a>
  </div>
</div>
