# FlashAttention 2 Windows Wheels

Prebuilt Windows wheels for FlashAttention 2, built from upstream `flash-attention` for the same target stack.

## Target Stack

- Windows 64-bit
- Python `3.12`
- PyTorch `2.9.1+cu130`
- CUDA runtime/toolkit family: `13.x`
- Target GPU architecture: Ampere (`sm_80`)

## Available Wheels

### `flash_attn-2.8.1-cp312-cp312-win_amd64.whl`

- Package: `flash_attn==2.8.1`
- Upstream ref: `v2.8.1`
- Size: `28,682,044` bytes
- SHA256: `4507b92e3e9cb24acde3d50fb002ac0ea9b374f94bf6be3f315e7162e0a95fef`

### `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`

- Package: `flash_attn==2.8.3`
- Upstream ref: `v2.8.3`
- Size: `57,035,463` bytes
- SHA256: `e602dc8936abd714a2c51baa5f10ff81fb14473f26e9af00fe02d42c99ad2005`

## Install

Install the matching PyTorch stack first:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
```

Then install one of the wheels:

```powershell
python -m pip install flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

or:

```powershell
python -m pip install flash_attn-2.8.1-cp312-cp312-win_amd64.whl
```

## Verification

```python
import flash_attn
import torch

print(flash_attn.__version__)
print(torch.__version__, torch.version.cuda)
```

Expected stack:

- `flash_attn`: `2.8.1` or `2.8.3`
- `torch`: `2.9.1+cu130`
- `torch.version.cuda`: `13.0`

## Build Notes

- Upstream source: `https://github.com/Dao-AILab/flash-attention`
- Both wheels were built on Windows with MSVC and CUDA `13.2`
- Both were verified locally with a CUDA runtime test on an RTX 3090
- The Windows build required a `setup.py` patch to add `/Zc:preprocessor` for CUDA `13.x`

## License

FlashAttention is an upstream open-source project. See the upstream repository for license and source details:

- `https://github.com/Dao-AILab/flash-attention`
