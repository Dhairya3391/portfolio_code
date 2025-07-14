<script lang="ts">
  const projects = [
    {
      id: 1,
      name: "Quiz Application",
      description:
        "A web application featuring full CRUD operations, the ability to export data as Excel files, multiple theme support, and a polished, user-friendly UI.",
      technologies: [".NET Core", "ADO.NET"],
      status: "Completed",
      link: "https://github.com/Dhairya3391/QuizApplication",
      features: [
        "Full CRUD Operations",
        "Excel Export",
        "Multiple Themes",
        "User-friendly UI",
      ],
    },
    {
      id: 2,
      name: "ASP.NET with EF Core",
      description:
        "An ongoing college project focused on learning Entity Framework Core as part of B.Tech CSE 5th-semester coursework.",
      technologies: ["ASP.NET", "EF Core"],
      status: "In Progress",
      link: "https://github.com/Dhairya3391/MyWebApi",
      features: [
        "Entity Framework Core",
        "Database First Approach",
        "MVC Architecture",
        "College Project",
      ],
    },
    {
      id: 3,
      name: "Wallpaper Analyzer",
      description:
        "A data mining and machine learning project that uses regression, collection, and clustering techniques to differentiate wallpapers and assign aesthetic ratings.",
      technologies: ["Python", "PyTorch"],
      status: "Completed",
      link: "https://github.com/Dhairya3391/wallpaper-analyzerV2",
      features: [
        "Machine Learning",
        "Image Analysis",
        "Clustering",
        "Aesthetic Rating",
      ],
    },
    {
      id: 4,
      name: "Wallpaper Setter",
      description:
        "A Rust-based tool for setting wallpapers on a phone using the Termux API. It's fully safe, faster than the native API, and auto-crops/adjusts images to fit the screen size.",
      technologies: ["Rust", "Termux API"],
      status: "Completed",
      link: "https://github.com/Dhairya3391/wallpaper-setter",
      features: [
        "Rust Performance",
        "Auto-crop Images",
        "Termux Integration",
        "Safe & Fast",
      ],
    },
  ];

  function getStatusColor(status: string) {
    switch (status) {
      case "Completed":
        return "text-green-400";
      case "In Progress":
        return "text-yellow-400";
      default:
        return "text-terminal-light";
    }
  }
</script>

