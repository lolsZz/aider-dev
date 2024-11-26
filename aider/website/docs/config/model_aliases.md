---
parent: Configuration
nav_order: 1000
description: Using a .env file to store LLM API keys for aider.
---

# Model Aliases

Model aliases allow you to create shorthand names for models you frequently use. This is particularly useful for models with long names or when you want to standardize model usage across your team.

## Command Line Usage

You can define aliases when launching aider using the `--alias` option:

```bash
aider --alias "fast:gpt-3.5-turbo" --alias "smart:gpt-4"
```

Multiple aliases can be defined by using the `--alias` option multiple times. Each alias definition should be in the format `alias:model-name`.

## Configuration File

You can also define aliases in your `.aider.conf.yml` file:

```yaml
alias:
  - "fast:gpt-3.5-turbo"
  - "smart:gpt-4"
  - "code:claude-3-sonnet-20240229"
```

## Using Aliases

Once defined, you can use the alias instead of the full model name:

```bash
aider --model fast  # Uses gpt-3.5-turbo
aider --model smart  # Uses gpt-4
```

## Built-in Aliases

Aider includes some built-in aliases for convenience:

- `4`: gpt-4-0613
- `4o`: gpt-4o-2024-08-06
- `4-turbo`: gpt-4-1106-preview
- `35turbo` or `35-turbo`: gpt-3.5-turbo
- `3`: gpt-3.5-turbo
- `sonnet`: claude-3-sonnet-20241022
- `haiku`: claude-3-haiku-20241022
- `opus`: claude-3-opus-20240229
- `deepseek`: deepseek/deepseek-coder

## Priority

If the same alias is defined in multiple places, the priority is:

1. Command line aliases (highest priority)
2. Configuration file aliases
3. Built-in aliases (lowest priority)

This allows you to override built-in aliases with your own preferences.