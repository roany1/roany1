# Hi, I'm Roany 👋

**Roany Romano** — electronic engineer and physicist.
I work with **particle detectors** (silicon / LGAD) and the **ROOT** data-analysis framework from CERN, and I build tools at the intersection of physics, electronics and software.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![ROOT](https://img.shields.io/badge/CERN%20ROOT-1E5EAB)
![Rust](https://img.shields.io/badge/Rust-000000?logo=rust&logoColor=white)
![macOS](https://img.shields.io/badge/Apple%20Silicon-000000?logo=apple&logoColor=white)

---

## 📌 Installing ROOT / PyROOT on Apple Silicon (M1 and later)

When Apple M1 machines came out, many people (me included) could not get the **PyROOT** libraries from [ROOT](https://root.cern) to work on them. This is the procedure I found and [shared on the CERN ROOT forum](https://root-forum.cern.ch/t/how-to-install-root-with-pyroot-in-apple-m1/48459/9).

The root cause is usually a mix of **x86_64 (Intel)** and **arm64** Python/Conda installations on the same machine. The fix is to start from a clean, native arm64 Conda and install ROOT from `conda-forge`.

### 1. Remove non-native installations

If you have a Conda build that is **not** for Apple Silicon (often several Python versions pile up), uninstall it completely.

If you have an old Homebrew installation that is not arm64-native, remove it too, so incompatible files don't interfere with the new arm64 Conda. To find where it lives:

```bash
which brew
```

> Native Apple Silicon Homebrew lives in `/opt/homebrew`; an Intel one lives in `/usr/local`.

### 2. Install Miniconda for Apple Silicon

Download the **arm64** installer from the [Miniconda page](https://docs.conda.io/en/latest/miniconda.html):

```bash
curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
sh ./Miniconda3-latest-MacOSX-arm64.sh
```

### 3. Create an environment with ROOT

Following the [official ROOT instructions for Conda](https://root.cern/install/#conda):

```bash
conda config --set channel_priority strict
conda create -c conda-forge --name <my-environment> root
conda activate <my-environment>
```

For example:

```bash
conda config --set channel_priority strict
conda create -c conda-forge --name env1 root
conda activate env1
```

### 4. Check it works

With the environment active, open `python3` and run:

```python
import ROOT
```

It now imports without errors. (At the time, Conda installed Python 3.10 in the environment.)

🔗 **Original discussion:** [How to install ROOT with PyROOT in Apple M1 — ROOT Forum](https://root-forum.cern.ch/t/how-to-install-root-with-pyroot-in-apple-m1/48459/9)

Thanks to everyone on the forum for the support.

---

## 🛠️ Other projects

- [**ferrotherm**](https://github.com/roany1/ferrotherm) — open-source thermal solver for electronics, written in Rust
- [**loopback-router**](https://github.com/roany1/loopback-router) — route audio between applications on macOS and Windows

---

<details>
<summary>📜 Original note (2022, unedited)</summary>

```text
Hi friends, I wanted to tell of PyRoot from ROOT CERN Framework.

What did I do to install it?

I have seen that people with an "Apple M1" have problems installing ROOT or rather PyRoot libraries on this machine.

I work with Particle Detectors and I work with ROOT.
I am an entrepreneur's Technology and futuristic visionary, I m a maker technology.

In this Readme, I talk about how I solved installation of PyRoot libraries.



if you have a version of Conda not for Apple Silicon, please delete all.
(many python version there are)
delete all homebrew installation for delete all file not compatible with new conda for arm64.
use:

where homebrew

and delete

I downloaded the version of CONDA for Apple Silicon M1 directly from here:
https://docs.conda.io/en/latest/miniconda.html 
the file is:
https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh
( for newbie install with sh ./filename.sh)

After that I followed as reported:
in this link

https://root.cern/install/#conda


$ conda config --set channel_priority strict 
$ conda create -c conda-forge --name <my-environment> root 
$ conda activate <my-environment>
  
for example:
  
conda config --set channel_priority strict 
conda create -c conda-forge --name env1 root 
conda activate env1
With enviroment conda actived

in python3 prompt

’’’
import ROOT
’’’
now work fine, without error.
Python 3.10 is installed with conda.

I posted this solution on the CERN ROOT forum, where I was looking for help to install it and finally shared the solution I found myself
https://root-forum.cern.ch/t/how-to-install-root-with-pyroot-in-apple-m1/48459/9

Thanks for support
```

</details>
