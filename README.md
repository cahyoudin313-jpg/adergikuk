# H9 Pearl Miner
More details see https://github.com/h9-dev/pearl-miner/releases

# h9-miner-pearl 使用说明 / User Guide

## 中文

`h9-miner-pearl` 是 PEARL 的 CUDA 矿工程序。最常用的启动参数是 `--apiKey` 和 `--devices`。

### 获取 APIKey

APIKey 从 H9 PEARL 矿池页面获取：

https://www.h9.com/mypools/pearl

登录后进入 PEARL 矿池页面，复制你的 APIKey，然后在启动命令中通过 `--apiKey` 传入。

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

设置矿工名称：

```bash
./h9-miner-pearl --apiKey=你的APIKey --devices=0,1 --name=worker-001
```

### 参数说明

| 参数 | 说明 | 示例 |
| --- | --- | --- |
| `--apiKey` / `--apikey` | H9 PEARL 矿池 APIKey | `--apiKey=abc123` |
| `--devices` | 指定 CUDA 显卡编号，多个编号用英文逗号分隔 | `--devices=0,1` |
| `--name` | 设置矿工名称；不设置时默认使用机器名 | `--name=worker-001` |

### 注意事项

- APIKey 需要从 https://www.h9.com/mypools/pearl 获取。
- `--devices` 中的编号必须是当前机器存在的 CUDA 设备编号。
- 多张显卡用英文逗号分隔，不要加空格，例如 `--devices=0,1,2`。
- 如果启动后提示设备编号无效，请先确认机器上实际的 GPU 数量和编号。

## English

`h9-miner-pearl` is the CUDA miner for PEARL. The two most important startup options are `--apiKey` and `--devices`.

### Get Your APIKey

Get your APIKey from the H9 PEARL pool page:

https://www.h9.com/mypools/pearl

Sign in, open the PEARL pool page, copy your APIKey, and pass it to the miner with `--apiKey`.

### Basic Start

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY
```

The lowercase option name also works:

```bash
./h9-miner-pearl --apikey=YOUR_API_KEY
```

`--apiKey` and `--apikey` are equivalent.

### Select GPUs

Use `--devices` to select CUDA GPUs. Device IDs start from `0`.

Use GPU 0 only:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY --devices=0
```

Use GPU 0 and GPU 1:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY --devices=0,1
```

If `--devices` is not set, the miner uses all available CUDA GPUs by default.

### Common Examples

Use all GPUs:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY
```

Use one GPU:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY --devices=0
```

Use multiple GPUs:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY --devices=0,1,2,3
```

Set a miner name:

```bash
./h9-miner-pearl --apiKey=YOUR_API_KEY --devices=0,1 --name=worker-001
```

### Options

| Option | Description | Example |
| --- | --- | --- |
| `--apiKey` / `--apikey` | H9 PEARL pool APIKey | `--apiKey=abc123` |
| `--devices` | CUDA GPU device IDs, separated by commas | `--devices=0,1` |
| `--name` | Miner name; defaults to the machine hostname when unset | `--name=worker-001` |

### Notes

- Get your APIKey from https://www.h9.com/mypools/pearl.
- Values passed to `--devices` must match CUDA device IDs available on the current machine.
- Separate multiple GPU IDs with commas and no spaces, for example `--devices=0,1,2`.
- If the miner reports an invalid device ID, check the actual GPU count and device IDs on the machine.
