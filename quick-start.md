# Quickstart

This doc shows you how to get this running in a few simple steps

## Prereqs
```
git
docker
openai API key (or you can use deepseek, grok, gemini, etc)
financial dataset API Key
```

## Setup
1. `git clone git@github.com:ehan1990/ai-hedge-fund.git; cd ai-hedge-fund`

2. `docker run -it --name aihedgefund -v "$PWD:/app" -w /app python:3 bash`

3. Run the following cmds in your container
```
apt update
curl -sSL https://install.python-poetry.org | python3 -
cp /root/.local/bin/poetry /usr/local/bin
poetry install
cp .env.example .env
```

4. Replace `your-openai-api-key` in `.env` with your OpenAI API key (https://platform.openai.com)

5. Replace `your-financial-datasets-api-key` in `.env` with your API key (https://financialdatasets.ai)

6. `poetry run python src/main.py --ticker GOOG`

```
? Select your AI analysts. done (3 selections)

Selected analysts: Cathie Wood, Michael Burry, Warren Buffett

? Select your LLM model: [openai] gpt-4o

Selected OpenAI model: gpt-4o

 ✓ Cathie Wood         [GOOGL] Done
 ✓ Michael Burry       [GOOGL] Done
 ✓ Warren Buffett      [GOOGL] Done
 ✓ Risk Management     [GOOGL] Done
 ✓ Portfolio Management[GOOGL] Done

Analysis for GOOGL
==================================================

AGENT ANALYSIS: [GOOGL]
+----------------+----------+--------------+--------------------------------------------------------------+
| Agent          |  Signal  |   Confidence | Reasoning                                                    |
+================+==========+==============+==============================================================+
| Cathie Wood    | NEUTRAL  |        60.0% | Alphabet Inc. (GOOGL) commands a substantial lead in the     |
|                |          |              | digital ecosystem with its suite of platforms that are       |
|                |          |              | integral to modern technological infrastructure, such as     |
|                |          |              | Google Search, YouTube, and cloud computing services. The    |
|                |          |              | company’s noteworthy R&D investment at 15.1% of revenue      |
|                |          |              | underscores its commitment to innovation, essential for      |
|                |          |              | maintaining its competitive edge and fostering new           |
|                |          |              | technology developments. High operating margins (26.4%) and  |
|                |          |              | a focus on reinvestment rather than dividends emphasize its  |
|                |          |              | strategic approach to sustain growth and innovation.         |
|                |          |              | However, despite these positive indicators, GOOGL’s market   |
|                |          |              | capitalization exceeds its intrinsic value by approximately  |
|                |          |              | 18%, signaling a premium that could limit immediate upside   |
|                |          |              | potential. Given these factors, while GOOGL remains a robust |
|                |          |              | player with substantial long-term prospects, the current     |
|                |          |              | valuation leads to a cautious approach, thus maintaining a   |
|                |          |              | neutral stance in anticipation of further innovations that   |
|                |          |              | might enhance its transformational impact in the digital     |
|                |          |              | realm.                                                       |
+----------------+----------+--------------+--------------------------------------------------------------+
| Warren Buffett | BULLISH  |        88.0% | I'm particularly impressed with Google's robust financial    |
|                |          |              | strength and strong economic moat. The company boasts a      |
|                |          |              | remarkable ROE of 32.5%, well above the industry average,    |
|                |          |              | indicating that it has a sustainable competitive advantage.  |
|                |          |              | This reminds me a bit of our investment in Apple, where we   |
|                |          |              | also recognized a strong brand and technological ecosystem.  |
|                |          |              | Google's conservative debt level with a debt-to-equity ratio |
|                |          |              | of only 0.385 ensures financial stability, akin to the       |
|                |          |              | financial fortitude we value in our holdings. Furthermore,   |
|                |          |              | the substantial margin of safety of about 33% gives a        |
|                |          |              | comfortable cushion, well aligning with my principle of      |
|                |          |              | buying at a significant discount to intrinsic value to       |
|                |          |              | ensure a margin of safety greater than 30%. The management   |
|                |          |              | team has shown a shareholder-friendly approach through their |
|                |          |              | share repurchase programs, displaying alignment with our     |
|                |          |              | preference for quality management. Additionally, Google's    |
|                |          |              | operating margin of 34.3% and a sustainable earnings growth  |
|                |          |              | pattern, despite some inconsistencies, reflect long-term     |
|                |          |              | operational excellence. While the revenue growth might       |
|                |          |              | appear moderate at around 3%, the consistent returns on      |
|                |          |              | invested capital and healthy margins outweigh these          |
|                |          |              | concerns. Altogether, these elements combine to form a       |
|                |          |              | compelling case for investment reminiscent of other          |
|                |          |              | successful ventures we've engaged in. Certainly, any         |
|                |          |              | concerns about the P/E ratio are mitigated by these          |
|                |          |              | longer-term prospects, making Google a solid candidate for   |
|                |          |              | continued investment.                                        |
+----------------+----------+--------------+--------------------------------------------------------------+
| Michael Burry  | NEUTRAL  |        33.3% | Low FCF yield 3.8%. Balance sheet strong: D/E 0.39, net cash |
|                |          |              | position. Negative insider activity: selling. Contrarian     |
|                |          |              | indicator: 101 negative headlines. Valuation not compelling  |
|                |          |              | enough for a strong move. Hold.                              |
+----------------+----------+--------------+--------------------------------------------------------------+

TRADING DECISION: [GOOGL]
+------------+----------------------------------------------------------+
| Action     | BUY                                                      |
+------------+----------------------------------------------------------+
| Quantity   | 132                                                      |
+------------+----------------------------------------------------------+
| Confidence | 88.0%                                                    |
+------------+----------------------------------------------------------+
| Reasoning  | The 'warren_buffett_agent' signals a strong bullish      |
|            | sentiment with high confidence of 88.0%, suggesting      |
|            | potential for upside. We have sufficient cash to buy the |
|            | maximum allowed 132 shares, and the confidence is high   |
|            | enough to justify a full position based on the bullish   |
|            | outlook.                                                 |
+------------+----------------------------------------------------------+

PORTFOLIO SUMMARY:
+----------+----------+------------+--------------+
| Ticker   |  Action  |   Quantity |   Confidence |
+==========+==========+============+==============+
| GOOGL    |   BUY    |        132 |        88.0% |
+----------+----------+------------+--------------+

Portfolio Strategy:
The 'warren_buffett_agent' signals a strong bullish
sentiment with high confidence of 88.0%, suggesting
potential for upside. We have sufficient cash to buy the
maximum allowed 132 shares, and the confidence is high
enough to justify a full position based on the bullish
outlook.
```
