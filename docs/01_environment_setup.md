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

- Updated the Ubuntu package index using `sudo apt update`.
- Upgraded installed packages using `sudo apt upgrade`.
- Installed Git using `sudo apt install git`.
- Verified Git installation using `git --version`.

**Note:** Record the actual completion status and Git version after running these commands.
