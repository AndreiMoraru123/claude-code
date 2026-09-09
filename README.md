# cc

Claude Code config for driving a local DeepSeek V4 Flash via [DwarfStar](../ds4).

Copy `settings.local.json` into a repo's `.claude/` directory.

## Running the server

```sh
./ds4-server --ctx 100000 --kv-disk-dir /tmp/ds4-kv --kv-disk-space-mb 8192 \
  -m ./ds4flash.gguf --vision gguf/DeepSeek-V4-Flash-Vision-Encoder.gguf
```

## Notes

`CLAUDE_CODE_MAX_OUTPUT_TOKENS` is set because Claude Code defaults to 32000 for
models it doesn't recognize, and sends that as `max_tokens`. Hitting it produces:

    API Error: Claude's response exceeded the 32000 output token maximum.

The value is reserved out of the context window, so keep it well under `--ctx`.
