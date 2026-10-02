# Personal Development Preferences

## System Environment
- OS: macOS
- Shell: fish
- Editor: VS Code

## Code Style
- Look for an `AGENTS.md` with instructions in the current cwd
- If no instructions, adapt to existing project style
- If not in a project
  - Best practices
  - JS/TS: ES modules
  - PHP: 8.4

## Development Workflow
- Never modify working code without explicit permission

## Tools & Commands
- Always check if dependencies are already installed before installing

## Communication Style
- When reporting information to me, be extremely concise and sacrifice grammar for the sake of concision
- Ask for clarification if requirements are ambiguous
- When reviewing code, don't mention nit pick things that are not bugs or real issues

## Do Not Touch
- Don't install anything into the current project without previous discussion
- Global installs / caches / temp dirs are fine for well-known tools (e.g. Playwright browsers)
- Don't change dependency versions without discussion
- Don't refactor working legacy code unless explicitly requested

## Commit message style
- See Communication style. Short and clear
- Keep URLs for reference if there are any (`@see https://...`)
- Do not mention yourself als Co-Author

## nono sandbox: profile changes
- "allow in nono …", "let nono …", "nono should permit …" etc. = draft a profile change, don't work around it
- Follow `~/.config/nono/AGENTS.md`: edit `profiles/claude.json` → draft `profile-drafts/claude.json` + SHA-256 of current file in `profile-drafts/claude.base`, then print promote command

## nono sandbox: browsers / Playwright
- Chromium ignores HTTPS_PROXY; under nono it must use the proxy explicitly, else net::ERR_ACCESS_DENIED:
  ```js
  const px = new URL(process.env.HTTPS_PROXY);
  chromium.launch({ proxy: { server: `${px.protocol}//${px.host}`,
    username: px.username, password: px.password, bypass: process.env.NO_PROXY } });
  ```
- Playwright MCP / CLI: pass same proxy server + credentials
- DDEV sites use ports 8080/8443 (e.g. `https://<project>.ddev.site:8443`)
