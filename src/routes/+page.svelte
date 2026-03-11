<svelte:head>
  <title>NullClaw Ecosystem Docs</title>
</svelte:head>

<section class="hero">
  <div class="hero-inner">
    <p class="kicker">NULLCLAW ECOSYSTEM</p>
    <h1>Documentation Hub For Autonomous AI Infrastructure</h1>
    <p class="summary">
      Documentation for the `nullclaw` agent runtime and its corresponding
      `nullclaw-chat-ui` web client. Note: for orchestrated pipelines and task
      tracking, please refer to the
      <a href="https://nullhub.io">NullHub Ecosystem</a>.
    </p>

    <div class="hero-actions">
      <a href="/nullclaw/docs/getting-started" class="btn primary"
        >NullClaw Quick Start</a
      >
      <a href="/chat-ui/docs/quick-start" class="btn secondary"
        >Chat UI Quick Start</a
      >
      <a href="https://nullhub.io" class="btn secondary">NullHub Ecosystem</a>
    </div>

    <div class="hero-metrics">
      <article>
        <h3>19</h3>
        <p>top-level CLI commands</p>
      </article>
      <article>
        <h3>0</h3>
        <p>external database dependencies</p>
      </article>
      <article>
        <h3>Terminal + Web</h3>
        <p>dual operator surface</p>
      </article>
    </div>
  </div>
</section>

<section class="projects">
  <div class="section-title">Projects</div>
  <div class="project-grid">
    <article class="project active">
      <div class="top">
        <span class="tag">ACTIVE</span>
        <span class="name">Core Runtime</span>
      </div>
      <h3>NullClaw</h3>
      <p>
        Fastest, smallest, and fully autonomous AI assistant infrastructure
        written in Zig.
      </p>
      <ul>
        <li>Providers, channels, tools, memory, policy</li>
        <li>Terminal and gateway operation modes</li>
        <li>Execution runtime for worker agents</li>
      </ul>
      <div class="actions">
        <a href="/nullclaw/docs/getting-started">Docs</a>
        <a href="https://github.com/nullclaw/nullclaw" target="_blank">GitHub</a
        >
      </div>
    </article>

    <article class="project active">
      <div class="top">
        <span class="tag">ACTIVE</span>
        <span class="name">Web Client</span>
      </div>
      <h3>NullClaw Chat UI</h3>
      <p>
        Svelte terminal-style client for WebChannel v1 pairing, streaming, tool
        timeline rendering, and approvals.
      </p>
      <ul>
        <li>Browser-first operator surface for nullclaw runtime</li>
        <li>Protocol-typed state machine and reconnect behavior</li>
        <li>Session persistence and theming controls</li>
      </ul>
      <div class="actions">
        <a href="/chat-ui/docs/quick-start">Docs</a>
        <a href="https://github.com/nullclaw/nullclaw-chat-ui" target="_blank"
          >GitHub</a
        >
      </div>
    </article>

    <article class="project roadmap">
      <div class="top">
        <span class="tag">IN DEVELOPMENT</span>
        <span class="name">Roadmap</span>
      </div>
      <h3>Orchestrator (Next Layer)</h3>
      <p>
        Higher-level orchestration and ecosystem glue is still in active product
        development.
      </p>
      <ul>
        <li>Cross-system policy and scheduling views</li>
        <li>Global observability and tenancy controls</li>
        <li>Long-term ecosystem control surface</li>
      </ul>
      <div class="actions">
        <a href="/orchestrator">Roadmap Page</a>
      </div>
    </article>
  </div>
</section>

<section class="boundaries">
  <div class="section-title">Product Boundaries</div>
  <div class="table-wrap">
    <table>
      <thead>
        <tr>
          <th>Product</th>
          <th>Primary Responsibility</th>
          <th>What It Owns</th>
          <th>What It Does Not Own</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>NullClaw</td>
          <td>Agent runtime and execution</td>
          <td>Provider calls, tool execution, memory, channels, gateway</td>
          <td>Cross-task queueing and stage lifecycle history</td>
        </tr>
      </tbody>
    </table>
  </div>
</section>

<section class="scenarios">
  <div class="section-title">When To Use What</div>
  <div class="scenario-grid">
    <article>
      <h3>Only NullClaw</h3>
      <p class="lead">
        Best for single-assistant flows with no queue orchestration.
      </p>
      <p>
        <strong>Use when:</strong> one engineer or one bot session handles tasks
        end-to-end, and you need fast local execution with tools/providers.
      </p>
      <p>
        <strong>Real software example:</strong> a maintainer asks the assistant to
        refactor a module, run tests, and open a PR summary in one interactive session.
      </p>
    </article>
  </div>
</section>

<section class="quickstart">
  <div class="section-title">Quick Start</div>
  <div class="panel">
    <pre><code
        ># The easiest way to get started is with NullHub!
