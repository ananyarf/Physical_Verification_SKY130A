# SKY130A Physical Verification

## 1. Objective

Set up a Linux environment for exploring physical verification using the SKY130A open-source process design kit (PDK).

## 2. Development Environment

- Host OS: Windows
- Virtualization: Oracle VirtualBox
- Guest OS: Ubuntu Linux
- PDK: SKY130A
- Project repository: Physical_Verification_SKY130A

## 3. Environment Setup

### Step 1: VirtualBox

VirtualBox is used to run Ubuntu in a virtual machine without replacing the Windows host operating system.

### Step 2: Ubuntu Installation

Ubuntu installation is currently in progress.

### Step 3: Environment Validation

After installation, verify the operating system and available resources.

Commands to run:

```bash
lsb_release -a
uname -a
free -h
df -h
```

## 4. Progress

- [x] Create a personal GitHub fork.
- [ ] Install and configure Ubuntu.
- [ ] Verify the Linux environment.
- [ ] Install the required EDA tools.
- [ ] Configure the SKY130A PDK.
- [ ] Run and document physical verification.

## 5. Results and Screenshots

Screenshots and verified results will be added as the work progresses.




## 4. System Information and Validation

### Operating System

- Distribution: Ubuntu
- Version: 26.04.1 LTS
- Virtualization platform: Oracle VirtualBox

### Virtual Machine Resources

| Resource | Observed value |
|---|---|
| RAM | 10 GiB |
| CPU cores | 6 |
| Root filesystem size | 16 GiB |
| Available root disk space | 8.6 GiB |
| Swap memory | 0 GiB |

### Validation Commands

```bash
lsb_release -a
free -h
df -h /
nproc
```

### Initial Observations

- Ubuntu boots successfully inside VirtualBox.
- The operating system version and allocated resources have been verified.
- The available disk space is limited for the planned EDA tools and SKY130A PDK setup.
- Virtual disk capacity will be reviewed before installing project dependencies.

### Status

Operating system installation and initial system validation completed.


### Package Updates and Git Installation



### Git Setup and Repository Access

- Git version: 2.53.0
- Configured Git username and email.
- Cloned the personal SKY130A Physical Verification repository.
- Inspected the repository files and verified the Git working tree.

**Status:** Update each item according to the actual result.



## 5. Git Installation and Repository Setup

### Git Installation

- Git version: 2.53.0
- Installation verified using `git --version`.

### Repository Setup

- Personal GitHub fork created.
- Repository cloned into the Ubuntu environment.
- Repository files inspected.
- Git working-tree status checked.

### Evidence

- `03_git_version.png` — Git version verification.
- `04_git_repository_status.png` — Repository status.

### Outcome

Git is installed, and the project repository is available locally in Ubuntu.

- Updated the Ubuntu package index using `sudo apt update`.
- Upgraded installed packages using `sudo apt upgrade`.
- Installed Git using `sudo apt install git`.
- Verified Git installation using `git --version`.

**Note:** Record the actual completion status and Git version after running these commands.

## Magic VLSI Installation on Ubuntu — Errors and Fixes

During the setup of the physical verification flow for SKY130A, I encountered compilation issues while building Magic VLSI from source on Ubuntu. This section documents the errors and their solutions.

### 1. Clone the Magic Source Code

```bash
git clone git://opencircuitdesign.com/magic
cd magic
```

Install the basic Tcl/Tk development dependencies:

```bash
sudo apt update
sudo apt install tcl-dev tk-dev
```

### 2. GCC 15 Compilation Error

**Error encountered:**

```text
error: too many arguments to function 'WindAddCommand'
error: too many arguments to function 'WindMove'
error: too many arguments to function 'WindSetWindowAreas'
error: too many arguments to function 'WindAddClient'
```

**Cause:**

The default C language standard used by GCC 15 can cause compatibility issues with older C code.

**Solution:**

Clean the previous build and configure Magic using GNU C17:

```bash
make clean
./configure CFLAGS="-std=gnu17"
```

If configuration completes successfully, compile the source:

```bash
make
```

### 3. Missing OpenGL/GLU Header

**Error encountered:**

```text
fatal error: GL/glu.h: No such file or directory
```

**Cause:**

The required OpenGL/GLU development headers were missing from the system.

**Solution:**

Install the required development packages:

```bash
sudo apt update
sudo apt install libgl-dev libglu1-mesa-dev
```

After installation, run the compilation again:

```bash
make
```

### 4. Install Magic

After successful compilation, install Magic:

```bash
sudo make install
```

Verify that the installation is accessible:

```bash
which magic
```

### 5. Optional Dependencies

The Magic configuration script may report that OpenGL, Cairo, or LaTeX documentation support is unavailable.

These features are not all mandatory for a basic build.

For OpenGL support, install:

```bash
sudo apt install libgl-dev libglu1-mesa-dev
```

For Cairo support, install:

```bash
sudo apt install libcairo2-dev
```

LaTeX-related dependencies are needed when regenerating the documentation, not simply to compile and run Magic.

### 6. Important Notes

- Run `./configure` again after changing compiler flags or installing missing development libraries.
- Use `make clean` before rebuilding when changing compilation settings.
- If compilation fails, read the first actual compiler error rather than focusing only on the final `make` error.
- The commands and fixes documented here were tested during setup on Ubuntu with GCC 15.2.0. Results may vary with other operating system and compiler versions.

**Status:** Magic compiled successfully after using GNU C17 and installing the missing OpenGL/GLU development packages. Installation was then performed using `sudo make install`.


### 7. Verify the Installation

Check the installed executable path:

```bash
which magic
```

Launch Magic:

```bash
magic
```

**Result:** Magic launches successfully on Ubuntu, confirming that the installation works.




