# docstring-generator

AST-powered Python docstring generator using local LLM inference with support for Google, NumPy, and Sphinx docstring styles.

---

## Features

- AST-based Python function parsing
- Local LLM-powered docstring generation
- Google-style rendering
- NumPy-style rendering
- Sphinx-style rendering
- Parameter validation layer
- Modular rendering pipeline
- Extensible architecture
- Streamlit frontend support

---

## Architecture

The pipeline consists of:

1. AST-based function parser
2. Function metadata extractor
3. Prompt builder
4. LLM inference layer
5. Style renderer
6. Validation layer
7. Universal pipeline runner

---

## Supported Docstring Styles

### Google Style

```python
"""
Adds two integers together.

Args:
    a (int): The first integer to add.
    b (int): The second integer to add.

Returns:
    int: The sum of the two integers.
"""
```

### NumPy Style

```python
"""
Adds two integers together.

Parameters
----------
a : int
    The first integer to add.
b : int
    The second integer to add.

Returns
-------
int
    The sum of the two integers.
"""
```

### Sphinx Style

```python
"""
Adds two integers together.

:param a: The first integer to add.
:type a: int
:param b: The second integer to add.
:type b: int

:return: The sum of the two integers.
:rtype: int
"""
```

---

## Example

### Input

```python
def add(a: int, b: int = 0) -> int:
    return a + b
```

### Generated Output

```python
"""
Adds two integers together.

Args:
    a (int): The first integer to add.
    b (int): The second integer to add.

Returns:
    int: The sum of the two integers.
"""
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/docstring-generator.git
cd docstring-generator
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Usage

```python
from app.pipeline import run_pipeline

source_code = '''
def multiply(x: float, y: float) -> float:
    return x * y
'''

result = run_pipeline(
    source_code,
    style="google"
)

print(result)
```

---

## Pipeline Overview

```text
Source Code
    ↓
AST Parsing
    ↓
Metadata Extraction
    ↓
Prompt Construction
    ↓
LLM Inference
    ↓
Style Rendering
    ↓
Validation
    ↓
Final Docstring
```

---

## Roadmap

- [x] Google-style rendering
- [x] NumPy-style rendering
- [ ] Sphinx-style polishing
- [ ] Streamlit UI
- [ ] Batch processing
- [ ] PyPI packaging
- [ ] Hugging Face deployment
- [ ] Docker support
- [ ] VSCode extension
- [ ] CI/CD integration

---

## Tech Stack

- Python
- AST
- Hugging Face Transformers
- PyTorch
- Google Colab
- Streamlit

---

## License

MIT License
