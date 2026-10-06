# setup-docker

A GitHub Action to set up Docker on [GitHub-hosted runners](https://docs.github.com/en/actions/using-github-hosted-runners/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources) for Linux, macOS, or Windows.

- All GitHub-hosted Linux runners, including `ubuntu-latest`, have Docker installed and configured already. On Linux, this action has no effect.
- GitHub's macOS and Windows runners do not have Docker installed or fully configured. On these platforms, we install [Podman](https://podman.io) as the backend.
- On macOS, this works only on the Intel-based runner, `macos-13`. It does not work on Apple Silicon runners (`macos-14`, `macos-15`) because [nested virtualization does not work](https://github.com/douglascamata/setup-docker-macos-action/tree/v1-alpha.16?tab=readme-ov-file#arm64-processors-m1-m2-m3-series-used-on-macos-14-images-are-unsupported).
- On Windows, this works on `windows-2022`, `windows-2025`, and `windows-latest`, but not on `windows-11-arm` or `windows-11-vs2026-arm` because the latter two lack WSL2.
