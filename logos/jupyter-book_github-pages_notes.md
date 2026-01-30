# Deploying a Jupyter Book on GitHub Pages

These steps describe how to create and publish a Jupyter Book as a static site using GitHub Pages.

---

## 1. Prepare the Book Configuration

1. Create the Jupyter Book configuration files in your repo:

- `_toc.yml` → defines the **table of contents**  
- `_config.yml` → defines **site settings and options**

---

## 2. Set Up a Python Environment

1. Create a virtual environment:

```bash
python3 -m venv .venv
```

2. Activate the environment and install required packages:

```bash
# Activate (Linux/macOS)
source .venv/bin/activate

# Activate (Windows PowerShell)
.venv\Scripts\Activate.ps1

# Install packages
pip install "jupyter-book<2" ghp-import
```

## 3. Build the Jupyter Book

Run the build command:
````
jupyter-book build PATH_SOURCE
````
Replace PATH_SOURCE with the path to your book root (e.g., . if you’re in the repo root).  
This generates the HTML site in _build/html

## Publish the Book to GitHub Pages

1. Deploy the built HTML to GitHub Pages:
````
ghp-import -n -p -f _build/html
````
* `-n` → disables Jekyll
* `-p` → pushes to GitHub
* `-f` → force overwrites existing gh-pages branch