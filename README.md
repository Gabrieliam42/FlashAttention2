# FlashAttention 2 Windows Wheels

Prebuilt Windows wheels for FlashAttention 2, built from upstream `flash-attention`.

All published wheels are stored directly at the repository root.

The wheel build tag encodes the target PyTorch stack and the CUDA toolkit used for the build:

- `torch2p8p0cu128cuda12p8` means PyTorch `2.8.0+cu128`, built with CUDA toolkit `12.8`
- `torch2p9p1cu130cuda13p2` means PyTorch `2.9.1+cu130`, built with CUDA toolkit `13.2`

## Published Wheels

### `flash_attn-2.8.3-1torch2p8p0cu128cuda12p8-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python: `3.12.10`
- PyTorch: `2.8.0+cu128`
- torchvision: `0.23.0+cu128`
- torchaudio: `2.8.0+cu128`
- CUDA toolkit used to build: `12.8`
- Target GPU architecture: Ampere (`sm_80`)
- Size: `56,682,111` bytes
- SHA256: `590f4a177466d17fe6085b2ed00f40f4a8e92d46bc6a41d63ce036727e547e93`

### `flash_attn-2.8.3-1torch2p9p1cu130cuda13p2-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python: `3.12.10`
- PyTorch: `2.9.1+cu130`
- CUDA toolkit used to build: `13.2`
- Size: `57,035,463` bytes
- SHA256: `e602dc8936abd714a2c51baa5f10ff81fb14473f26e9af00fe02d42c99ad2005`

### `flash_attn-2.8.1-1torch2p9p1cu130cuda13p2-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.1`
- Python: `3.12.10`
- PyTorch: `2.9.1+cu130`
- CUDA toolkit used to build: `13.2`
- Size: `28,682,044` bytes
- SHA256: `4507b92e3e9cb24acde3d50fb002ac0ea9b374f94bf6be3f315e7162e0a95fef`

## Install

Install the matching PyTorch stack first.

PyTorch `2.8.0+cu128`, CUDA toolkit `12.8` wheel:

```powershell
python -m pip install torch==2.8.0+cu128 torchvision==0.23.0+cu128 torchaudio==2.8.0+cu128 --index-url https://download.pytorch.org/whl/cu128 --extra-index-url https://pypi.org/simple
python -m pip install .\flash_attn-2.8.3-1torch2p8p0cu128cuda12p8-cp312-cp312-win_amd64.whl
```

PyTorch `2.9.1+cu130`, CUDA toolkit `13.2` wheels:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
python -m pip install .\flash_attn-2.8.3-1torch2p9p1cu130cuda13p2-cp312-cp312-win_amd64.whl
```

## Verification

```python
import flash_attn
import torch

print(flash_attn.__version__)
print(torch.__version__, torch.version.cuda)
```

Expected stack for `flash_attn-2.8.3-1torch2p8p0cu128cuda12p8-cp312-cp312-win_amd64.whl`:

- `flash_attn`: `2.8.3`
- `torch`: `2.8.0+cu128`
- `torch.version.cuda`: `12.8`

## Build Notes

- Upstream source: `https://github.com/Dao-AILab/flash-attention`
- The CUDA 12.8 wheel was built on Windows in `.venv312` against a repo-local CUDA `12.8` toolkit assembled from NVIDIA redistrib archives under `cuda_12_8_redist/toolkit`
- The Windows source build required a `setup.py` patch to add `/Zc:preprocessor` and `-allow-unsupported-compiler`
- The CUDA 12.8 wheel was verified locally on an RTX 3090 with CUDA forward and backward tests
- Avoid validating from the repo root if possible, because the local `triton` directory in the build workspace can shadow Torch's Triton package

## License

FlashAttention is an upstream open-source project. See the upstream repository for license and source details:

- `https://github.com/Dao-AILab/flash-attention`
