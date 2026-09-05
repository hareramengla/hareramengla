## Hareram Engla

**Solutions Engineer — London.** I build the systems I support, not just the tickets that come with them.

Fourteen years keeping enterprise ad and trading platforms running — currently Senior Support & Solutions Engineer at FreeWheel (Comcast), before that Goldman Sachs and Infosys. The repos below are what I build after hours, when a problem is interesting enough to chase.

Open to **Solutions Engineering**, **Technical Account Management**, and AI-forward technical roles.

---

### What's here

**[agent-eval-harness](https://github.com/hareramengla/agent-eval-harness)** — A test harness for conversational LLM agents.

Prompt changes are untestable by inspection: you tighten one instruction, the agent gets better at the case you were looking at and quietly worse at four you weren't. Asserting on reply text doesn't help either, because there are twenty reasonable ways to say the same thing. So this asserts on what the agent *did* — which tool it called, with what arguments, whether that call actually succeeded, and what state it left behind. Every failure carries a *mode*, and the report ranks by mode, because thirty failures for one reason is a single fix.

The check I'd point at first fails an agent that uses confident language with no successful tool call behind it. An agent that fails and says so is a poor experience; an agent that fails and says it worked is an incident.

`Python` · `Gemini API` · `OpenAI API` · `agent evaluation` · runs offline, no API key needed

---

**[api-rca-toolkit](https://github.com/hareramengla/api-rca-toolkit)** — API log diagnostics with ranked root-cause hypotheses.

Any monitoring tool can tell you the error rate spiked. During an incident that's rarely the hard part — the hard part is that five detectors fired and four of them are the same problem seen from different angles. This parses the logs, runs seven independent detectors, then correlates the findings into ranked explanations that separate causes from consequences, mark the consequences as symptoms, and end in a concrete next check.

I found two real bugs in it by running it against its own sample incident and asking why an obvious signal wasn't reported. Both failed *silently* — a baseline contaminated by the incident it was measuring, and a split that moved with traffic volume. Both are fixed, both have regression tests, and both are written up in the README, because that's the more useful half of the story.

`Python` · `log analysis` · `incident response` · `root cause analysis` · zero runtime dependencies

---

**[algo-trading-systems](https://github.com/hareramengla/algo-trading-systems)** — Two automated trading systems: Indian index options via Zerodha Kite Connect, and forex/metals via MetaTrader 5.

Architecture is public, the trading edge is not. What's shared is the design — risk-first position sizing where lot size is *derived* from the stop rather than configured, a single decision function that live trading and backtesting both call so they can't drift apart, and kill switches that sit outside the strategy and can't be overridden by a signal.

No performance figures, deliberately. Backtest numbers on a strategy you designed yourself are easy to overstate, and I'd rather discuss the methodology than defend a headline.

`Python` · `Kite Connect` · `MetaTrader 5` · `risk management`

---

### Elsewhere

Portfolio → **[hareramengla.github.io](https://hareramengla.github.io)**
LinkedIn → **[hareram-engla-se](https://linkedin.com/in/hareram-engla-se)**
