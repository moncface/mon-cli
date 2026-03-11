# mon-cli

> Developer tools in your terminal. CLI companion for [Mon [tab]](https://github.com/moncface/mon-tab).
>
> by [moncface](https://github.com/moncface)

## Install

```bash
npm install -g mon-tab
```

## Update

```bash
npm update -g mon-tab
```

## Usage

```bash
mon uuid              # 550e8400-e29b-41d4-a716-...
mon pw                # Xk#9mP2@vL5q!...
mon b64 hello         # aGVsbG8=
mon sha hello         # 2cf24dba5fb0a30e...
mon calc 1920/1080    # 1920/1080 = 1.777777778
mon --version         # 0.3.2
mon ?                 # list all commands
echo "b64 hello" | mon  # aGVsbG8= (stdin pipe)
```

Type `mon ?` to see all available commands.

## .lndf Distillation (CLI only)

```bash
mon ld    # generate project snapshot from git + package.json
mon lv    # view current .lndf
mon lc    # generate + copy to clipboard
```

Generates a minimal project state file (`.lndf/current.lndf`) designed for LLM context injection. See [LNDF](https://github.com/moncface/lndf) for the philosophy.

## Architecture

`mon-cli` imports shared commands from the [`mon-tab`](https://www.npmjs.com/package/mon-tab) npm package. Chrome-only commands (like `rem`) are not available in CLI.

## License

MIT
