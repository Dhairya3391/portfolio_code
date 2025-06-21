<div class="container mx-auto px-4 py-16">
  <div class="terminal-window max-w-6xl mx-auto">
    <div class="terminal-header">
      <span class="text-terminal-pink">dhairya@portfolio:~$</span>
      <span class="text-terminal-light ml-2">cat skills.txt</span>
    </div>
    
    <div class="terminal-content p-6">
      <div class="space-y-8">
        <h2 class="text-2xl font-bold text-terminal-pink mb-6">Technical Skills</h2>
        
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
          <!-- Programming Languages -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">📝</span> Programming Languages
            </h3>
            <div class="space-y-2">
              {#each ['C', 'Go', 'Java', 'Python', 'JavaScript', 'Bash Script', 'Rust'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>

          <!-- Web Technologies -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">🌐</span> Web Technologies
            </h3>
            <div class="space-y-2">
              {#each ['HTML5', 'CSS/SASS', 'JavaScript (Node.js, jQuery)', 'Flask', 'FastAPI', 'Svelte', 'SvelteKit'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>

          <!-- Databases -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">🗄️</span> Databases
            </h3>
            <div class="space-y-2">
              {#each ['Microsoft SQL Server', 'MongoDB', 'MySQL', 'PostgreSQL', 'SQLite'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>

          <!-- DevOps & Tools -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">⚙️</span> DevOps & Tools
            </h3>
            <div class="space-y-2">
              {#each ['AWS', 'Heroku', 'Vercel', 'Docker', 'Kubernetes', 'GitHub Actions', 'Nginx'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>

          <!-- Data Science & ML -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">🤖</span> Data Science & ML
            </h3>
            <div class="space-y-2">
              {#each ['Matplotlib', 'NumPy', 'Pandas', 'TensorFlow', 'PyTorch', 'OpenCV'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>

          <!-- Other -->
          <div class="skill-category">
            <h3 class="text-terminal-pink font-bold mb-3 flex items-center">
              <span class="mr-2">🔧</span> Other Technologies
            </h3>
            <div class="space-y-2">
              {#each ['Arduino', 'Raspberry Pi', 'FFmpeg', 'OpenGL', 'Termux API'] as skill}
                <div class="skill-item">
                  <span class="text-terminal-pink">></span>
                  <span class="text-terminal-light ml-2">{skill}</span>
                </div>
              {/each}
            </div>
          </div>
        </div>

        <div class="mt-8 p-4 bg-gray-800 bg-opacity-30 rounded border border-terminal-purple">
          <p class="text-terminal-light text-sm">
            <span class="text-terminal-pink">Note:</span> This list represents my current technical stack. 
            I'm always learning and exploring new technologies to expand my skillset.
          </p>
        </div>
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
    font-family: 'Fira Code', monospace;
  }

  .terminal-content {
    background: #121212;
    border-radius: 0 0 8px 8px;
  }

  .skill-category {
    background: rgba(106, 13, 173, 0.1);
    border: 1px solid rgba(106, 13, 173, 0.3);
    border-radius: 8px;
    padding: 20px;
    transition: all 0.3s ease;
  }

  .skill-category:hover {
    background: rgba(106, 13, 173, 0.15);
    border-color: rgba(106, 13, 173, 0.5);
    transform: translateY(-2px);
  }

  .skill-item {
    display: flex;
    align-items: center;
    padding: 4px 0;
    transition: all 0.2s ease;
  }

  .skill-item:hover {
    background: rgba(255, 179, 186, 0.1);
    border-radius: 4px;
    padding-left: 8px;
  }
</style>
