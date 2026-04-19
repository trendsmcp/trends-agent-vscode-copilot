# trends-agent-vscode-copilot

Live trend data inside VS Code with GitHub Copilot Agent Mode. Connect
Trends MCP and Copilot can pull search, social, ecommerce, news, and
developer trend data right next to your code.

> Live trend data for AI agents. One connection. Every platform.
> Powered by [trendsmcp.ai](https://trendsmcp.ai)

## Get your free API key

1. Go to [trendsmcp.ai](https://trendsmcp.ai)
2. Enter your email, key sent instantly
3. 100 free requests per month, no credit card

[Get your free key](https://trendsmcp.ai)

## Connect VS Code in 30 seconds

The cleanest path is per workspace via `.vscode/mcp.json`. You can also
add it globally with the Command Palette.

### Per workspace (recommended)

Create `.vscode/mcp.json` at the root of your project, then paste this
inside `servers`:

```json
{
  "servers": {
    "trends-mcp": {
      "type": "http",
      "url": "https://api.trendsmcp.ai/mcp",
      "headers": { "Authorization": "Bearer YOUR_API_KEY" }
    }
  }
}
```

Reload VS Code, then open Copilot Chat in `Agent` mode. The
`trends-mcp` tools will appear in the tool picker.

### Globally via Command Palette

Open the Command Palette (`Ctrl+Shift+P` on Windows / Linux,
`Cmd+Shift+P` on Mac) and run `MCP: Add Server`. Choose HTTP, paste
`https://api.trendsmcp.ai/mcp`, and add the `Authorization` header.

The full setup walkthrough is at
[trendsmcp.ai/docs](https://trendsmcp.ai/docs).

## What you can ask Copilot

Once connected, switch Copilot Chat to `Agent` mode and talk in plain
English. Include the phrase **"using TrendsMCP"** or **"via TrendsMCP"**
so Copilot routes to the MCP instead of doing a web search.

- "Using TrendsMCP, fetch npm weekly downloads for `langchain`, `llamaindex`, and `haystack`, then plot them in a notebook."
- "Via TrendsMCP, get GitHub Trending Repos for today and add the top 10 to a `trending.md` doc."
- "Using TrendsMCP, compare Steam concurrent players for `Elden Ring` and `Baldur's Gate 3`, then write SQL to track this weekly."
- "Via TrendsMCP, fetch news sentiment for `OpenAI` over 90 days and dump the JSON into `tests/fixtures/`."
- "Using TrendsMCP, pull the Google Search trend for our brand over 1 year and refresh the dashboard JSON."

## Three tools your AI gets

- `get_trends`, historical time series for any keyword on any source
  (5 years weekly, 30 days daily where supported).
- `get_growth`, percentage change over any period (7D, 1M, 3M, 6M, 1Y,
  YTD, custom dates).
- `get_top_trends`, what is trending right now across live platform feeds.

## All data sources in one connection

One API key gives Copilot every keyword source and every live feed below.

### Keyword sources (Get Trends and Get Growth)

| source | What it measures | Keyword format |
| --- | --- | --- |
| `google search` | Google search volume | Any keyword or phrase |
| `google images` | Google image search volume | Any keyword or phrase |
| `google news` | Google News search volume | Any keyword or phrase |
| `google shopping` | Google Shopping search volume | Any keyword or phrase |
| `youtube` | YouTube search volume | Any keyword or phrase |
| `tiktok` | TikTok hashtag volume | Hashtag or topic |
| `reddit` | Subreddit subscribers | Subreddit name only, no `r/` prefix |
| `amazon` | Amazon product search volume | Product name or category |
| `wikipedia` | Wikipedia page views | Article title or topic |
| `news volume` | News article mention volume | Any keyword or phrase |
| `news sentiment` | News sentiment score (positive / negative) | Any keyword or phrase |
| `app downloads` | Mobile app download estimates (Android) | Package id or app identifier |
| `npm` | npm package weekly downloads | Exact package name e.g. react |
| `steam` | Steam concurrent players (monthly) | Game display name e.g. Elden Ring |

All values are normalized to a 0 to 100 scale where the pipeline supports
it, so you can compare different sources directly.

### Live leaderboards (Get Top Trends)

Google Trends, Google News Top News, TikTok Trending Hashtags, YouTube
Trending, X (Twitter) Trending, Reddit Hot Posts, Reddit World News,
Wikipedia Trending, Amazon Best Sellers Top Rated, Amazon Best Sellers by
Category, App Store Top Free, App Store Top Paid, Google Play, Top
Websites, Spotify Top Podcasts, Steam Most Played, GitHub Trending Repos,
IMDb MOVIEmeter, Trending Books.

The source list evolves over time. Authoritative reference at
[trendsmcp.ai/docs](https://trendsmcp.ai/docs).

## Use cases inside VS Code

- **Data plus code in one flow.** Pull a real time series and have
  Copilot scaffold the loader, schema, and tests in the same chat.
- **Test fixtures from real data.** Snapshot a real series for
  reproducible test cases.
- **Trend dashboards.** Fetch the data, generate the chart component,
  and wire it into your app.
- **Release notes and changelogs.** Pull GitHub Trending or npm growth
  and have Copilot draft the writeup.
- **AI coding agents.** Use live trend signals as context when
  generating product code, marketing copy, or analytics SQL.

## Pricing

Free forever for 100 requests per month. Paid plans available. See
[trendsmcp.ai/pricing](https://trendsmcp.ai/pricing).

## Resources

- [Get a free API key](https://trendsmcp.ai)
- [Documentation and full reference](https://trendsmcp.ai/docs)
- [Pricing](https://trendsmcp.ai/pricing)
- [All TrendsMCP repositories](https://github.com/trendsmcp)

## Security

Never commit your API key to a public repository. Use environment variables
or your OS secret store. Keys can be rotated at any time from your
TrendsMCP dashboard. The `YOUR_API_KEY` placeholder above is a literal
string to replace with your own key after you copy the snippet locally.

## License

MIT. See [LICENSE](./LICENSE).
