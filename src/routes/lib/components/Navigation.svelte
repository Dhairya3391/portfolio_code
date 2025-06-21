<script>
  let { command } = $props();

  const sections = [
    {
      name: "about.txt",
      command: "cat about.txt",
      description: "Personal information and background",
    },
    {
      name: "skills.txt",
      command: "cat skills.txt",
      description: "Technical skills and expertise",
    },
    {
      name: "projects/",
      command: "ls projects",
      description: "Portfolio of completed projects",
    },
    {
      name: "contact.txt",
      command: "cat contact.txt",
      description: "Get in touch and social links",
    },
    {
      name: "resume.pdf",
      command: "download resume",
      description: "Download my resume",
    },
  ];

  function executeCommand(cmd) {
    command(cmd);
  }
</script>

<div class="container mx-auto px-4 py-16">
  <div class="terminal-window max-w-4xl mx-auto">
    <div class="terminal-header">
      <span class="text-terminal-pink">dhairya@portfolio:~$</span>
      <span class="text-terminal-light ml-2">ls -la</span>
    </div>

    <div class="terminal-content p-6">
      <div class="space-y-3">
        <div class="text-terminal-light opacity-70 text-sm mb-4">
          total {sections.length} items
        </div>

        {#each sections as section, index}
          <div
            class="flex items-center justify-between group hover:bg-gray-800 hover:bg-opacity-30 p-2 rounded transition-all duration-200"
          >
            <div class="flex items-center space-x-4 flex-1">
              <span class="text-terminal-pink text-sm w-12">
                {section.name.includes(".") ? "-rw-r--r--" : "drwxr-xr-x"}
              </span>
              <button
                class="text-terminal-light hover:text-terminal-pink transition-colors text-left"
                onclick={() => executeCommand(section.command)}
              >
                {section.name}
              </button>
            </div>
            <div class="text-terminal-light opacity-50 text-sm hidden md:block">
              {section.description}
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-8 pt-4 border-t border-gray-700">
        <p class="text-terminal-light opacity-70 text-sm mb-3">
          Quick commands:
        </p>
        <div class="flex flex-wrap gap-2">
          {#each ["whoami", "cat about.txt", "cat skills.txt", "ls projects", "retro"] as cmd}
            <button
              class="command-button text-xs"
              onclick={() => executeCommand(cmd)}
            >
              {cmd}
            </button>
          {/each}
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
    font-family: "Fira Code", monospace;
  }

  .terminal-content {
    background: #121212;
    border-radius: 0 0 8px 8px;
  }

  .command-button {
    background: rgba(106, 13, 173, 0.2);
    border: 1px solid #6a0dad;
    color: #ffb3ba;
    padding: 4px 8px;
    border-radius: 4px;
    font-family: inherit;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .command-button:hover {
    background: rgba(106, 13, 173, 0.4);
    color: #e0e0e0;
    transform: translateY(-1px);
  }
</style>
