# Genkit Extension for Gemini CLI

This package provides a standalone [Gemini CLI](https://geminicli.com/) extension for [Genkit](https://genkit.dev).

This extension provides `gemini-cli` with instructions and tools for interacting with Genkit applications.

## Get started

### Prerequisites
- [Gemini CLI](https://geminicli.com/)
- npx

### Install
```bash
gemini extensions install https://github.com/gemini-cli-extensions/genkit
```

## Usage

Once installed and configured, Gemini CLI will have access to Genkit documentation and Genkit MCP tools to understand, interact and improve your app.

For example, you can create a new flow:

```shell
> Write a flow that tests an input string for profanity.
```

Or build and improve your existing Genkit app:

```shell
> Write an evaluator with a sample dataset for my `profanityCheckerFlow`
```

Or analyze any trace and make changes:

```
> The last invocation of `profanityCheckerFlow` produced a weird result, can you fix it?
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

See [CONTRIBUTING.md](docs/contributing.md) for more information about contributing to this project.

## License

This project is licensed under the Apache 2 License - see the [LICENSE](LICENSE) file for details.
