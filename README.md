# cc

Claude Code config for driving a local DeepSeek V4 Flash via [DwarfStar](../ds4).

Copy `settings.local.json` into a repo's `.claude/` directory.

## Running the server

```sh
./ds4-server --ctx 100000
             --kv-disk-dir /tmp/ds4-kv
             --kv-disk-space-mb 8192
             -m ./ds4flash.gguf
             --vision gguf/DeepSeek-V4-Flash-Vision-Encoder.gguf
```
