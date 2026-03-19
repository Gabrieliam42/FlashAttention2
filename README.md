# FlashAttention 2 Windows Wheels

Prebuilt Windows wheels for FlashAttention 2, built from upstream `flash-attention`.

All published wheels are stored directly at the repository root.

## Evidence Model

- Wheel metadata directly proves:
  - package version
  - Python compatibility tag
- Wheel metadata does not pin an exact Torch version. It only records `Requires-Dist: torch`.
- Exact Torch stack and CUDA toolkit version below come from local build provenance and byte-for-byte SHA256 matches to the original build artifacts in `wheelhouse`.
- For the three CUDA 13.2 wheels, the binary also directly embeds `Cuda compilation tools, release 13.2`.

## Published Wheels

### `flash_attn-2.8.3-torch2.8.0cu128cuda12.8-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python compatibility tag: `cp312-cp312-win_amd64`
- Build/test environment provenance: Python `3.12.10`
- Torch stack provenance: `torch==2.8.0+cu128`, `torchvision==0.23.0+cu128`, `torchaudio==2.8.0+cu128`
- CUDA toolkit provenance: `12.8`
- Target GPU architecture: Ampere (`sm_80`)
- Published filename note: stored with a provenance filename; the canonical wheel filename is `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`
- Size: `56,682,111` bytes
- SHA256: `590f4a177466d17fe6085b2ed00f40f4a8e92d46bc6a41d63ce036727e547e93`

### `flash_attn-2.8.3-torch2.9.1cu128cuda12.8-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python compatibility tag: `cp312-cp312-win_amd64`
- Build/test environment provenance: Python `3.12.10`
- Torch stack provenance: `torch==2.9.1+cu128`, `torchvision==0.24.1+cu128`, `torchaudio==2.9.1+cu128`
- CUDA toolkit provenance: `12.8`
- Target GPU architecture: Ampere (`sm_80`)
- Published filename note: stored with a provenance filename; the canonical wheel filename is `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`
- Size: `56,690,614` bytes
- SHA256: `b94101f7ae37037335bbc51d60030870d6b7ac22282d166e11c84fff4705ceab`

### `flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python compatibility tag: `cp312-cp312-win_amd64`
- Build/test environment provenance: Python `3.12.10`
- Torch stack provenance: `torch==2.9.1+cu130`, `torchvision==0.24.1+cu130`, `torchaudio==2.9.1+cu130`
- CUDA toolkit:
  - direct binary evidence: `13.2`
  - build provenance: `13.2`
- Target GPU architecture: Ampere (`sm_80`)
- Published filename note: stored with a provenance filename; the canonical wheel filename is `flash_attn-2.8.3-cp312-cp312-win_amd64.whl`
- Size: `57,035,463` bytes
- SHA256: `e602dc8936abd714a2c51baa5f10ff81fb14473f26e9af00fe02d42c99ad2005`

### `flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp313-cp313-win_amd64.whl`

- Package version: `flash_attn==2.8.3`
- Python compatibility tag: `cp313-cp313-win_amd64`
- Build/test environment provenance: Python `3.13.12`
- Torch stack provenance: `torch==2.9.1+cu130`, `torchvision==0.24.1+cu130`, `torchaudio==2.9.1+cu130`
- CUDA toolkit:
  - direct binary evidence: `13.2`
  - build provenance: `13.2`
- Target GPU architecture: Ampere (`sm_80`)
- Published filename note: stored with a provenance filename; the canonical wheel filename is `flash_attn-2.8.3-cp313-cp313-win_amd64.whl`
- Size: `57,031,437` bytes
- SHA256: `1f8d356ef4ef38e353ad2c035afc75932426deceb39c0ba99821f5ff95434c95`

### `flash_attn-2.8.1-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl`

- Package version: `flash_attn==2.8.1`
- Python compatibility tag: `cp312-cp312-win_amd64`
- Build/test environment provenance: Python `3.12.10`
- Torch stack provenance: `torch==2.9.1+cu130`, `torchvision==0.24.1+cu130`, `torchaudio==2.9.1+cu130`
- CUDA toolkit:
  - direct binary evidence: `13.2`
  - build provenance: `13.2`
