# FlashAttention 2 Wheels

Prebuilt FlashAttention 2 wheels built from upstream `flash-attention`.

All published wheels are stored directly at the repository root.

## Featured Wheel

### `flash_attn-2.8.3-cp313-cp313-linux_x86_64.whl`

- Package version: `flash_attn==2.8.3`
- Platform tag: `cp313-cp313-linux_x86_64`
- Build environment: Linux / WSL, Python `3.13.12`
- Torch stack provenance: `torch==2.10.0+cu130`, `triton==3.6.0`, `xformers==0.0.35`, `deepspeed==0.18.8`, `torchao==0.16.0+cu130`
- CUDA toolkit provenance: `13.0`
- Target GPU architecture: Ampere (`sm_80`)
- CUDA runtime intent: main FlashAttention 2 CUDA extension included for standard attention kernels
- Optional extras not bundled: `fused_dense_lib`, `dropout_layer_norm`, `flash_attn_cuda` blocksparse extension
- Size: `59,964,425` bytes
- SHA256: `0EABE58102DF8F033E46B970C9E47F419DE5E8CA0CFA55D5EA7DACF119F46984`

## Install

Use a matching Linux Python 3.13 environment with the `cu130` PyTorch stack.

```bash
python -m pip install torch==2.10.0+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
python -m pip install ./flash_attn-2.8.3-cp313-cp313-linux_x86_64.whl
```

## Verification

```python
import flash_attn
import torch

print(flash_attn.__version__)
print(torch.__version__, torch.version.cuda)
print(torch.cuda.get_device_name(0))
```

Expected baseline:

- `flash_attn`: `2.8.3`
- `torch`: `2.10.0+cu130`
- `torch.version.cuda`: `13.0`

## Notes

- This wheel was built from upstream `flash-attention` `v2.8.3`.
- It was built with `FLASH_ATTN_CUDA_ARCHS=80`, so it is Ampere-focused rather than a multi-architecture build.
- The compiled CUDA extension is included in the wheel as `flash_attn_2_cuda`.
- The wheel build was completed successfully. Runtime verification was not published in this repo at build time.

## Other Published Wheels

Other Windows wheels remain available at repo root:

- `flash_attn-2.8.3-torch2.8.0cu128cuda12.8-cp312-cp312-win_amd64.whl`
- `flash_attn-2.8.3-torch2.9.1cu128cuda12.8-cp312-cp312-win_amd64.whl`
- `flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl`
- `flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp313-cp313-win_amd64.whl`
- `flash_attn-2.8.1-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl`

## License

FlashAttention is an upstream open-source project. Source and license:

- `https://github.com/Dao-AILab/flash-attention`