# This single binary will download, install, and wire up the rest of the ecosystem.
# See https://nullhub.io for more.

# -------------------------------------------------------------
# Or, if you want to run NullClaw manually from source:

git clone https://github.com/nullclaw/nullclaw.git
cd nullclaw
zig build -Doptimize=ReleaseSmall
./zig-out/bin/nullclaw onboard --provider openrouter --api-key &lt;API_KEY&gt;
./zig-out/bin/nullclaw agent -m "hello from nullclaw"</code
      ></pre>
  </div>
</section>

<style>
  .hero,
  .projects,
  .boundaries,
  .scenarios,
  .quickstart {
    width: min(1180px, 100% - 48px);
    margin: 0 auto;
  }

  .hero {
    padding: 72px 0 52px;
  }

  .hero-inner {
    border: 1px solid var(--border);
    background: radial-gradient(
        circle at 85% 0%,
        color-mix(in srgb, var(--accent) 24%, transparent),
        transparent 40%
      ),
      var(--bg-surface);
    padding: 34px;
    border-radius: 12px;
  }

  .kicker {
    color: var(--accent-dim);
    font-size: 0.8rem;
    letter-spacing: 0.2em;
    margin-bottom: 14px;
  }

  h1 {
    margin: 0;
    font-size: clamp(1.8rem, 4vw, 3rem);
    line-height: 1.1;
    max-width: 18ch;
    text-wrap: balance;
  }

  .summary {
    color: var(--fg-dim);
    max-width: 76ch;
    margin: 16px 0 0;
    line-height: 1.7;
  }

  .hero-actions {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
    margin: 24px 0 26px;
  }

  .btn {
    text-decoration: none;
    padding: 10px 16px;
    border-radius: 8px;
    border: 1px solid var(--border);
    font-weight: 700;
    font-size: 0.85rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  .btn.primary {
    background: color-mix(in srgb, var(--accent) 18%, transparent);
    color: var(--fg);
  }

  .btn.secondary {
    color: var(--accent);
  }

  .btn:hover {
    border-color: var(--accent);
    box-shadow: 0 0 12px var(--border-glow);
  }

  .hero-metrics {
    display: grid;
    gap: 12px;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  }

  .hero-metrics article {
    border: 1px dashed var(--border);
    border-radius: 10px;
    padding: 14px;
    background: color-mix(in srgb, var(--bg) 70%, transparent);
  }

  .hero-metrics h3 {
    margin: 0;
    font-size: 1.5rem;
    color: var(--accent);
  }

  .hero-metrics p {
    margin: 8px 0 0;
    color: var(--fg-dim);
    font-size: 0.85rem;
    line-height: 1.4;
  }

  .section-title {
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 0.14em;
    color: var(--accent-dim);
    margin-bottom: 16px;
  }

  .projects {
    margin-top: 28px;
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
  }

  .project {
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 18px;
    background: var(--bg-surface);
    display: grid;
    gap: 10px;
  }

  .project.active {
    background: linear-gradient(
        160deg,
        color-mix(in srgb, var(--accent) 7%, transparent),
        transparent 45%
      ),
      var(--bg-surface);
  }

  .project.roadmap {
    opacity: 0.93;
  }

  .top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 8px;
  }

  .tag {
    font-size: 0.7rem;
    padding: 4px 8px;
    border: 1px solid var(--border);
    border-radius: 999px;
    letter-spacing: 0.08em;
  }

  .name {
    color: var(--fg-dim);
    font-size: 0.8rem;
    text-transform: uppercase;
  }

  .project h3 {
    margin: 0;
    font-size: 1.35rem;
  }

  .project p {
    margin: 0;
    color: var(--fg-dim);
    line-height: 1.6;
  }

  .project ul {
    margin: 0;
    padding-left: 18px;
    color: var(--fg-dim);
    display: grid;
    gap: 6px;
  }

  .actions {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .actions a {
    color: var(--accent);
    text-decoration: none;
    border-bottom: 1px dashed var(--accent-dim);
    font-size: 0.9rem;
  }

  .actions a:hover {
    border-bottom-style: solid;
  }

  .quickstart {
    margin: 30px auto 56px;
  }

  .panel {
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: auto;
    background: #000;
  }

  pre {
    margin: 0;
    padding: 18px;
    font-size: 0.88rem;
    line-height: 1.5;
  }

  @media (max-width: 1100px) {
    .project-grid,
    .scenario-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 700px) {
    .hero,
    .projects,
    .boundaries,
    .scenarios,
    .quickstart {
      width: min(1180px, 100% - 26px);
    }

    .hero {
      padding: 30px 0 40px;
    }

    .hero-inner {
      padding: 24px 18px;
    }

    h1 {
      font-size: 1.6rem;
    }

    .hero-actions {
      justify-content: stretch;
    }

    .hero-actions .btn {
      width: 100%;
      text-align: center;
    }

    .hero-metrics {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }
</style>
