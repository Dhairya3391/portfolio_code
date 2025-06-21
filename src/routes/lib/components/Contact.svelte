<div class="container mx-auto px-4 py-16">
  <div class="terminal-window max-w-4xl mx-auto">
    <div class="terminal-header">
      <span class="text-terminal-pink">dhairya@portfolio:~$</span>
      <span class="text-terminal-light ml-2">cat contact.txt</span>
    </div>

    <div class="terminal-content p-6">
      <div class="space-y-8">
        <h2 class="text-2xl font-bold text-terminal-pink mb-6">
          Contact Information
        </h2>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <!-- Email Section -->
          <div class="contact-section">
            <h3 class="text-terminal-pink font-bold mb-4 flex items-center">
              <span class="mr-2">📧</span> Email Addresses
            </h3>
            <div class="space-y-3">
              <div class="command-line">
                <span class="text-terminal-pink">$</span>
                <span class="text-terminal-light ml-2"
                  >echo "dhairyaadroja3391@gmail.com"</span
                >
              </div>
              <div class="output">
                <a href="mailto:dhairyaadroja3391@gmail.com" class="email-link">
                  dhairyaadroja3391@gmail.com
                </a>
                <span class="text-terminal-light opacity-70 text-sm ml-2"
                  >(Primary)</span
                >
              </div>

              <div class="command-line mt-4">
                <span class="text-terminal-pink">$</span>
                <span class="text-terminal-light ml-2"
                  >echo "noobokay8580@gmail.com"</span
                >
              </div>
              <div class="output">
                <a href="mailto:noobokay8580@gmail.com" class="email-link">
                  noobokay8580@gmail.com
                </a>
                <span class="text-terminal-light opacity-70 text-sm ml-2"
                  >(Secondary)</span
                >
              </div>
            </div>
          </div>

          <!-- Social Links Section -->
          <div class="contact-section">
            <h3 class="text-terminal-pink font-bold mb-4 flex items-center">
              <span class="mr-2">🔗</span> Social Links
            </h3>
            <div class="space-y-3">
              <div class="command-line">
                <span class="text-terminal-pink">$</span>
                <span class="text-terminal-light ml-2"
                  >git clone https://github.com/Dhairya3391</span
                >
              </div>
              <div class="output">
                <a
                  href="https://github.com/Dhairya3391"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="social-link"
                >
                  🐙 GitHub Profile
                </a>
              </div>

              <div class="command-line mt-4">
                <span class="text-terminal-pink">$</span>
                <span class="text-terminal-light ml-2"
                  >curl -L linkedin.com/in/adroja-dhairya</span
                >
              </div>
              <div class="output">
                <a
                  href="https://linkedin.com/in/adroja-dhairya"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="social-link"
                >
                  💼 LinkedIn Profile
                </a>
              </div>

              <div class="command-line mt-4">
                <span class="text-terminal-pink">$</span>
                <span class="text-terminal-light ml-2"
                  >wget twitter.com/AdrojaDhairya1</span
                >
              </div>
              <div class="output">
                <a
                  href="https://twitter.com/AdrojaDhairya1"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="social-link"
                >
                  🐦 Twitter Profile
                </a>
              </div>
            </div>
          </div>
        </div>

        <!-- Resume Section -->
        <div class="contact-section full-width">
          <h3 class="text-terminal-pink font-bold mb-4 flex items-center">
            <span class="mr-2">📄</span> Resume
          </h3>
          <div class="command-line">
            <span class="text-terminal-pink">$</span>
            <span class="text-terminal-light ml-2">wget resume.pdf</span>
          </div>
          <div class="output mt-2">
            <a href="resume.pdf" class="resume-link" download>
              📥 Download Resume (PDF)
            </a>
            <p class="text-terminal-light opacity-70 text-sm mt-2">
              Replace this link with your actual resume PDF URL
            </p>
          </div>
        </div>

        <!-- Quick Contact Commands
        <div
          class="mt-8 p-4 bg-gray-800 bg-opacity-30 rounded border border-terminal-purple"
        >
          <h4 class="text-terminal-pink font-semibold mb-3">
            Quick Contact Commands:
          </h4>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-2 text-sm">
            <div>
              <span class="text-terminal-pink">$</span>
              <span class="text-terminal-light"
                >mail dhairyaadroja3391@gmail.com</span
              >
            </div>
            <div>
              <span class="text-terminal-pink">$</span>
              <span class="text-terminal-light"
                >open linkedin.com/in/adroja-dhairya</span
              >
            </div>
            <div>
              <span class="text-terminal-pink">$</span>
              <span class="text-terminal-light"
                >git clone github.com/Dhairya3391</span
              >
            </div>
            <div>
              <span class="text-terminal-pink">$</span>
              <span class="text-terminal-light">follow @AdrojaDhairya1</span>
            </div>
          </div>
        </div> -->
      </div>
    </div>
  </div>
</div>

<style>
  .terminal-window {
    background: #1a1a1a;
    border: 1px solid #333;
    border-radius: 8px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  }

  .terminal-header {
    background: #2d2d2d;
    padding: 12px 16px;
    border-bottom: 1px solid #333;
    border-radius: 8px 8px 0 0;
    font-family: "Fira Code", monospace;
  }

  .terminal-content {
    background: #121212;
    border-radius: 0 0 8px 8px;
  }

  .contact-section {
    background: rgba(106, 13, 173, 0.1);
    border: 1px solid rgba(106, 13, 173, 0.3);
    border-radius: 8px;
    padding: 20px;
    transition: all 0.3s ease;
  }

  .contact-section:hover {
    background: rgba(106, 13, 173, 0.15);
    border-color: rgba(106, 13, 173, 0.5);
  }

  .contact-section.full-width {
    grid-column: 1 / -1;
  }

  .command-line {
    font-family: "Fira Code", monospace;
    background: rgba(0, 0, 0, 0.3);
    padding: 8px 12px;
    border-radius: 4px;
    border: 1px solid rgba(106, 13, 173, 0.3);
  }

  .output {
    margin-left: 20px;
    margin-top: 8px;
  }

  .email-link,
  .social-link,
  .resume-link {
    color: #ffb3ba;
    text-decoration: none;
    transition: all 0.2s ease;
    display: inline-block;
  }

  .email-link:hover,
  .social-link:hover,
  .resume-link:hover {
    color: #e0e0e0;
    transform: translateX(4px);
  }

  .resume-link {
    background: rgba(106, 13, 173, 0.2);
    border: 1px solid #6a0dad;
    padding: 8px 16px;
    border-radius: 4px;
    font-weight: bold;
    transition: all 0.2s ease;
  }

  .resume-link:hover {
    background: rgba(106, 13, 173, 0.4);
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(106, 13, 173, 0.3);
  }
</style>
