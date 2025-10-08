# nodejs-actions-starter-template

![Coverage](./badges/coverage.svg)

👋 Starter template with the action layout, linting, CI, and publishing pre-configured

A complete GitHub Action starter template that includes:

- ✅ Action boilerplate with inputs/outputs
- ✅ ESLint configuration for code quality
- ✅ Jest testing framework with sample tests
- ✅ GitHub Actions CI/CD workflow
- ✅ Automated bundling with ncc
- ✅ Example implementation that works out of the box
- ✅ GitHub REST API integration with Octokit
- ✅ Repository statistics fetching example

## Example Usage

```yml
- name: Hello World Action
  uses: your-username/your-action-name@v1
  with:
    who-to-greet: 'World'
    include-time: true
    message-prefix: 'Hello'
    github-token: ${{ secrets.GITHUB_TOKEN }} # Optional: for repo stats
```

## Action Inputs

| Input            | Description                                      | Required | Default   |
| ---------------- | ------------------------------------------------ | -------- | --------- |
| `who-to-greet`   | Who to greet in the message                      | No       | `'World'` |
| `include-time`   | Whether to include current time in output        | No       | `false`   |
| `message-prefix` | Prefix for the greeting message                  | No       | `'Hello'` |
| `github-token`   | GitHub token for API access (enables repo stats) | No       | -         |

## Action Outputs

| Output       | Description                                    |
| ------------ | ---------------------------------------------- |
| `message`    | The generated greeting                         |
| `time`       | Current timestamp (if requested)               |
| `repo-stats` | Repository statistics JSON (if token provided) |

## Development

This template includes everything you need to start developing GitHub Actions:

### Getting Started

1. Clone this repository
2. Install dependencies: `npm install`
3. Make your changes to `src/index.js`
4. Run tests: `npm test`
5. Build the action: `npm run package`

### Available Scripts

- `npm test` - Run Jest tests
- `npm run lint` - Run ESLint
- `npm run format:write` - Format code with Prettier
- `npm run package` - Bundle the action with ncc
- `npm run all` - Run format, lint, test, coverage, and package

### Testing Locally

You can test the action locally by setting environment variables:

```bash
export INPUT_WHO_TO_GREET="Local Dev"
export INPUT_INCLUDE_TIME="true"
export INPUT_MESSAGE_PREFIX="Hey"
node src/index.js
```

### Project Structure

```text
├── src/
│   └── index.js          # Main action code
├── __tests__/
│   └── index.test.js     # Jest tests
├── dist/                 # Bundled action (generated)
├── action.yml           # Action metadata
├── package.json         # Dependencies and scripts
└── README.md           # This file
```
