## 🐍 Step-by-Step Guide: Using Python with Conda on a Linux Workstation (Lmod + Anaconda3)

### ✅ Step 1: Load the Anaconda Module

1. **Open the terminal**.

2. Check available Python-related modules:

   ```bash
   module avail anaconda
   ```

3. Load the Anaconda module (adjust version if needed):

   ```bash
   module load anaconda3
   ```

4. Check that `conda` is available:

   ```bash
   conda --version
   ```

---

### ✅ Step 2: Create a Conda Environment

1. Create a new environment (e.g., called `myenv`) with Python 3.9:

   ```bash
   conda create --name myenv python=3.9
   ```

2. Activate the environment:

   ```bash
   conda activate myenv
   ```

3. You should now see `(myenv)` at the start of your terminal prompt.

---

### ✅ Step 3: Install Python Packages

Let’s install some useful packages for scientific work:

```bash
conda install numpy pandas matplotlib jupyter
```

Or if you want to use `pip` (for non-Conda packages):

```bash
pip install somepackage
```

---

### ✅ Step 4: Run Python Interactively

1. Start the Python shell:

   ```bash
   python
   ```

2. Try a quick example:

   ```python
   import numpy as np
   a = np.array([1, 2, 3])
   print("Array:", a)
   print("Mean:", a.mean())
   ```

3. Exit the shell:

   ```python
   exit()
   ```

---

### ✅ Step 5: Run a Python Script

1. Create a simple Python file:

   ```bash
   nano hello.py
   ```

2. Paste this content:

   ```python
   print("Hello from Python!")
   ```

3. Save (Ctrl+O), then exit (Ctrl+X).

4. Run it:

   ```bash
   python hello.py
   ```

---

### ✅ Step 6: (Optional) Run Jupyter Notebook

1. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

2. A browser should open. If not, it will show a link you can copy and paste into your browser.

3. Create a new notebook and try:

   ```python
   import pandas as pd
   df = pd.DataFrame({"x": [1, 2, 3], "y": [4, 5, 6]})
   df.plot()
   ```

---

### ✅ Step 7: Deactivate Environment

When you're done:

```bash
conda deactivate
```

---

### ✅ Summary of Useful Commands

| Command                         | Description                    |
| ------------------------------- | ------------------------------ |
| `module load anaconda3`         | Load Anaconda module via Lmod  |
| `conda create --name myenv ...` | Create a new Conda environment |
| `conda activate myenv`          | Use the Conda environment      |
| `conda install package-name`    | Install packages               |
| `python script.py`              | Run a Python script            |
| `jupyter notebook`              | Launch Jupyter in browser      |
| `conda deactivate`              | Exit Conda environment         |
