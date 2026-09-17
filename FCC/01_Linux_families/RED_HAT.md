# RED HED ENTRIPRE LINUX [REHL]

# RHEL Family (Red Hat Enterprise Linux)

```text
Linux Kernel
      │
      ▼
Red Hat Enterprise Linux (RHEL)
      │
      ├── Fedora
      ├── CentOS
      └── Oracle Linux
```

## Distributions

- **RHEL (Red Hat Enterprise Linux)**
  - Enterprise Linux distribution developed by Red Hat.
  - Used by many companies in production servers.

- **Fedora**
  - Community-driven distribution sponsored by Red Hat.
  - Receives newer features and technologies first.

- **CentOS**
  - Historically a free rebuild of RHEL.
  - Today replaced by **CentOS Stream**, which sits between Fedora and RHEL in the development cycle.

- **Oracle Linux**
  - Oracle's enterprise Linux distribution.
  - Compatible with RHEL and commonly used in Oracle environments.

## Package Manager

| Distribution | Package Format | Package Manager |
|--------------|----------------|-----------------|
| RHEL | `.rpm` | `dnf` (formerly `yum`) |
| Fedora | `.rpm` | `dnf` |
| Oracle Linux | `.rpm` | `dnf` |
| CentOS | `.rpm` | `dnf` / `yum` (older versions) |

## Key Facts About the RHEL Family

- **Fedora** is the upstream testing platform for RHEL.
  - New features are introduced and tested in Fedora before reaching RHEL.

- **CentOS**
  - Historically a free, community rebuild of RHEL.
  - Today, **CentOS Stream** acts as the upstream development branch for RHEL.

- **Supported Architectures**
  - Intel x86 (x86_64)
  - ARM (AArch64)
  - Itanium (legacy)
  - PowerPC (legacy)

- **Package Manager**
  - Uses **YUM** (Yellowdog Updater, Modified) on older releases.
  - Modern RHEL and Fedora use **DNF**, which replaced YUM while keeping compatibility.

- **Enterprise Focus**
  - Designed for enterprise environments.
  - Known for stability, long-term support (LTS), and security.
  - Commonly used on production servers, cloud platforms, and data centers.