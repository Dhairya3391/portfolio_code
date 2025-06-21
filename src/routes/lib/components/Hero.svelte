<script lang="ts">
  import { onMount } from "svelte";

  let { commandDispatch } = $props();

  let typewriterText = $state("");
  let showCursor = $state(true);
  let showWhoami = $state(false);
  let showTagline = $state(false);
  let commandExecuted = $state(false);

  const command = "dhairya@portfolio:~$ whoami";
  const name = "Adroja Dhairya";
  const tagline =
    "I don't just follow trends — I live at the edge where innovation happens.";

  onMount(() => {
    typeCommand();

    // Cursor blink animation
    const cursorInterval = setInterval(() => {
      showCursor = !showCursor;
    }, 500);

    return () => clearInterval(cursorInterval);
  });

  async function typeCommand() {
    for (let i = 0; i <= command.length; i++) {
      typewriterText = command.slice(0, i);
      await new Promise((resolve) => setTimeout(resolve, 50));
    }
    await new Promise((resolve) => setTimeout(resolve, 200));
  }

  function executeCommand() {
    if (!commandExecuted) {
      commandExecuted = true;
      showWhoami = true;
      showTagline = true;
    }
  }

  function handleKeyPress(event: KeyboardEvent) {
    if (event.key === "Enter") {
      executeCommand();
    }
  }
</script>

<div class="flex items-center justify-center min-h-screen p-4">
  <div class="terminal-window max-w-4xl w-full">
    <div class="terminal-header">
      <div class="flex space-x-2">
        <div class="w-3 h-3 bg-red-500 rounded-full"></div>
        <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
        <div class="w-3 h-3 bg-green-500 rounded-full"></div>
      </div>
      <div class="text-center text-sm text-terminal-light opacity-70">
        dhairya@portfolio - Terminal
      </div>
    </div>

    <div class="terminal-content p-6 space-y-4">
      <!-- Command Line -->
      <div class="flex items-center space-x-2">
        <span class="text-terminal-pink">$</span>
        <span class="text-terminal-light">{typewriterText}</span>
        {#if showCursor}
          <span class="bg-terminal-light text-terminal-dark px-1">_</span>
        {/if}
      </div>

      <!-- Output -->
      {#if showWhoami}
        <div class="space-y-2 animate-fade-in">
          <div class="text-terminal-pink text-2xl font-bold">{name}</div>
          {#if showTagline}
            <div class="text-terminal-light opacity-90 animate-fade-in">
              {tagline}
            </div>
          {/if}
        </div>
      {/if}

      <!-- Interactive Prompt -->
      {#if !commandExecuted}
        <div class="mt-8 space-y-2">
          <p class="text-terminal-light opacity-70 text-sm">
            Press <kbd class="bg-terminal-purple px-2 py-1 rounded text-xs"
              >Enter</kbd
            >
            or
            <button
              class="text-terminal-pink hover:text-terminal-light underline transition-colors"
              onclick={executeCommand}
              onkeypress={handleKeyPress}
            >
              click here
            </button> to execute command
          </p>
        </div>
      {:else}
        <div class="mt-8 space-y-2 animate-fade-in">
          <p class="text-terminal-light opacity-70 text-sm">
            Type <span class="text-terminal-pink">ls</span> to explore available
            sections
          </p>
          <div class="flex flex-wrap gap-2 mt-4">
            <button
              class="command-button"
              onclick={() => commandDispatch("ls")}
            >
              ls
            </button>
            <button
              class="command-button"
              onclick={() => commandDispatch("cat about.txt")}
            >
              cat about.txt
            </button>
            <button
              class="command-button"
              onclick={() => commandDispatch("cat skills.txt")}
            >
              cat skills.txt
            </button>
          </div>
        </div>
      {/if}
    </div>
  </div>
</div>

<svelte:window onkeypress={handleKeyPress} />

<style>
  .terminal-window {
    background: #1a1a1a;
    border: 1px solid #333;
    border-radius: 8px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
  }

  .terminal-header {
    background: #2d2d2d;
    padding: 12px 16px;
    border-bottom: 1px solid #333;
    border-radius: 8px 8px 0 0;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .terminal-content {
    background: #121212;
    border-radius: 0 0 8px 8px;
    min-height: 200px;
  }

  .command-button {
    background: rgba(106, 13, 173, 0.2);
    border: 1px solid #6a0dad;
    color: #ffb3ba;
    padding: 6px 12px;
    border-radius: 4px;
    font-family: inherit;
    font-size: 0.875rem;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .command-button:hover {
    background: rgba(106, 13, 173, 0.4);
    color: #e0e0e0;
    transform: translateY(-1px);
  }

  kbd {
    font-family: inherit;
    font-size: 0.75rem;
  }

  @keyframes fade-in {
    from {
      opacity: 0;
      transform: translateY(10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .animate-fade-in {
    animation: fade-in 0.5s ease-out;
  }
</style>
