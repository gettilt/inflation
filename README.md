<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Inflation
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Inflation will persist globally as governments solve any problem by printing money. Commodities, land, real estate, and companies with monopolistic positions enabling pricing power stand to benefit.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ADM | Archer-Daniels-Midland Company benefits from higher agricultural commodity prices, which are driven by inflation. | chat_gpt,claude |
| BHP | BHP Group is a major player in mining and commodities, which tend to rise in value with inflation. | chat_gpt,claude |
| CVX | Chevron Corporation benefits from rising oil prices, which are often correlated with inflation. | chat_gpt |
| DE | Deere & Company benefits from rising agricultural commodity prices, which are influenced by inflation. | chat_gpt,claude |
| FCX | Freeport-McMoRan Inc. is a major copper producer, and copper prices typically rise with inflation. | chat_gpt |
| FNV | Franco-Nevada Corporation is a gold-focused royalty and streaming company, benefiting from rising gold prices. | chat_gpt,google |
| KO | Coca-Cola has strong brand power and pricing ability, allowing it to pass on higher costs to consumers. | chat_gpt,google |
| MO | Altria Group has a monopolistic position in the tobacco industry, enabling it to maintain pricing power. | chat_gpt |
| NEM | Newmont Corporation is a leading gold mining company, benefiting directly from higher gold prices. | chat_gpt,claude,google |
| NTR | Nutrien Ltd. is a major player in agricultural inputs, benefiting from higher commodity prices. | chat_gpt,google |
| PSA | Public Storage is a REIT that benefits from rising real estate values and increased demand for storage. | chat_gpt,claude,google |
| RGLD | Royal Gold, Inc. acquires and manages precious metal royalties, benefiting from rising gold prices. | chat_gpt |
| SPG | Simon Property Group is a leading real estate investment trust (REIT) that benefits from rising property values. | chat_gpt |
| TGT | Target has strong pricing power and can pass on higher costs to consumers, maintaining profitability. | chat_gpt,google |
| WMT | Walmart has significant pricing power and can pass on higher costs to consumers, maintaining its margins. | chat_gpt,google |
| XOM | ExxonMobil benefits from rising oil prices, which often accompany inflation. | chat_gpt,claude |
| AAPL | Apple's strong brand loyalty and premium positioning give it pricing power to raise prices and maintain margins in an inflationary environment. | claude |
| AMT | As a real estate investment trust (REIT) that owns and operates cell towers, American Tower's property holdings and long-term lease agreements provide a hedge against inflation. | claude |
| AMZN | Amazon's e-commerce dominance and its ability to quickly pass on higher costs to consumers can help it weather inflation. | claude,google |
| GOOGL | Google's search and advertising dominance give it pricing power to increase ad rates in line with inflation. | claude,google |
| LMT | As a major defense contractor, Lockheed Martin could benefit from rising government military spending in an inflationary environment. | claude |
| MSFT | As a technology leader with a strong competitive position, Microsoft has pricing power for its software and cloud services, which can help it navigate an inflationary environment. | claude,google |
| NEE | As a regulated utility with a focus on renewable energy, NextEra has pricing power to raise rates with inflation and its long-term contracts provide stable cash flows. | claude |
| PG | As a consumer staples giant, P&G has pricing power to raise prices on its essential household goods in an inflationary environment, helping to maintain its profitability. | claude,google |
| PLD | Prologis is a REIT that owns and operates logistics facilities like warehouses. Its real estate holdings can provide a hedge against inflation, and it can raise rents in an inflationary environment. | claude,google |
| V | As a payment network, Visa earns a percentage of transaction volumes, which could grow in dollar terms if inflation drives up prices, benefiting its fee income. | claude,google |
| WM | As a waste collection and disposal company, Waste Management provides an essential service and has pricing power to raise fees in line with inflation. | claude |
| AZN |  | google |
| BRK.B |  | google |
| CHD |  | google |
| COR |  | google |
| MA |  | google |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/inflation/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/inflation" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
