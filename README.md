# FlashAttention 2 Windows Wheels

Prebuilt Windows wheels for FlashAttention 2, built from upstream `flash-attention`.

## Recommended Build

- Path: `wheelhouse/flash-attn-cuda12.8/flash_attn-2.8.3-cp312-cp312-win_amd64.whl`
- Package: `flash_attn==2.8.3`
- Python: `3.12.10`
- PyTorch: `2.9.1+cu128`
- CUDA toolkit used to build: `12.8`
- Target GPU architecture: Ampere (`sm_80`)
- Size: `56,690,614` bytes
- SHA256: `b94101f7ae37037335bbc51d60030870d6b7ac22282d166e11c84fff4705ceab`

## Legacy Wheels

These older wheels are still present, but they were built for the CUDA 13 / `cu130` stack.

### `flash_attn-2.8.1-cp312-cp312-win_amd64.whl`

- Path: `flash_attn-2.8.1-cp312-cp312-win_amd64.whl`
- Package: `flash_attn==2.8.1`
- Upstream ref: `v2.8.1`
- Size: `28,682,044` bytes
- SHA256: `4507b92e3e9cb24acde3d50fb002ac0ea9b374f94bf6be3f315e7162e0a95fef`
- Build stack: PyTorch `2.9.1+cu130`, CUDA `13.2`

### `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`

- Path: `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`
- Package: `flash_attn==2.8.3`
- Upstream ref: `v2.8.3`
- Size: `57,035,463` bytes
- SHA256: `e602dc8936abd714a2c51baa5f10ff81fb14473f26e9af00fe02d42c99ad2005`
- Build stack: PyTorch `2.9.1+cu130`, CUDA `13.2`

## Install

Install the matching PyTorch stack first.

Recommended CUDA 12.8 / `cu128` build:

```powershell
python -m pip install torch==2.9.1+cu128 torchvision==0.24.1+cu128 torchaudio==2.9.1+cu128 --index-url https://download.pytorch.org/whl/cu128 --extra-index-url https://pypi.org/simple
python -m pip install .\wheelhouse\flash-attn-cuda12.8\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

Legacy CUDA 13 / `cu130` builds:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
python -m pip install .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

## Verification

```python
import flash_attn
import torch

print(flash_attn.__version__)
print(torch.__version__, torch.version.cuda)
```

Expected stack for the recommended wheel:

- `flash_attn`: `2.8.3`
- `torch`: `2.9.1+cu128`
- `torch.version.cuda`: `12.8`

## Build Notes

- Upstream source: `https://github.com/Dao-AILab/flash-attention`
- The recommended wheel was built on Windows in `.venv312` with a repo-local CUDA `12.8` toolkit assembled from NVIDIA's official redistrib archives under `cuda_12_8_redist/toolkit`
- The Windows source build required a `setup.py` patch to add `/Zc:preprocessor`
- The CUDA 12.8 build also required `-allow-unsupported-compiler` for the installed VS 2022 MSVC toolset
- The recommended wheel was verified locally on an RTX 3090 with CUDA forward and backward tests
- Avoid validating from the repo root if possible, because the local `triton` directory can shadow Torch's Triton package

## License

FlashAttention is an upstream open-source project. See the upstream repository for license and source details:

- `https://github.com/Dao-AILab/flash-attention`
