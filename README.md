# BankrollSZN for Claude

BankrollSZN puts DFS and sports research data into Claude. Ask a question in plain words. Claude gets the answer from BankrollSZN tools and shows a BankrollSZN card in the chat.

Sports: NBA, NFL, NHL, MLB, WNBA, PGA, UFC and League of Legends.

## What you get

- **Connector.** The BankrollSZN MCP server at `https://mcp.bankrollszn.com/app`. It has projections, ownership by contest type, DraftKings lineup optimizers, player props against BankrollSZN projections, odds comparison, line movement, Monte Carlo sim picks with a graded record, injuries, Elo ratings, matchups and BankrollSZN Targets.
- **Skills.**
  - `dfs-lineup-builder`: builds DraftKings lineups from the optimizer, with every number from a tool call.
  - `slate-research`: gives a short research brief for one slate or one game.
  - `prop-research`: compares the market prop line to the BankrollSZN projection for a player or a team.

## Set up

1. Add the BankrollSZN plugin in Claude (Customize > Plugins).
2. Open the plugin's Connectors tab and select Connect.
3. Sign in with your BankrollSZN account. There is no API key.

A free BankrollSZN account works. The free plan has a daily call limit. The Fan plan has a higher limit. See https://bankrollszn.com/ai for the current limits.

## Example prompts

- "Build me 3 DraftKings NBA GPP lineups for tonight's main slate."
- "Give me a research brief for the NFL Sunday main slate."
- "Which NBA player props have the biggest gap between the line and the BankrollSZN projection?"
- "Backtest isolation-heavy guards against Orlando this season."

## Data and privacy

The connector reads BankrollSZN data. It does not place bets, move money or connect to a sportsbook account. It can save and delete BankrollSZN Targets on your account only when you ask. Privacy policy: https://bankrollszn.com/privacy. Terms: https://bankrollszn.com/terms.

## Support

Email support@bankrollszn.com or see https://bankrollszn.com/ai.

## Responsible play

BankrollSZN is research and entertainment, not financial advice. DFS and sports betting are for adults of legal age in permitted places only. If you or someone you know has a gambling problem, call 1-800-GAMBLER.
