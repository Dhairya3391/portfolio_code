<script lang="ts">
  import { onMount } from "svelte";
  import Hero from "./lib/components/Hero.svelte";
  import About from "./lib/components/About.svelte";
  import Skills from "./lib/components/Skills.svelte";
  import Projects from "./lib/components/Projects.svelte";
  import Contact from "./lib/components/Contact.svelte";
  import Terminal from "./lib/components/Terminal.svelte";
  import Navigation from "./lib/components/Navigation.svelte";

  let showEasterEgg = $state("");
  let currentSection = "hero";

  const retroQuotes = [
    "It's-a me, Mario!",
    "Thank you Mario! But our princess is in another castle!",
    "Gotta go fast! - Sonic",
    "Way past cool! - Sonic",
    "FINISH HIM! - Mortal Kombat",
    "Get over here! - Scorpion",
    "Your princess is in another castle!",
    "Game Over - Insert Coin to Continue",
  ];

  function handleCommand(command: string) {
    const cmd = command.toLowerCase().trim();

    if (cmd === "retro") {
      const randomQuote =
        retroQuotes[Math.floor(Math.random() * retroQuotes.length)];
      showEasterEgg = randomQuote;
      setTimeout(() => (showEasterEgg = ""), 3000);
      return;
    }

    // Handle navigation commands
    switch (cmd) {
      case "ls":
      case "ls -la":
        scrollToSection("navigation");
        break;
      case "whoami":
      case "cat bio":
      case "cat about.txt":
        scrollToSection("about");
        break;
      case "cat skills.txt":
      case "skills":
        scrollToSection("skills");
        break;
      case "ls projects":
      case "cd projects":
      case "cat projects.txt":
        scrollToSection("projects");
        break;
      case "contact":
      case "cat contact.txt":
        scrollToSection("contact");
        break;
      case "clear":
        window.scrollTo({ top: 0, behavior: "smooth" });
        break;
    }
  }

  function scrollToSection(sectionId: string) {
    const element = document.getElementById(sectionId);
    if (element) {
      element.scrollIntoView({ behavior: "smooth" });
      currentSection = sectionId;
    }
  }

  onMount(() => {
    // Smooth scroll behavior
    document.documentElement.style.scrollBehavior = "smooth";
  });
</script>

<main class="min-h-screen bg-terminal-dark text-terminal-light font-mono">
  <!-- Easter Egg Display -->
  {#if showEasterEgg !== ""}
    <div
      class="fixed top-4 right-4 z-50 bg-terminal-purple text-white px-4 py-2 rounded border border-terminal-pink animate-pulse"
    >
      <span class="text-terminal-pink">$</span>
      {showEasterEgg}
    </div>
  {/if}

  <!-- Hero Section -->
  <section id="hero" class="min-h-screen">
    <Hero commandDispatch={handleCommand} />
  </section>

  <!-- Navigation Commands -->
  <section id="navigation">
    <Navigation command={handleCommand} />
  </section>

  <!-- About Section -->
  <section id="about">
    <About />
  </section>

  <!-- Skills Section -->
  <section id="skills">
    <Skills />
  </section>

  <!-- Projects Section -->
  <section id="projects">
    <Projects />
  </section>

  <!-- Contact Section -->
  <section id="contact">
    <Contact />
  </section>

  <!-- Terminal Component for global commands -->
  <Terminal commandCallback={handleCommand} />
</main>

<style>
  :global(html) {
    scroll-behavior: smooth;
  }

  :global(body) {
    margin: 0;
    padding: 0;
    font-family: "Fira Code", "Courier New", monospace;
    background-color: #121212;
    color: #e0e0e0;
  }

  :global(*) {
    box-sizing: border-box;
  }
</style>
