# FlashAttention 2.8.1 Windows Wheel

Prebuilt Windows wheel for FlashAttention 2, built from upstream `flash-attention` `v2.8.1`.

## Wheel

- File: `flash_attn-2.8.1-cp312-cp312-win_amd64.whl`
- Package: `flash_attn==2.8.1`
- Python tag: `cp312`
- Platform tag: `win_amd64`
- Size: `28,682,044` bytes
- SHA256: `4507b92e3e9cb24acde3d50fb002ac0ea9b374f94bf6be3f315e7162e0a95fef`

## Intended Stack

- Windows 64-bit
- Python `3.12`
- PyTorch `2.9.1+cu130`
- CUDA runtime/toolkit family: `13.x`
- Target GPU architecture: Ampere (`sm_80`)

## Install

Install the matching PyTorch stack first:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
```

Then install the wheel:

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

- `flash_attn`: `2.8.1`
- `torch`: `2.9.1+cu130`
- `torch.version.cuda`: `13.0`

## Build Notes

- Upstream source: `https://github.com/Dao-AILab/flash-attention`
- Upstream ref: `v2.8.1`
- Built on Windows with MSVC and CUDA `13.2`
- Verified locally with a CUDA runtime test on an RTX 3090
- The build required a Windows-specific `setup.py` patch to add `/Zc:preprocessor` for CUDA `13.x`

## License

FlashAttention is an upstream open-source project. See the upstream repository for license and source details:

- `https://github.com/Dao-AILab/flash-attention`
