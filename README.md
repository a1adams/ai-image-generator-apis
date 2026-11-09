# AI Image Generator API: 7 Providers Ranked for Developers (2026)

This list ranks 7 AI image generator API providers by how much of an image job one request covers, how the result comes back and what a failed request costs, using vendor docs checked in October 2026. Wireflow is first because one request runs a saved multi-step workflow and a signed webhook returns the result. Of the 7, 5 document a completion webhook.

1. **Wireflow**: Best overall for multi-step image jobs from one call, a node canvas whose saved workflows run by REST API
2. **Runware**: Best for many image tasks in one request, a task API where every request is an array
3. **Black Forest Labs API**: Best for calling FLUX models directly, an asynchronous API that returns a polling URL
4. **WaveSpeedAI**: Best for 1,000+ models behind one API key, a usage-priced API with a price endpoint
5. **Together AI**: Best for open models and FLUX on one prepaid API, an inference platform with an images endpoint
6. **DeepInfra**: Best for pay-per-use open image models, an inference cloud with webhooks on its native API
7. **Stability AI**: Best for Stability's own image models, a developer platform with synchronous generation endpoints

The Wireflow team maintains this list, so read entry 1 with that in mind. [Wireflow's node-based image generation page](https://www.wireflow.ai/node-based-image-generation) shows the canvas that entry 1 describes, and every other entry links to its vendor's own docs so that each cell can be checked.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-11-09** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections are welcome, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [Comparison table](#comparison-table)
- [The tools](#the-tools)
  - [Wireflow](#1-wireflow)
  - [Runware](#2-runware)
  - [Black Forest Labs API](#3-black-forest-labs-api)
  - [WaveSpeedAI](#4-wavespeedai)
  - [Together AI](#5-together-ai)
  - [DeepInfra](#6-deepinfra)
  - [Stability AI](#7-stability-ai)
- [What each check means](#what-each-check-means)
- [How this list is maintained](#how-this-list-is-maintained)
- [FAQ](#faq)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Model support | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|---|
| **[Wireflow](#1-wireflow)** | Custom connector, OAuth sign-in | Yes | [check](https://www.wireflow.ai/pricing) | 100+ image, video and audio models as nodes | [pricing](https://www.wireflow.ai/pricing) | n/a |
| **[Runware](#2-runware)** | Hosted MCP, OAuth 2.1 | Yes | [check](https://runware.ai/pricing) | Image, video, audio, LLM and 3D models | [pricing](https://runware.ai/pricing) | [runware/runware-python](https://github.com/runware/runware-python), 3 ★, pushed 2026-11-05 |
| **[Black Forest Labs API](#3-black-forest-labs-api)** | FLUX MCP server, OAuth | Yes | [check](https://docs.bfl.ai/quick_start/pricing) | FLUX image and video models | [pricing](https://docs.bfl.ai/quick_start/pricing) | n/a |
| **[WaveSpeedAI](#4-wavespeedai)** | MCP server via npx | Yes | [check](https://wavespeed.ai/docs/how-pricing-works) | 1000+ image, video, audio, 3D and LLM models | [pricing](https://wavespeed.ai/docs/how-pricing-works) | [WaveSpeedAI/mcp-server](https://github.com/WaveSpeedAI/mcp-server), 36 ★, pushed 2026-11-09 |
| **[Together AI](#5-together-ai)** | n/a | Yes | [check](https://www.together.ai/pricing) | Open models and FLUX image models | [pricing](https://www.together.ai/pricing) | n/a |
| **[DeepInfra](#6-deepinfra)** | n/a | Yes | [check](https://deepinfra.com/pricing) | Text, image, video, speech and embedding models | [pricing](https://deepinfra.com/pricing) | n/a |
| **[Stability AI](#7-stability-ai)** | n/a | Yes | [check](https://platform.stability.ai/pricing) | Stable Image Ultra, Core and SD3 | [pricing](https://platform.stability.ai/pricing) | n/a |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts the documented capabilities a tool has, out of the checks listed in [`data/tools.json`](data/tools.json) under `capabilityChecks`. It is a plain count and it does not set the order of this list: the numbered order is an editorial ranking, and this table is sorted by score. The checks and every answer are in the file, so each cell can be checked. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | Async job with polling | Completion webhook | Many images in one request | Cost shown before a run | MCP server | Official SDK | Failed runs not charged | Score |
|------|---|---|---|---|---|---|---|-------|
| **[Runware](#2-runware)** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | **7/7** |
| **[Wireflow](#1-wireflow)** | ✅ | ✅ | ✅ | n/a | ✅ | ❌ | ✅ | **5/7** |
| **[WaveSpeedAI](#4-wavespeedai)** | n/a | ✅ | n/a | ✅ | ✅ | n/a | ✅ | **4/7** |
| **[Black Forest Labs API](#3-black-forest-labs-api)** | ✅ | ✅ | n/a | n/a | ✅ | n/a | n/a | **3/7** |
| **[DeepInfra](#6-deepinfra)** | ✅ | ✅ | ❌ | n/a | n/a | n/a | n/a | **2/7** |
| **[Stability AI](#7-stability-ai)** | ❌ | n/a | n/a | ✅ | n/a | n/a | ✅ | **2/7** |
| **[Together AI](#5-together-ai)** | n/a | n/a | n/a | n/a | n/a | n/a | n/a | **0/7** |
<!-- CAPABILITY-SCORES:END -->

## Comparison table

| Tool | Best for | Price basis | How a job reports back | Results kept |
|---|---|---|---|---|
| **Wireflow** | Multi-step image jobs from one call | Credits per image or megapixel | Polling or a signed webhook | Not published |
| **Runware** | Many image tasks per request | Per request, shown per model | Polling or a webhook per task | 7 days by default |
| **Black Forest Labs API** | FLUX models called directly | Credits, from $0.014 an image | Polling URL, webhook on some | 10 minutes |
| **WaveSpeedAI** | 1,000+ models on one key | Per request, quoted before a run | Webhook, or sync mode | Not published |
| **Together AI** | Open models and FLUX on one API | Per image, from $0.0154 | Image URL in the response | Not published |
| **DeepInfra** | Pay-per-use open image models | Per image, FLUX-2-pro $0.015 | Webhook on the native API | Not published |
| **Stability AI** | Stability's own image models | Credits per successful result | Image in the response | 24 hours for async upscales |

From each vendor's own docs and pricing pages, checked 2026-10-11. Prices change, so follow the pricing links in the data table.

## The tools

### 1. Wireflow

*Best overall for multi-step image jobs from one call*

![Wireflow screenshot](https://assets.wireflow.ai/competitors/wireflow-70f47ccd9660.png?v=r5)

- **What it is:** [Wireflow](https://www.wireflow.ai/) is a hosted platform where ad teams and AI agents build and rerun creative on a shared node board. Each model is a node on one canvas and the output of one node feeds the next, so an LLM prompt step, an image model, an edit and a layout can run as one saved workflow behind one API call.
- **Best for:** Developers whose finished image needs more than one model call, for example a prompt written by an LLM, a generated image and an on-brand layout, and who want one request to run the chain.
- **Pricing basis:** It charges credits per generation, according to the model you run, and 1 credit is US$0.01. The public catalog prices image models per image or per megapixel, for example Imagen 4 at 10 credits an image, Nano Banana 2 at 20, GPT Image 2 at 44 and Flux Schnell at 1 credit a megapixel. See the [Wireflow pricing page](https://www.wireflow.ai/pricing), checked October 2026.
- **Standout:** If the balance is short, an API run returns a 402 with the required credits, the available credits and a per-node breakdown instead of starting. Credits are taken only when a model finishes, a failed model is not charged, and the execution reports `creditsUsed`. Source: [the executions reference](https://www.wireflow.ai/docs/api/executions).
- **Limit:** The API starts one run per request, so there is no bulk submit endpoint that takes a file of items. There is no official SDK. An endpoint that returns the total cost of a whole workflow before a run, when the balance is enough, is not documented, and a retention period for outputs is not published. Running generations needs a paid plan.
- **API or automation:** `GET /api/v1/workflows/{id}/run` returns a saved workflow's input schema, and `POST` to the same path starts it and returns 202 with an execution ID. An `Idempotency-Key` on that POST replays the original run instead of starting a new one, and a webhook block makes Wireflow POST the result when the run finishes, as [the run endpoint reference](https://www.wireflow.ai/docs/api/run) explains.
- **Sources:** the Wireflow pricing page, model catalog, run reference, executions reference and webhooks reference, checked 2026-10-11.
- **Links:**
  - [Wireflow node based image generation page](https://www.wireflow.ai/node-based-image-generation)
  - [Docs](https://www.wireflow.ai/docs/api/overview)

Pick Wireflow when the image your app needs is the end of a chain, not one model call, and you want the chain, the retry rule and the callback in one place. More on [chaining several AI models in one API call](https://www.wireflow.ai/features/chain-ai-models-api) is on the Wireflow site. The completion webhook is signed with HMAC-SHA256 and retried for up to 12 attempts. If each image is one model call, entries 2 and 3 are simpler to call.

Run a saved workflow from code: send its input values to this endpoint with an API key, then poll the execution or add a webhook block. The request format is in the API reference linked under Docs.
```text
POST /api/v1/workflows/{id}/run
```
Or add the Wireflow connector to Claude Code, from the wireflowINC/skills README. Then run /mcp to sign in.
```bash
claude mcp add --transport http wireflow https://www.wireflow.ai/api/mcp
```

### 2. Runware

*Best for many image tasks in one request*

![Runware screenshot](https://assets.wireflow.ai/competitors/runware-1dad906299e3.png?v=r5)

- **What it is:** [Runware](https://runware.ai/) is an AI infrastructure platform with pay-as-you-go APIs for image, video, audio, LLM and 3D models.
- **Best for:** Developers generating images in bulk through an API.
- **Pricing basis:** Per request, in USD, with no subscription and no minimum spend, and the balance never expires. Most models charge a rate per unit, so the price is known before you send the request, for example FLUX 3 Image at $0.041 an image. You are charged only for successful requests. See the [Runware pricing page](https://runware.ai/pricing), checked October 2026.
- **Standout:** Every Models API request is an array of tasks, each processed independently, so one call can batch many images. Errors are scoped to the task that failed and the rest may still succeed. Source: [the Runware Models API introduction](https://runware.ai/docs/models-api/introduction).
- **Limit:** When a model's queue is over capacity, new tasks are rejected with a 429 and a Retry-After header, and a 504 means a request waited past the maximum queue time. Output URLs are kept for 7 days by default unless you set a `ttl`.
- **API or automation:** Set `webhookURL` and Runware POSTs the complete task response for each completed item. Failed deliveries are retried with exponential backoff from 250ms up to 8 seconds, and a webhook can arrive more than once, so you track the task UUIDs you have processed, as [the Runware webhook docs](https://runware.ai/docs/models-api/webhooks) say.
- **Note:** The linked repository is the official Python SDK. A TypeScript SDK is documented as well.
- **Sources:** [Runware's pricing docs](https://runware.ai/docs/models-api/pricing) and [rate limits page](https://runware.ai/docs/models-api/rate-limits), checked 2026-10-11.
- **Links:**
  - [runware/runware-python](https://github.com/runware/runware-python)

Pick Runware over Wireflow when each image is one model call and you want hundreds of them in one request with a price you can compute in advance. It also publishes TypeScript and Python SDKs and a hosted MCP server.

Send one image task, from the Runware Models API introduction. The request body is an array, so more task objects can go in the same call.
```bash
curl https://api.runware.ai/v1 \
  -H "Authorization: Bearer $RUNWARE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '[
    {
      "taskType": "imageInference",
      "taskUUID": "a770f077-f413-47de-9dac-be0b26a35da6",
      "model": "xai:grok-imagine@image-quality",
      "positivePrompt": "A golden retriever on a park bench, cinematic lighting",
      "width": 1024,
      "height": 1024
    }
  ]'
```

### 3. Black Forest Labs API

*Best for calling FLUX models directly*

![Black Forest Labs API screenshot](https://assets.wireflow.ai/competitors/black-forest-labs-api-2e3fbb330599.png?v=r5)

- **What it is:** The [Black Forest Labs API](https://docs.bfl.ai/quick_start/introduction) generates and edits images and video with the FLUX model family, including FLUX 3 and FLUX.2.
- **Best for:** Developers who want FLUX models called directly from code.
- **Pricing basis:** Credits, where 1 credit is $0.01. FLUX.2 [klein] 4B starts at $0.014 an image and FLUX 3 Image 1k is $0.048, and batch requests multiply the base cost by the number of images. See the [Black Forest Labs pricing page](https://docs.bfl.ai/quick_start/pricing), checked October 2026.
- **Standout:** The same models are also released as open weights, FLUX.2 [klein] and [dev] and FLUX.1 [dev], so you can move to self-hosting later. The primary endpoint routes requests across clusters with automatic failover, with EU and US regional endpoints.
- **Limit:** Generated images expire after 10 minutes and the delivery URLs have no CORS support, so you download each image and serve it from your own storage. Most endpoints allow at most 24 concurrent requests, and a 402 comes back when credits run out.
- **API or automation:** A request returns an `id` and a `polling_url` that you poll until the status is Ready. The FLUX.2 [pro] endpoint accepts a `webhook_url` and an optional `webhook_secret`, and the FLUX 3 image endpoint lists a polling URL and no webhook field, as [the integration guidelines](https://docs.bfl.ai/api_integration/integration_guidelines) describe.
- **Note:** No official SDK repository is named in the docs index, so none is listed in the data table.
- **Sources:** the pricing page and integration guidelines linked above, and [the FLUX MCP integration page](https://docs.bfl.ai/api_integration/mcp_integration), checked 2026-10-11.

Pick the Black Forest Labs API over Runware when you only use FLUX and want the model maker's own endpoint and the option of open weights. Plan for the 10-minute expiry in your storage step.

Submit a request and read the polling URL, from the Black Forest Labs integration guide. The guide then polls that URL until the status is Ready.
```bash
response=$(curl -X 'POST' \
  'https://api.bfl.ai/v1/flux-2-pro-preview' \
  -H 'accept: application/json' \
  -H "x-key: ${BFL_API_KEY}" \
  -H 'Content-Type: application/json' \
  -d '{
    "prompt": "A serene landscape with mountains",
    "width": 1440,
    "height": 810
  }')

request_id=$(echo $response | jq -r .id)
polling_url=$(echo $response | jq -r .polling_url)
```

### 4. WaveSpeedAI

*Best for 1,000+ models behind one API key*

![WaveSpeedAI screenshot](https://assets.wireflow.ai/competitors/wavespeed-2d81973fb165.png?v=r5)

- **What it is:** [WaveSpeedAI](https://wavespeed.ai/) is a platform with 1000+ image, video, audio, 3D and LLM models behind a single API key.
- **Best for:** Developers who want one API across many generative models.
- **Pricing basis:** Usage-based and set per model, with no subscription: you top up credits, which never expire and are non-refundable. For example nano-banana-2.1 text to image is listed at $0.04, shown discounted to $0.036. See the [WaveSpeedAI pricing guide](https://wavespeed.ai/docs/how-pricing-works), checked October 2026.
- **Standout:** A price endpoint, `POST /api/v3/model/price`, returns the price for a model and a set of inputs, and a submission whose price cannot be calculated is rejected before a task is created or charged.
- **Limit:** Chaining models means separate requests, polling each step before you start the next one. A sync-mode request that times out on the client side is not automatically refundable if the task continues or completes.
- **API or automation:** Add a `webhook` query parameter and WaveSpeedAI POSTs to your HTTPS endpoint when a task completes or fails, with up to 3 retries, and sync mode cannot be combined with a webhook, as [the WaveSpeedAI webhook guide](https://wavespeed.ai/docs/how-to-use-webhooks) explains.
- **Note:** The linked repository is the official MCP server. Its get_price tool quotes a price before a run.
- **Sources:** [the WaveSpeedAI refund policy](https://wavespeed.ai/docs/refund-policy) and [the WaveSpeedAI MCP server repo](https://github.com/WaveSpeedAI/mcp-server), checked 2026-10-11.

Pick WaveSpeedAI over the Black Forest Labs API when you want to switch between many model families on one key and check the price in code before each run. Failed requests and system timeouts are eligible for automatic credit reversal under its refund policy.

Add the WaveSpeedAI MCP server to Claude Code, from the WaveSpeedAI/mcp-server README. It runs with npx and your API key.
```bash
claude mcp add wavespeed -- npx -y @wavespeed/mcp
```

### 5. Together AI

*Best for open models and FLUX on one prepaid API*

![Together AI screenshot](https://assets.wireflow.ai/competitors/together-ai-b10eac5a548d.png?v=r5)

- **What it is:** [Together AI](https://www.together.ai/) provides serverless inference, dedicated inference, GPU clusters and fine-tuning for open models.
- **Best for:** Developers running open models and FLUX image models through one API.
- **Pricing basis:** Per image for image models, for example FLUX.2 [dev] at $0.0154 an image and FLUX.2 [pro] at $0.03. Listed image prices assume the lowest resolution and the default steps. Together is fully prepaid, with a minimum $15 first credit purchase. See the [Together AI pricing page](https://www.together.ai/pricing), checked October 2026.
- **Standout:** The image API is one POST to `/v1/images/generations` that names a model, and the response returns the image URL. A Batch API runs many requests from one JSONL file at up to 50% off serverless rates, documented for chat completions and audio endpoints. Source: [Together's images overview](https://docs.together.ai/docs/images-overview).
- **Limit:** The billing docs say there are no free trials. API keys do not support their own spending limits, and API access is suspended when the balance reaches zero until you add credits.
- **API or automation:** A billing usage API (`GET /v1/billing/usage`) returns cost-annotated line items, which can lag up to 1 hour during its beta. Chaining models in one request and a completion webhook are not described in the images or batch docs, as [Together's batch inference docs](https://docs.together.ai/docs/batch-inference) show.
- **Note:** Fully prepaid, with a minimum $15 first credit purchase; the billing docs say there are no free trials (checked 2026-10-11).
- **Sources:** [Together's billing docs](https://docs.together.ai/docs/billing-credits) and [spend controls page](https://docs.together.ai/docs/billing-spend-controls), checked 2026-10-11.

Pick Together AI over WaveSpeedAI when you already run open language models on Together and want FLUX on the same prepaid balance. Check its billing docs before you rely on spend controls.

The image endpoint, from Together's images overview: one POST that names a model, such as FLUX.2 dev, and returns the image URL.
```text
POST /v1/images/generations
```

### 6. DeepInfra

*Best for pay-per-use open image models*

![DeepInfra screenshot](https://assets.wireflow.ai/competitors/deepinfra-d9bcb5ba00a2.png?v=r5)

- **What it is:** [DeepInfra](https://deepinfra.com/) is an inference cloud that hosts text, image, video, speech and embedding models behind an API.
- **Best for:** Developers who want pay-per-use access to open models, including FLUX image models.
- **Pricing basis:** Pay as you go with no long-term contracts. FLUX image models are priced per image by formula, for example FLUX-2-pro at $0.015 an image and FLUX-1-schnell at $0.0005 x (width/1024) x (height/1024) x iterations. You can set a spending limit. See the [DeepInfra pricing page](https://deepinfra.com/pricing), checked October 2026.
- **Standout:** Webhooks on the native API: you add a `webhook` parameter, the API answers with status queued, then calls your URL when inference completes, with the status, runtime and cost in the payload. Source: [DeepInfra's webhook docs](https://docs.deepinfra.com/account/webhooks).
- **Limit:** Webhooks are not supported with the OpenAI-compatible API. Image generation endpoints are not yet supported in the Batch API, and you must add a card or pre-pay before the first call.
- **API or automation:** Every account has a default limit of 200 concurrent requests per model, with a 429 above it, as [DeepInfra's rate limits page](https://docs.deepinfra.com/account/rate-limits) states. Each inference call names one model.
- **Note:** Webhooks are a feature of the native API and are not supported with the OpenAI-compatible API (checked 2026-10-11).
- **Sources:** [DeepInfra's Batch API introduction](https://docs.deepinfra.com/batch/introduction), checked 2026-10-11.

Pick DeepInfra over Together AI when you want per-image pricing with no prepaid minimum stated and a webhook that reports the cost of each job. Pick Together AI when its Batch API discount covers your other workloads.

### 7. Stability AI

*Best for Stability's own image models*

![Stability AI screenshot](https://assets.wireflow.ai/competitors/stability-ai-2c0c269d4099.png?v=r5)

- **What it is:** [Stability AI](https://platform.stability.ai/) runs a developer platform with API access to its image generation models.
- **Best for:** Developers who want Stability's models, such as Stable Image Ultra and Core, through an API.
- **Pricing basis:** Credits per successful result, for example a flat 3 credits per Stable Image Core generation and 8 credits per Stable Image Ultra result, and failed generations are not charged. Plan prices are not repeated here. See the [Stability AI pricing page](https://platform.stability.ai/pricing), checked October 2026.
- **Standout:** The REST API reference lists endpoints for generation (Stable Image Ultra, Core and SD3), upscaling, editing (erase, inpaint, outpaint, search and replace, remove background) and control (sketch, structure, style). Source: [Stability AI's API spec](https://api.stability.ai/v2alpha/openapi).
- **Limit:** The API is rate-limited to 150 requests every 10 seconds, and over the limit you receive a 429 and are timed out for 60 seconds. The spec mentions no webhooks and no batch endpoint, so each request is one generation.
- **API or automation:** Generation endpoints answer in the same request with the image itself or base64 in JSON. Creative Upscale is asynchronous: you poll the results endpoint no more than once every 10 seconds, and results are deleted 24 hours after generation.
- **Note:** Generation endpoints answer in the same request; Creative Upscale is asynchronous and its results are deleted after 24 hours.
- **Sources:** the Stability AI platform, pricing page and API spec linked in this entry, checked 2026-10-11.

Pick Stability AI when you need its editing and control endpoints and a synchronous call fits your app. It sits last only because the criterion rewards batching and callbacks.

## What each check means

A check means the vendor's own source documents it. A cross means the source says it works another way. Anything in brackets is not published, or not verified for this list, which is not proof that it is absent.

- **Async job with polling:** A request returns an ID straight away and you poll it, so a slow generation does not hold the connection open.
- **Completion webhook:** The service calls your URL when the image is ready, so a worker does not have to poll.
- **Many images in one request:** One call covers many images, through an array, a batch or a saved workflow.
- **Cost shown before a run:** The price of a request can be known before it runs.
- **MCP server:** A documented Model Context Protocol server, so an agent such as Claude can call the API.
- **Official SDK:** A client library published by the vendor itself.
- **Failed runs not charged:** The docs say a failed generation is not billed or is refunded.

## How this list is maintained

Every cell comes from the vendor's own docs, API reference or pricing page, last checked on 11 October 2026. The numbered order is editorial and uses 4 checks: how much of an image job one request covers, how a finished job reports back, whether the cost of a request can be known before it runs, and what a failed or repeated request costs. Providers that leave the least retry and polling code to you come first. The capability score in the README is a separate plain count of documented checks, and it does not set the order. Nothing here was benchmarked, so no image was generated and no latency was measured.

We left out app-only image generators with no public API and APIs that only host one company's chat models, because this list is about generating images from code. To correct a cell, open an issue or a pull request with the tool, the check and a link to the vendor page that proves it. PRs are welcome, including corrections to entry 1.

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run, so edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## FAQ

<details>
<summary><strong>What is the best AI image generator API?</strong></summary>

It depends on the job. For an image that needs several model steps from one call, Wireflow fits. For many single-model images in one request, Runware fits, and for FLUX from the model maker, the Black Forest Labs API fits. Stability AI suits its own editing and control endpoints.

</details>

<details>
<summary><strong>Is there a free AI image generator API?</strong></summary>

Most providers here are paid per request. Runware lists $2 of free credits for sign-ups with a business email, Together AI's billing docs say it offers no free trials, and DeepInfra needs a card or pre-payment. Wireflow's free plan lets you build workflows, and running generations needs a paid plan.

</details>

<details>
<summary><strong>What is the best text to image API?</strong></summary>

For text to image on one model, Runware, the Black Forest Labs API, WaveSpeedAI, Together AI and DeepInfra each take a prompt and return an image. Wireflow adds steps around the model, such as an LLM that writes the prompt and a layout after it, as [Wireflow's batch generation page](https://www.wireflow.ai/features/batch-ai-generation) shows.

</details>

<details>
<summary><strong>Is there a FLUX API?</strong></summary>

Yes. Black Forest Labs runs its own API for the FLUX family, including FLUX 3 and FLUX.2, and also releases open weights for FLUX.2 [klein] and [dev]. Runware, Together AI, DeepInfra and Wireflow also list FLUX models.

</details>

<details>
<summary><strong>Is there a Stable Diffusion API?</strong></summary>

Yes. Stability AI's developer platform lists SD3 generation endpoints next to Stable Image Ultra and Core, plus upscaling, editing and control endpoints. Requests carry an API key in the Authorization header.

</details>

<details>
<summary><strong>Is there an AI image generation API with no API key required?</strong></summary>

The nearest option is an MCP connector with OAuth sign-in. Wireflow's connector, Runware's hosted MCP server and the FLUX MCP server let an agent sign in with OAuth, so there is no API key to paste. A direct REST call to Wireflow still uses an API key.

</details>

## The short version

Pick Wireflow when the image your app ships is the end of a chain of model calls and you want one request, one retry rule and one signed callback. Pick Runware when you want many single-model images in one request at a price you can compute first, and the Black Forest Labs API when you only use FLUX. Before you commit, send the same 50 prompts to your two finalists and note what a failed task costs in each. To see which image models Wireflow runs, browse [the Wireflow model catalog](https://www.wireflow.ai/models).

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE), public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).
