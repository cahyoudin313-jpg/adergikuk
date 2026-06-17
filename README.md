# H9 Pearl Miner
More details see https://github.com/h9-dev/pearl-miner/releases

# h9-miner-pearl 使用说明 / User Guide

## 中文

`h9-miner-pearl` 的启动参数是 `--apiKey` 和 `--devices`。

### 获取 APIKey

APIKey 从 H9 PEARL 页面获取：

https://www.h9.com/mypools/pearl

登录后进入 PEARL 页面，复制你的 APIKey，然后在启动命令中通过 `--apiKey` 传入。

### 基本启动

```bash
./h9-miner-pearl --apiKey=你的APIKey
```

也可以写成小写参数名：

```bash
./h9-miner-pearl --apikey=你的APIKey
```

`--apiKey` 和 `--apikey` 都可以使用，效果相同。

### 指定 GPU

`--devices` 用来指定使用哪些 CUDA 显卡。设备编号从 `0` 开始。

只使用第 0 张卡：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0
```

使用第 0、1 张卡：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0,1
```

如果不设置 `--devices`，矿工会默认使用机器上的全部 CUDA 显卡。

### 常用示例

使用全部显卡：

```bash
./h9-miner-pearl --apiKey=你的APIKey
```

只使用 1 张显卡：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0
```

使用多张显卡：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0,1,2,3
```

设置名称：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0,1 --name=worker-001
```

### 参数说明

| 参数 | 说明 | 示例 |
| --- | --- | --- |
| `--apiKey` / `--apikey` | H9 PEARL APIKey | `--apiKey=abc123` |
| `--devices` | 指定 CUDA 显卡编号，多个编号用英文逗号分隔 | `--devices=0,1` |
| `--name` | 设置名称；不设置时默认使用机器名 | `--name=worker-001` |

### 注意事项

- APIKey 需要从 https://www.h9.com/mypools/pearl 获取。
- `--devices` 中的编号必须是当前机器存在的 CUDA 设备编号。
- 多张显卡用英文逗号分隔，不要加空格，例如 `--devices=0,1,2`。
- 如果启动后提示设备编号无效，请先确认机器上实际的 GPU 数量和编号。

## English

The startup arguments for `h9-miner-pearl` are `--apiKey` and `--devices`.

### Get Your APIKey

Get your APIKey from the H9 PEARL page:

https://www.h9.com/mypools/pearl

After logging in, open the PEARL page, copy your APIKey, and pass it to the startup command with `--apiKey`.

### Basic Startup

```bash
./h9-miner-pearl --apiKey=yourAPIKey
```

You can also use the lowercase argument name:

```bash
./h9-miner-pearl --apikey=yourAPIKey
```

Both `--apiKey` and `--apikey` are supported and have the same effect.

### Specify GPUs

Use `--devices` to specify which CUDA GPUs to use. Device IDs start from `0`.

Use only GPU 0:

```bash
./h9-miner-pearl --apiKey=yourAPIKey --devices=0
```

Use GPU 0 and GPU 1:

```bash
./h9-miner-pearl --apiKey=yourAPIKey --devices=0,1
```

If `--devices` is not set, the miner uses all CUDA GPUs on the machine by default.

### Common Examples

Use all GPUs:

```bash
./h9-miner-pearl --apiKey=yourAPIKey
```

Use only one GPU:

```bash
./h9-miner-pearl --apiKey=yourAPIKey --devices=0
```

Use multiple GPUs:

```bash
./h9-miner-pearl --apiKey=yourAPIKey --devices=0,1,2,3
```

Set a worker name:

```bash
./h9-miner-pearl --apiKey=yourAPIKey --devices=0,1 --name=worker-001
```

### Arguments

| Argument | Description | Example |
| --- | --- | --- |
| `--apiKey` / `--apikey` | H9 PEARL APIKey | `--apiKey=abc123` |
| `--devices` | Specifies CUDA GPU device IDs. Separate multiple IDs with commas. | `--devices=0,1` |
| `--name` | Sets the worker name. If omitted, the machine name is used by default. | `--name=worker-001` |

### Notes

- Get your APIKey from https://www.h9.com/mypools/pearl.
- The IDs in `--devices` must match existing CUDA device IDs on the current machine.
- Separate multiple GPUs with commas and do not add spaces, for example `--devices=0,1,2`.
- If startup reports an invalid device ID, first check the actual number and IDs of GPUs on the machine.

