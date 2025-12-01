Comandos de configuração do MCP (execute na raiz do repositório):

Sentry
codex mcp add sentry --url https://mcp.sentry.dev/mcp
codex mcp login sentry

Supabase
codex mcp add supabase --url https://mcp.supabase.com/mcp
codex mcp login supabase

Context7
codex mcp add context7 -- npx -y @upstash/context7-mcp --api-key=<SUA_CONTEXT7_API_KEY>

Substitua `<SUA_CONTEXT7_API_KEY>` por uma chave válida e mantenha-a em sigilo.

C:\Users\SEU_USUARIO\.codex\config.toml
No config.toml adicione:

[mcp_servers.github]
type = "http"
url = "https://api.githubcopilot.com/mcp/"
bearer_token_env_var = "CODEX_GITHUB_PERSONAL_ACCESS_TOKEN"
