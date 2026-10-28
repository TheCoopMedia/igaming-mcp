# THE COOP MCP connector: iGaming news and provider research

Bring [THE COOP’s iGaming news](https://thecoop.media/articles), [provider database](https://thecoop.media/providers) and [industry events](https://thecoop.media/events) into your AI research workflow.

THE COOP is an independent B2B publication covering payments, platforms, technology and the people behind iGaming. Its public **Model Context Protocol (MCP) connector** lets compatible AI assistants search published articles, retrieve source-linked provider profiles and explore event records. Results link back to the original pages so you can inspect the evidence yourself.

**Connector URL:** `https://thecoop.media/mcp`

**Transport:** Streamable HTTP · **Authentication:** none · **Access:** read-only

[Try the connector in your browser](https://thecoop.media/ai#try) · [Set up your assistant](https://thecoop.media/ai#setup) · [Browse iGaming providers](https://thecoop.media/providers)

## What you can research

- **iGaming payment providers:** payment processors, gateways, wallets and local payment methods, with documented capabilities and restrictions.
- **Payment orchestration platforms:** routing, integrations and the product details recorded in provider profiles.
- **Sportsbook software providers:** sportsbook platforms, odds feeds and sports data.
- **iGaming platform providers:** casino software, white-label and turnkey offerings.
- **Crypto payment gateways:** crypto and stablecoin payment services, with evidence labels and documented gaps.
- **iGaming news:** reporting, interviews and analysis across payments, platforms, technology and people.

The [provider directory](https://thecoop.media/providers) distinguishes desk-reviewed records from research candidates. A listing does not establish suitability or mean that an organisation accepts gambling businesses.

## Connect your AI assistant

Add a remote MCP server in a client that supports **Streamable HTTP**:

1. Name the connector `THE COOP`.
2. Enter `https://thecoop.media/mcp` as its URL.
3. Select no authentication, where your client asks.
4. Enable the connector in your conversation and try a prompt below.

No THE COOP account or API key is required. Client features and availability vary; the [setup guide](https://thecoop.media/ai#setup) covers Claude, Claude Code, ChatGPT, Cursor, VS Code and other compatible clients.

### Cursor configuration

Add this entry to your MCP configuration, preserving any existing servers:

```json
{
  "mcpServers": {
    "thecoop": {
      "url": "https://thecoop.media/mcp"
    }
  }
}
```

### Claude Code

```sh
claude mcp add --transport http thecoop https://thecoop.media/mcp
```

You can also [try the public tools on THE COOP’s website](https://thecoop.media/ai#try) before configuring a client.

## Example prompts and research starting points

Use these prompts after enabling the connector. They ask the assistant to retrieve published evidence; the links also let you explore the same subject directly.

### Sportsbook software providers

> Find sportsbook software providers in THE COOP’s database. Open the relevant profiles, distinguish sportsbook platforms from odds and data services, and cite documented capabilities and sources. Identify integration or market details that remain unknown.

Browse [sportsbook software providers and odds services](https://thecoop.media/providers/sportsbook-software). For a specific record, explore [Altenar’s provider profile](https://thecoop.media/providers/altenar).

### Payment orchestration platforms

> Research payment orchestration platforms for an iGaming operator. Open desk-reviewed profiles and compare documented routing, integration and reconciliation capabilities where available. Cite each fact’s evidence status and flag missing information. Do not assume gambling acceptance.

Start with [payment orchestration providers](https://thecoop.media/providers/payment-orchestration), then inspect a full record such as [Akurateco](https://thecoop.media/providers/dir-akurateco).

### Crypto payment gateway research

> Find crypto payment gateway profiles in THE COOP. Separate documented crypto acceptance, fiat conversion and settlement features. Cite sources and evidence labels, and identify unknown fees, supported networks or merchant restrictions. Do not infer gambling eligibility from an integration.

Explore the [crypto payment gateway and stablecoin provider category](https://thecoop.media/providers/crypto-payments).

### iGaming payment providers and high risk payment processing

> Help me research iGaming payment providers and assess a high risk payment processor. Use THE COOP’s profiles to separate documented services from supplier claims. Report any published gambling restrictions, onboarding requirements and gaps, with sources. Do not treat a directory listing as approval for my business.

Browse [iGaming payment providers](https://thecoop.media/providers/payments) and read the [PSP onboarding framework](https://thecoop.media/articles/igaming-psp-onboarding-before-the-sales-call) before a sales conversation.

### iGaming platform providers

> Find iGaming platform providers in THE COOP’s database. Open relevant profiles and compare documented white-label, turnkey and standalone products. Separate platform capabilities from game aggregation and sportsbook services. Link the records and identify pricing, migration or integration details not documented.

Explore [iGaming platform providers](https://thecoop.media/providers/platforms). For a related function, browse [casino game aggregation providers](https://thecoop.media/providers/game-aggregation).

### Payment processing fees

> Search THE COOP’s published coverage for payment processing fees relevant to iGaming operators. Open the articles and explain the cost components they document. Distinguish processing fees, FX, settlement and reserves where covered; identify costs that are not quantified. Cite titles, URLs and dates.

Read [THE COOP’s payments coverage](https://thecoop.media/articles?topic=payments) and inspect the [payment provider database](https://thecoop.media/providers/payments) for organisation-specific evidence.

### iGaming news

> Summarise THE COOP’s latest iGaming news about payments, platforms and technology. Open the relevant articles and give five concise takeaways, each with its title, publication date and canonical link. Preserve any sponsorship disclosure.

Read the [latest iGaming news and analysis](https://thecoop.media/articles), or explore [payments](https://thecoop.media/articles?topic=payments), [platforms](https://thecoop.media/articles?topic=platforms) and [technology](https://thecoop.media/articles?topic=technology).

## How the connector works

1. **Search:** your assistant calls a tool to find relevant published records.
2. **Open:** it retrieves the full article, provider profile or event rather than relying on a search excerpt.
3. **Check:** it inspects available sources, dates, evidence labels and missing information.
4. **Cite:** it links to the canonical URL returned with the record.

The connector exposes nine read-only tools:

- `search` — semantic and keyword search across published articles, provider profiles and events.
- `list_articles` — published articles, with optional topic and format filters.
- `get_article` — a full published article, including available sources, dates and disclosures.
- `search_suppliers` — provider and media profiles filtered by name, category or review status.
- `get_supplier` — a full profile with sourced facts, evidence labels and approved buyer answers or overview where published.
- `list_events` — events filtered by period, region or query.
- `get_event` — an event record, with an optional exhibitor list.
- `list_exhibitors` — paginated exhibitors filtered by event, category or name.
- `about_the_coop` — publication, citation and connector logging information.

The website uses **providers** in its directory. The MCP tool names `search_suppliers` and `get_supplier` retain their existing API names. Follow pagination when requesting a complete list.

The connector retrieves published information. It does not expose drafts, edit records or carry out payments or gambling transactions. The [live guide and tool demo](https://thecoop.media/ai) show the current public surface.

## Read the evidence before making a decision

Search match strength describes text relevance, not factual certainty or product suitability. Open the full record before comparing providers.

- **`supplier-stated`:** the organisation makes the claim; this is not independent verification.
- **`register-matched`:** information was matched to an official register within the recorded scope.
- **`editorially-checked`:** THE COOP’s editors checked the information.
- **`unconfirmed`:** the information remains unconfirmed.
- **`missing`:** THE COOP has not documented the information. Unknown does not mean “no”.

THE COOP’s Egg Score concerns evidence readiness, not product quality. A missing rating is not zero. Preserve source references, dates and sponsorship disclosures when using a record. Read [how THE COOP assesses providers](https://thecoop.media/providers/methodology) and its [editorial standards](https://thecoop.media/editorial-standards).

## Privacy and use of content

Tool arguments and questions, returned-record information, timing and client details are logged to improve coverage and operate the service. The public policy describes a daily rotating IP hash and scheduled deletion of raw connector logs after 180 days; question text can still identify you. Semantic search queries may pass through an external embedding provider. Keep confidential information out of requests and read the [privacy policy](https://thecoop.media/privacy).

Cite the returned record’s title and canonical URL, with `checked_at` where supplied. Provider eligibility depends on the relevant entity, product, jurisdiction and contract. Content use is governed by [THE COOP’s terms](https://thecoop.media/terms).

## About THE COOP

[THE COOP](https://thecoop.media/) combines independent journalism with source-linked provider intelligence for people working in iGaming. Learn [about the publication and team](https://thecoop.media/about), browse [provider comparisons](https://thecoop.media/compare), or explore the [events calendar](https://thecoop.media/events).

For corrections, include the page URL and the fact or source that needs checking using the [contact details on the About page](https://thecoop.media/about).

**Serious business. Questionable poultry.**

Documentation checked: 28 October 2026. This repository documents the hosted connector; it does not contain the server implementation or grant a licence to republish the underlying database.
