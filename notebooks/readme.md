# 🧠 Semantic Project – Setup Guide

This guide will help you set up a virtual Python environment and install all the necessary dependencies for semantic analysis and visualization.

---

## 🔧 Step 1: Create a Virtual Environment

Use Python’s built-in `venv` module to create an isolated environment called `semantic_env`:

```bash
python -m venv semantic_env
```

This will create a folder named `semantic_env` in your current directory.

---

## ▶️ Step 2: Activate the Virtual Environment (Windows)

Activate the virtual environment:

```bash
semantic_env\Scripts\activate.bat
```

You should see `(semantic_env)` appear in your terminal prompt, indicating that the environment is active.

---

## 📦 Step 3: Install Required Packages

Install all required Python libraries:

```bash
pip install sentence-transformers scikit-learn pandas matplotlib ipykernel
```

These packages are used for:
- `sentence-transformers`: semantic vector embeddings and similarity
- `scikit-learn`: clustering and machine learning
- `pandas`: data manipulation
- `matplotlib`: data visualization
- `ipykernel`: Jupyter kernel integration

---

## 🧪 Step 4: Register the Environment for Jupyter

Register the environment so it can be selected in Jupyter Notebook or JupyterLab:

```bash
python -m ipykernel install --user --name=semantic_env --display-name "Python (semantic)"
```

After this, `"Python (semantic)"` will be available as a kernel option in Jupyter.

---

## ✅ Done!

Your semantic environment is now ready. Happy coding!
