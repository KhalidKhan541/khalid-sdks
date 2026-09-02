# khalid-sdks

> A comprehensive collection of 10 API SDKs by **KhalidKhan541**

## Overview

This repository contains all my SDKs in one place. Each SDK is a standalone wrapper for popular APIs, designed for easy integration in Node.js applications.

## SDKs Included

| SDK | Description | Install |
|-----|-------------|---------|
| `sdk-github` | GitHub API SDK | `npm install khalid-sdk-github` |
| `sdk-stripe` | Stripe payment SDK | `npm install khalid-sdk-stripe` |
| `sdk-twilio` | Twilio SMS SDK | `npm install khalid-sdk-twilio` |
| `sdk-sendgrid` | SendGrid email SDK | `npm install khalid-sdk-sendgrid` |
| `sdk-aws` | AWS SDK wrapper | `npm install khalid-sdk-aws` |
| `sdk-firebase` | Firebase SDK wrapper | `npm install khalid-sdk-firebase` |
| `sdk-slack` | Slack API SDK | `npm install khalid-sdk-slack` |
| `sdk-discord` | Discord API SDK | `npm install khalid-sdk-discord` |
| `sdk-telegram` | Telegram Bot SDK | `npm install khalid-sdk-telegram` |
| `sdk-openai` | OpenAI API SDK | `npm install khalid-sdk-openai` |

## Project Structure

```
sdks/
├── sdk-github/
│   ├── src/
│   │   └── index.js
│   ├── tests/
│   │   └── sdk-github.test.js
│   ├── examples/
│   │   └── basic.js
│   ├── package.json
│   └── README.md
├── sdk-stripe/
│   └── ...
└── ... (10 SDKs total)
```

## Features

- **Async/Await** - Modern Promise-based API
- **Error Handling** - Built-in error handling
- **TypeScript** - Includes type definitions
- **Tested** - Jest with 50%+ coverage thresholds
- **CI/CD** - GitHub Actions workflow included
- **Node.js 16+** - Modern Node.js support

## Quick Start

```bash
# Install any SDK
npm install khalid-sdk-github

# Import and use
import { GitHubSDK } from 'khalid-sdk-github';
const github = new GitHubSDK('your-token');
const repos = await github.getRepos('octocat');
```

## SDK Usage Examples

### GitHub SDK
```javascript
import { GitHubSDK } from 'khalid-sdk-github';
const github = new GitHubSDK('your-token');

// Get user repos
const repos = await github.getRepos('octocat');

// Create a new repo
const repo = await github.createRepo('my-repo', 'My new repo', true);
```

### Stripe SDK
```javascript
import { StripeSDK } from 'khalid-sdk-stripe';
const stripe = new StripeSDK('sk_test_...');

// Create a customer
const customer = await stripe.createCustomer('john@example.com', 'John Doe');

// Create a charge
const charge = await stripe.createCharge(2000, 'usd', customer.id);
```

### Slack SDK
```javascript
import { SlackSDK } from 'khalid-sdk-slack';
const slack = new SlackSDK('xoxb-...');

// Post a message
await slack.postMessage('#general', 'Hello from SDK!');

// Get user info
const user = await slack.getUserInfo('U12345');
```

### Discord SDK
```javascript
import { DiscordSDK } from 'khalid-sdk-discord';
const discord = new DiscordSDK('your-bot-token');

// Send a message
await discord.sendMessage('channel-id', 'Hello from SDK!');

// Get guild info
const guild = await discord.getGuild('guild-id');
```

### OpenAI SDK
```javascript
import { OpenAISDK } from 'khalid-sdk-openai';
const openai = new OpenAISDK('sk-...');

// Create chat completion
const response = await openai.createChatCompletion('gpt-4', [
  { role: 'user', content: 'Hello!' }
]);

// Generate image
const image = await openai.createImage('A beautiful sunset');
```

## Development

```bash
# Clone the repo
git clone https://github.com/KhalidKhan541/khalid-sdks.git
cd khalid-sdks

# Navigate to an SDK
cd sdks/sdk-github

# Install dependencies
npm install

# Run tests
npm test

# Run lint
npm run lint
```

## API Keys

Each SDK requires API keys for the respective service. Store them securely in environment variables:

```bash
export GITHUB_TOKEN=your_token
export STRIPE_SECRET_KEY=your_key
export TWILIO_ACCOUNT_SID=your_sid
export TWILIO_AUTH_TOKEN=your_token
export SENDGRID_API_KEY=your_key
export SLACK_TOKEN=your_token
export DISCORD_TOKEN=your_token
export TELEGRAM_TOKEN=your_token
export OPENAI_API_KEY=your_key
```

## CI/CD

Each SDK includes a GitHub Actions workflow that:
- Runs tests on Node.js 18.x and 20.x
- Runs ESLint
- Publishes to NPM on main branch pushes

## License

MIT License - see individual SDKs for details

## Author

**KhalidKhan541**
- GitHub: [@KhalidKhan541](https://github.com/KhalidKhan541)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Run `npm test` and `npm run lint`
6. Submit a pull request
