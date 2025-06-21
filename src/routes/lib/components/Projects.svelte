<script>
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
      link: "https://github.com/Dhairya3391/MyWebApi", // Placeholder
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
      link: "https://github.com/Dhairya3391/wallpaper-setter", // Placeholder
      features: [
        "Rust Performance",
        "Auto-crop Images",
        "Termux Integration",
        "Safe & Fast",
      ],
    },
  ];

  function getStatusColor(status) {
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

<div class="container mx-auto px-4 py-16">
  <div class="terminal-window max-w-6xl mx-auto">
    <div class="terminal-header">
      <span class="text-terminal-pink">dhairya@portfolio:~$</span>
      <span class="text-terminal-light ml-2">ls projects/ -la</span>
    </div>

    <div class="terminal-content p-6">
      <div class="space-y-8">
        <div class="flex items-center justify-between">
          <h2 class="text-2xl font-bold text-terminal-pink">
            Projects Directory
          </h2>
          <span class="text-terminal-light opacity-70 text-sm">
            total {projects.length} projects
          </span>
        </div>

        <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
          {#each projects as project}
            <div class="project-card group">
              <div class="project-header">
                <div class="flex items-center justify-between">
                  <h3 class="text-terminal-pink font-bold text-lg">
                    📁 {project.name}
                  </h3>
                  <span
                    class="text-xs px-2 py-1 rounded border {getStatusColor(
                      project.status
                    )} border-current"
                  >
                    {project.status}
                  </span>
                </div>
              </div>

              <div class="project-content">
                <p class="text-terminal-light text-sm mb-4 leading-relaxed">
                  {project.description}
                </p>

                <div class="mb-4">
                  <h4 class="text-terminal-pink text-sm font-semibold mb-2">
                    Technologies:
                  </h4>
                  <div class="flex flex-wrap gap-2">
                    {#each project.technologies as tech}
                      <span class="tech-tag">
                        {tech}
                      </span>
                    {/each}
                  </div>
                </div>

                <div class="mb-4">
                  <h4 class="text-terminal-pink text-sm font-semibold mb-2">
                    Key Features:
                  </h4>
                  <ul class="space-y-1">
                    {#each project.features as feature}
                      <li class="text-terminal-light text-sm">
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
                    class="project-link"
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
    padding: 12px 16px;
    border-bottom: 1px solid #333;
    border-radius: 8px 8px 0 0;
    font-family: "Fira Code", monospace;
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
    padding: 16px;
    border-bottom: 1px solid rgba(106, 13, 173, 0.3);
  }

  .project-content {
    padding: 16px;
  }

  .tech-tag {
    background: rgba(255, 179, 186, 0.2);
    color: #ffb3ba;
    padding: 4px 8px;
    border-radius: 4px;
    font-size: 0.75rem;
    border: 1px solid rgba(255, 179, 186, 0.3);
  }

  .project-footer {
    margin-top: 16px;
    padding-top: 16px;
    border-top: 1px solid rgba(106, 13, 173, 0.3);
  }

  .project-link {
    color: #e0e0e0;
    text-decoration: none;
    font-size: 0.875rem;
    font-family: "Fira Code", monospace;
    transition: all 0.2s ease;
    display: block;
    padding: 8px;
    background: rgba(0, 0, 0, 0.3);
    border-radius: 4px;
    border: 1px solid transparent;
  }

  .project-link:hover {
    color: #ffb3ba;
    background: rgba(0, 0, 0, 0.5);
    border-color: rgba(255, 179, 186, 0.3);
    transform: translateX(4px);
  }
</style>