- Target GPU architecture: Ampere (`sm_80`)
- Published filename note: stored with a provenance filename; the canonical wheel filename is `flash_attn-2.8.1-cp312-cp312-win_amd64.whl`
- Size: `28,682,044` bytes
- SHA256: `4507b92e3e9cb24acde3d50fb002ac0ea9b374f94bf6be3f315e7162e0a95fef`

## Install

Install the matching PyTorch stack first.
Published filenames include provenance data. Copy only the matching wheel to the canonical filename shown in each example before installing with `pip`.

For `flash_attn-2.8.3-torch2.8.0cu128cuda12.8-cp312-cp312-win_amd64.whl`:

```powershell
python -m pip install torch==2.8.0+cu128 torchvision==0.23.0+cu128 torchaudio==2.8.0+cu128 --index-url https://download.pytorch.org/whl/cu128 --extra-index-url https://pypi.org/simple
Copy-Item .\flash_attn-2.8.3-torch2.8.0cu128cuda12.8-cp312-cp312-win_amd64.whl .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
python -m pip install .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

For `flash_attn-2.8.3-torch2.9.1cu128cuda12.8-cp312-cp312-win_amd64.whl`:

```powershell
python -m pip install torch==2.9.1+cu128 torchvision==0.24.1+cu128 torchaudio==2.9.1+cu128 --index-url https://download.pytorch.org/whl/cu128 --extra-index-url https://pypi.org/simple
Copy-Item .\flash_attn-2.8.3-torch2.9.1cu128cuda12.8-cp312-cp312-win_amd64.whl .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
python -m pip install .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

For the CUDA 13.2 wheels:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
Copy-Item .\flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
python -m pip install .\flash_attn-2.8.3-cp312-cp312-win_amd64.whl
```

For the Python 3.13 provenance-named CUDA 13.2 wheel:

```powershell
python -m pip install torch==2.9.1+cu130 torchvision==0.24.1+cu130 torchaudio==2.9.1+cu130 --index-url https://download.pytorch.org/whl/cu130 --extra-index-url https://pypi.org/simple
Copy-Item .\flash_attn-2.8.3-torch2.9.1cu130cuda13.2-cp313-cp313-win_amd64.whl .\flash_attn-2.8.3-cp313-cp313-win_amd64.whl
python -m pip install .\flash_attn-2.8.3-cp313-cp313-win_amd64.whl
```

If you specifically want `flash_attn==2.8.1` on the same stack:

```powershell
Copy-Item .\flash_attn-2.8.1-torch2.9.1cu130cuda13.2-cp312-cp312-win_amd64.whl .\flash_attn-2.8.1-cp312-cp312-win_amd64.whl
python -m pip install .\flash_attn-2.8.1-cp312-cp312-win_amd64.whl
```

## Verification

```python
import flash_attn
import torch

print(flash_attn.__version__)
print(torch.__version__, torch.version.cuda)
```

Expected stack for `flash_attn-2.8.3-torch2.8.0cu128cuda12.8-cp312-cp312-win_amd64.whl`:

- `flash_attn`: `2.8.3`
- `torch`: `2.8.0+cu128`
- `torch.version.cuda`: `12.8`

## Build Notes

- Upstream source: `https://github.com/Dao-AILab/flash-attention`
- The two CUDA 12.8 wheels were built on Windows in `.venv312` against a repo-local CUDA `12.8` toolkit assembled from NVIDIA redistrib archives under `cuda_12_8_redist/toolkit`
- The three CUDA 13.2 wheels target the `torch==2.9.1+cu130` stack
- All published wheels use provenance filenames; rename or copy each wheel to its canonical wheel filename before installing with pip
- The Windows source build required a `setup.py` patch to add `/Zc:preprocessor` and `-allow-unsupported-compiler`
- The CUDA 12.8 wheels were verified locally on an RTX 3090 with CUDA forward and backward tests
- Avoid validating from the repo root if possible, because the local `triton` directory in the build workspace can shadow Torch's Triton package

## License

FlashAttention is an upstream open-source project. See the upstream repository for license and source details:

- `https://github.com/Dao-AILab/flash-attention`
