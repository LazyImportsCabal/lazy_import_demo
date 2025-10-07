# Python Lazy Imports Demo

Interactive WebAssembly demo showcasing [PEP 810](https://peps.python.org/pep-0810/) - Explicit Lazy Imports in Python.

## Features

- 🚀 Live Python REPL running in your browser
- 📦 Interactive examples demonstrating lazy import behavior
- 🔍 Real-time `sys.modules` tracking
- ✨ Custom `lazy_demo` package with visible import side effects

## Examples

1. **Basic Usage** - Module not in sys.modules until used
2. **From Import** - Lazy from import syntax
3. **Eager vs Lazy** - Direct comparison with sys.modules
4. **Type Annotations** - Annotations don't trigger loading
5. **Demo Package** - Custom package with import tracking

## Try It Live

Visit the demo at: [https://yourusername.github.io/lazy_import_demo/](https://yourusername.github.io/lazy_import_demo/)

## Running Locally

```bash
python server.py
```

Then open http://localhost:8000/ in your browser.

## About Lazy Imports

Lazy imports allow you to defer module loading until first use:

```python
import sys

lazy import json
print('json' in sys.modules)  # False - not loaded yet

result = json.dumps({"test": 1})  # Now it loads!
print('json' in sys.modules)  # True
```

## Technical Details

- Built with Emscripten (WASM)
- Python 3.15 with PEP 810 implementation
- Requires `SharedArrayBuffer` support (enabled via CORS headers)

## Credits

- PEP 810: Explicit Lazy Imports
- Python WebAssembly build
- Demo by Pablo Galindo Salgado