<div class="container mx-auto px-4 sm:px-6 py-8 sm:py-16">
  <div class="terminal-window max-w-6xl mx-auto">
    <div class="terminal-header">
      <span class="text-terminal-pink text-sm sm:text-base"
        >dhairya@portfolio:~$</span
      >
      <span class="text-terminal-light ml-2 text-sm sm:text-base"
        >ls projects/ -la</span
      >
    </div>

    <div class="terminal-content p-4 sm:p-6">
      <div class="space-y-6 sm:space-y-8">
        <div
          class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-2"
        >
          <h2 class="text-xl sm:text-2xl font-bold text-terminal-pink">
            Projects Directory
          </h2>
          <span class="text-terminal-light opacity-70 text-xs sm:text-sm">
            total {projects.length} projects
          </span>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 sm:gap-6">
          {#each projects as project}
            <div class="project-card group">
              <div class="project-header">
                <div
                  class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-2"
                >
                  <h3 class="text-terminal-pink font-bold text-base sm:text-lg">
                    📁 {project.name}
                  </h3>
                  <span
                    class="text-xs px-2 py-1 rounded border {getStatusColor(
                      project.status
                    )} border-current self-start sm:self-auto"
                  >
                    {project.status}
                  </span>
                </div>
              </div>

              <div class="project-content">
                <p
                  class="text-terminal-light text-xs sm:text-sm mb-3 sm:mb-4 leading-relaxed"
                >
                  {project.description}
                </p>

                <div class="mb-3 sm:mb-4">
                  <h4
                    class="text-terminal-pink text-xs sm:text-sm font-semibold mb-2"
                  >
                    Technologies:
                  </h4>
                  <div class="flex flex-wrap gap-1 sm:gap-2">
                    {#each project.technologies as tech}
                      <span class="tech-tag text-xs">
                        {tech}
                      </span>
                    {/each}
                  </div>
                </div>

                <div class="mb-3 sm:mb-4">
                  <h4
                    class="text-terminal-pink text-xs sm:text-sm font-semibold mb-2"
                  >
                    Key Features:
                  </h4>
                  <ul class="space-y-1">
                    {#each project.features as feature}
                      <li class="text-terminal-light text-xs sm:text-sm">
                        <span class="text-terminal-pink">></span>
                        {feature}
                      </li>
                    {/each}
                  </ul>
                </div>

                <div class="project-footer">
                  <a
                    href={project.link}
                    target="_blank"
                    rel="noopener noreferrer"
                    class="project-link text-xs sm:text-sm"
                  >
                    <span class="text-terminal-pink">$</span> git clone {project.link}
                  </a>
                </div>
              </div>
            </div>
          {/each}
        </div>

        <!-- <div
          class="mt-8 p-4 bg-gray-800 bg-opacity-30 rounded border border-terminal-purple"
        >
          <p class="text-terminal-light text-sm">
            <span class="text-terminal-pink">Note:</span> These are placeholder links.
            Replace them with your actual GitHub repository URLs or live demo links.
          </p>
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
    padding: 8px 12px;
    border-bottom: 1px solid #333;
    border-radius: 8px 8px 0 0;
    font-family: "Fira Code", monospace;
    word-wrap: break-word;
    overflow-wrap: break-word;
  }

  .terminal-content {
    background: #121212;
    border-radius: 0 0 8px 8px;
  }

  .project-card {
    background: rgba(106, 13, 173, 0.1);
    border: 1px solid rgba(106, 13, 173, 0.3);
    border-radius: 8px;
    overflow: hidden;
    transition: all 0.3s ease;
  }

  .project-card:hover {
    background: rgba(106, 13, 173, 0.15);
    border-color: rgba(106, 13, 173, 0.5);
    transform: translateY(-4px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
  }

  .project-header {
    background: rgba(45, 45, 45, 0.5);
    padding: 12px;
    border-bottom: 1px solid rgba(106, 13, 173, 0.3);
  }

  .project-content {
    padding: 12px;
  }

  .tech-tag {
    background: rgba(255, 179, 186, 0.2);
    color: #ffb3ba;
    padding: 2px 6px;
    border-radius: 4px;
    font-size: 0.75rem;
    border: 1px solid rgba(255, 179, 186, 0.3);
  }

  .project-footer {
    margin-top: 12px;
    padding-top: 12px;
    border-top: 1px solid rgba(106, 13, 173, 0.3);
  }

  .project-link {
    color: #e0e0e0;
    text-decoration: none;
    font-size: 0.875rem;
    font-family: "Fira Code", monospace;
    transition: all 0.2s ease;
    display: block;
    padding: 6px 8px;
    background: rgba(0, 0, 0, 0.3);
    border-radius: 4px;
    border: 1px solid transparent;
    word-wrap: break-word;
    overflow-wrap: break-word;
    white-space: pre-wrap;
  }

  .project-link:hover {
    color: #ffb3ba;
    background: rgba(0, 0, 0, 0.5);
    border-color: rgba(255, 179, 186, 0.3);
    transform: translateX(4px);
  }

  /* Mobile-specific improvements */
  @media (max-width: 640px) {
    .terminal-header {
      font-size: 0.875rem;
      padding: 8px 12px;
    }

    .terminal-content {
      padding: 12px;
    }

    .project-header {
      padding: 12px;
    }

    .project-content {
      padding: 12px;
    }

    .tech-tag {
      font-size: 0.75rem;
      padding: 2px 6px;
    }

    .project-link {
      font-size: 0.75rem;
      padding: 6px 8px;
    }
  }

  /* Desktop improvements */
  @media (min-width: 640px) {
    .terminal-header {
      padding: 12px 16px;
    }

    .terminal-content {
      padding: 24px;
    }

    .project-header {
      padding: 16px;
    }

    .project-content {
      padding: 16px;
    }

    .tech-tag {
      padding: 4px 8px;
    }

    .project-link {
      padding: 8px;
    }
  }
</style>
