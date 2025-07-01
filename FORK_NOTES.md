# My Custom Fork of ColBERT

This repository is a customized fork of [stanford-futuredata/ColBERT](https://github.com/stanford-futuredata/ColBERT).

## 📦 Building and Publishing `colbert-modern` to PyPI

This guide walks you through building and uploading the `colbert-modern` package to [PyPI](https://pypi.org/).

### ✅ Prerequisites

- Python 3.8+
- A [PyPI account](https://pypi.org/account/register/)
- Your project should include:
  - `setup.py`
  - `README.md`
  - `LICENSE`
  - `pyproject.toml` (optional but recommended)

---

### 🧱 Step-by-Step Instructions

#### 1. Create and Activate a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

#### 2. Install Build Tools

```bash
pip install --upgrade build
```

#### 3. Build the Package

This will generate `dist/` containing `.tar.gz` and `.whl` files.

```bash
python -m build
```

### 4. Install Twine

```bash
pip install --upgrade twine
```

### 5. Configure PyPI Credentials

Create or edit your `~/.pypirc` file or `$HOME/.pypirc` :
> 💡 You can generate a token from your [PyPI account settings](https://pypi.org/manage/account/).

```bash
[distutils]
index-servers =
    pypi

[pypi]
username = __token__
password = pypi-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

#### 6. Upload the Package

```bash
twine upload --repository pypi dist/*
```

Sample output:

```bash
Uploading distributions to https://upload.pypi.org/legacy/
Uploading colbert_modern-0.1.0-py3-none-any.whl
100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 133.8/133.8 kB • 00:00 • 483.0 kB/s
Uploading colbert_modern-0.1.0.tar.gz
100% ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 105.8/105.8 kB • 00:00 • 49.1 MB/s

View at:
https://pypi.org/project/colbert-modern/0.1.0/
```

#### 🧪 Optional: Test on TestPyPI First

To avoid publishing broken packages, test on TestPyPI:

```bash
twine upload --repository testpypi dist/*
```

Install from TestPyPI:

```bash
python -m pip install colbert-modern
```
