
## [v1.0.0-alpha.37] - 2026-03-07

### Added
- **Tiered LLM Routing:** Modified `internal/llm/waterfall.go` to inject `classifyComplexity`. The router now automatically diverts simple URL processing tasks (Reddit, Twitter, YCombinator) away from expensive frontier models (Priority > 10) to cheaper, local Small Language Models (SLMs). This addresses the massive 10x cost variance problem outlined in the Model Intelligence section of the roadmap.
- **Fit Markdown Scraper Filter:** Modified `internal/sync/linkcrawler.go` `extractVisibleText` to aggressively strip out `<nav>`, `<header>`, `<footer>`, and `<aside>` HTML tags before converting text. This removes substantial HTML boilerplate, enabling token optimizations mapped to the "Progressive Context Optimization" architectural goal.
