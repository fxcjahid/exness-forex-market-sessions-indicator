# Forex Market Sessions

An indicator written in [Indie](https://takeprofit.com/docs/indie/What-is-Indie) for TakeProfit charts. It draws a box around each trading session (Sydney, Tokyo, London, New York) so you can see at a glance which session is running and how far price moved in it.

> This is a charting aid, not trading advice. It does not generate buy or sell signals.

## Features

- A dotted box for each session, from the session's first candle to its latest candle and from its lowest low to its highest high. Overlapping sessions blend together.
- The session name above the box, in the session's color, with the session range (pips, points or price).
- Previous session high and low lines that keep extending to the right until price touches them.
- Session hours follow each city's own timezone, so daylight saving changes are handled automatically.
- Settings for colors, fill opacity, border style, width and opacity, padding, and name position and height.
- An optional "Now" panel in the top-right corner showing which sessions are running.

## Default sessions

Hours are local to each city.

| Session  | Hours       | Timezone            |
|----------|-------------|---------------------|
| Sydney   | 07:00-16:00 | Australia/Sydney    |
| Tokyo    | 09:00-18:00 | Asia/Tokyo          |
| London   | 08:00-17:00 | Europe/London       |
| New York | 08:00-17:00 | America/New_York    |

Brokers and traders define sessions differently. To change the hours, edit the four `make_schedule(...)` lines in `Main.__init__`.

## Installation

1. Open a chart on TakeProfit and add the **Indicators Code Editor** widget.
2. Copy the full contents of `forex_market_sessions.indie5` and paste it into the editor.
3. Click **Add to Chart**.

## Settings

| Setting | Default | What it does |
|---|---|---|
| Show Sydney / Tokyo / London / New York session | On | Turns each session on or off |
| Sydney / Tokyo / London / New York color | Purple / Yellow / Blue / Orange | Color of the box, border and name |
| Box fill opacity | 0.08 | Strength of the fill inside the box |
| Border style | 3 | 1 = solid, 2 = dashed, 3 = dotted |
| Border width | 1 | Line thickness (1 to 5) |
| Border opacity | 0.8 | Strength of the border color |
| Box padding (% of session range) | 4 | Space between the highs/lows and the box |
| Show session name above box | On | Shows or hides the name |
| Session name position | 2 | 1 = left, 2 = center, 3 = right |
| Session name height above box | 12 | Raises the name, as a % of the session range |
| Show session range in the name | On | Adds the range, for example `London \| 85.3 pips` |
| Range unit | 1 | 1 = pips, 2 = points, 3 = price |
| Show previous session high/low lines | On | Draws the extending high and low lines |
| Show "Now" panel | Off | Lists the sessions running right now |
| Label font size | 10 | Size of the labels |

## Limitations

- Intraday timeframes only. On daily or higher timeframes the indicator shows an error.
- It does not skip weekends. On forex there are no candles then, but on 24/7 markets such as crypto the boxes also appear on weekends.
- Pips are calculated as 10 ticks on instruments with 2, 3 or 5 price decimals. For other instruments use the points or price unit.
- Rounded borders and real label padding are not available in Indie labels.

## Credits

The `make_schedule()` helper is adapted from the "3 Trading Sessions" indicator by @dr_jones (MIT License), which was ported from TradingView's built-in Trading Sessions: <https://indie-script.github.io/indicators/3%20Trading%20Sessions/>

## License

MIT. See [LICENSE](LICENSE). Replace `[Your Name]` in the license and in the code header with your own name before publishing.
