# Step 0:  Installing Miniconda (macOS & Linux)

Miniconda is a minimal installer for Conda, a popular package and environment manager. Follow the steps below to install it on your system.

### 📦 For macOS

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh
```

### 🐧 For Linux

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

### 🛠 After Installation

Once installed, close and reopen your terminal, or run:

```bash
source ~/.bashrc
```

Then verify that Conda is available:

```bash
conda --version
```

You're now ready to create environments and install packages using Conda.

