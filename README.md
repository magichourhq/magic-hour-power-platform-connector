# Magic Hour

Magic Hour brings AI image and video generation to Microsoft Power Automate and Azure Logic Apps. Create images from prompts, create videos from prompts or source images, then retrieve project status and signed output URLs.

## Publisher

[Magic Hour](https://magichour.ai)

## Prerequisites

- A Magic Hour account
- A Magic Hour API key from [API keys](https://magichour.ai/settings/api-keys)
- Enough Magic Hour credits for generation actions

## Supported operations

- **Get account** — Verify the connection and return tier and credit balance.
- **Create image** — Start an AI image generation project.
- **Create video** — Start a text-to-video project.
- **Animate image** — Start an image-to-video project from a Magic Hour file path or public image URL.
- **Get image project** — Return image project status and output URLs.
- **Get video project** — Return video project status and output URLs.

Generation actions are asynchronous. Save the returned project ID, wait or use a recurrence trigger, then call the matching project action until `status` is `complete`, `error`, or `canceled`.

## Obtaining credentials

1. Sign in to [Magic Hour](https://magichour.ai).
2. Open [API keys](https://magichour.ai/settings/api-keys).
3. Create or copy an API key.
4. Enter the raw key when Power Platform creates the Magic Hour connection. The connector adds the required `Bearer` prefix.

## Known limitations

- Generation consumes Magic Hour credits when the create action succeeds.
- Output URLs are signed and expire at the returned `expires_at` time.
- **Animate image** accepts a stable public image URL or the `file_path` returned by Magic Hour's upload URL API. This first connector version does not upload a Power Platform file automatically.
- Supported model, duration, resolution, and aspect-ratio combinations vary. See the [Magic Hour API documentation](https://docs.magichour.ai/api-reference).

## Local installation

The `MagicHour` directory contains `apiDefinition.swagger.json`, `apiProperties.json`, `icon.png`, and `readme.md`. Import them with the [Power Platform custom connector CLI](https://learn.microsoft.com/connectors/custom-connectors/paconn-cli) or import the Swagger file in Power Automate or Logic Apps.

Marketplace certification and publication are separate Microsoft processes. This repository does not submit or publish the connector.
