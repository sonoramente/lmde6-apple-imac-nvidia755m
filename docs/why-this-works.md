## Debian Driver Policy (Why 535 Is Rejected)

On Debian 12 / LMDE 6, the meta-package `nvidia-driver` points to the current
mainline NVIDIA branch (535+). Kepler GPUs such as the GT 755M are no longer
supported by this branch.

During installation, Debian detects this mismatch and prevents installation,
redirecting the user to the legacy Tesla 470 driver instead.

This behavior is intentional and protects the system from loading an
unsupported graphics stack.
