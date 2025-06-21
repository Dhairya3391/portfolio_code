<script>
  let { commandCallback } = $props();

  let isVisible = $state(false);
  let command = $state("");
  let inputRef = $state();

  function toggleTerminal() {
    isVisible = !isVisible;
    if (isVisible && inputRef) {
      setTimeout(() => inputRef.focus(), 100);
    }
  }

  function handleSubmit(event) {
    event.preventDefault();
    if (command.trim()) {
      commandCallback(command.trim());
      command = "";
    }
  }

  function handleKeydown(event) {
    if (event.key === "Escape") {
      isVisible = false;
    }
  }
</script>

<!-- Terminal Toggle Button -->
<button
  class="fixed bottom-4 right-4 z-40 terminal-toggle"
  onclick={toggleTerminal}
  title="Open Terminal"
>
  <span class="text-lg">⌨️</span>
</button>

<!-- Terminal Overlay -->
{#if isVisible}
  <div class="fixed inset-0 z-50 flex items-end justify-center p-4">
    <div
      class="terminal-overlay"
      role="presentation"
      onclick={toggleTerminal}
      onkeydown={() => {}}
    ></div>
    <div class="terminal-popup">
      <div class="terminal-header">
        <div class="flex items-center justify-between">
          <span class="text-terminal-pink">dhairya@portfolio:~$</span>
          <button
            class="text-terminal-light hover:text-terminal-pink"
            onclick={toggleTerminal}
          >
            ✕
          </button>
        </div>
      </div>

      <div class="terminal-body">
        <form onsubmit={handleSubmit} class="flex items-center space-x-2">
          <span class="text-terminal-pink">$</span>
          <input
            bind:this={inputRef}
            bind:value={command}
            type="text"
            class="terminal-input"
            placeholder="Type a command (ls, whoami, cat skills.txt, retro, etc.)"
            onkeydown={handleKeydown}
          />
        </form>

        <div class="mt-4 text-sm text-terminal-light opacity-70">
          <p>
            Available commands: ls, whoami, cat about.txt, cat skills.txt, ls
            projects, contact, retro, clear
          </p>
          <p class="mt-1">
            Press <kbd class="bg-terminal-purple px-1 rounded text-xs">Esc</kbd>
            to close
          </p>
        </div>
      </div>
    </div>
  </div>
{/if}

<style>
  .terminal-toggle {
    background: rgba(106, 13, 173, 0.9);
    border: 1px solid #6a0dad;
    color: #ffb3ba;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: all 0.3s ease;
    backdrop-filter: blur(10px);
  }

  .terminal-toggle:hover {
    background: rgba(106, 13, 173, 1);
    transform: scale(1.1);
    box-shadow: 0 4px 20px rgba(106, 13, 173, 0.4);
  }

  .terminal-overlay {
    position: absolute;
    inset: 0;
    background: rgba(0, 0, 0, 0.7);
    backdrop-filter: blur(4px);
    cursor: pointer;
  }

  .terminal-popup {
    background: #1a1a1a;
    border: 1px solid #333;
    border-radius: 8px;
    width: 100%;
    max-width: 600px;
    position: relative;
    z-index: 10;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
  }

  .terminal-header {
    background: #2d2d2d;
    padding: 12px 16px;
    border-bottom: 1px solid #333;
    border-radius: 8px 8px 0 0;
    font-family: "Fira Code", monospace;
  }

  .terminal-body {
    background: #121212;
    padding: 16px;
    border-radius: 0 0 8px 8px;
  }

  .terminal-input {
    background: transparent;
    border: none;
    color: #e0e0e0;
    font-family: "Fira Code", monospace;
    font-size: 14px;
    outline: none;
    flex: 1;
    padding: 4px 0;
  }

  .terminal-input::placeholder {
    color: rgba(224, 224, 224, 0.5);
  }

  kbd {
    font-family: inherit;
    font-size: 0.75rem;
  }
</style>
