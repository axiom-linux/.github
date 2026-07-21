<p align="center">
  <img src="https://axiom.bottlecat.xyz/axiphoto/axiomicon.png" alt="Axiom GNU/Linux" width="200">
</p>

<h1 align="center">Axiom GNU/Linux</h1>
<p align="center"><strong>Simple, Stable, Centrist.</strong></p>
<p align="center">
  <a href="https://axiom.bottlecat.xyz">Website</a> · <a href="https://axiom.bottlecat.xyz/axm/index.html">AXM Docs</a> · <a href="https://axiom.bottlecat.xyz/wiki/index.html">Wiki</a> · <a href="https://axiom.bottlecat.xyz/downloads/index.html">Downloads</a> · <a href="https://discord.gg/9YHAZUZ4PX">Discord</a>
</p>

---

Axiom is an independent GNU/Linux distribution built on a deeply debloated Debian Sid base. It uses a hybrid declarative architecture—your host system stays pristine and rock-solid while containerized Distropaks let you run packages from literally any other distro without breaking anything. The whole thing is driven by `axm`, a C-compiled package engine that resolves cross-distro package names in under 1ms using a memory-mapped binary search index. Yeah, I wanted it to be insanely fast. Yeah its totally gonna get bottlenecked by the Distropak's package manager.

This is a passion project architected and programmed from scratch by a 13-year-old developer. Made by a coder, for coders.

---

### `Extended Features List`

**`[01]` The AXM Engine: C-Compiled & Declarative Core**
> AXM is written directly in C for sub-millisecond execution. It keeps your system declarative via files in `/etc/axiom/axm/packages.d/` (like `system.list` and `flatpak.list`). You run `sudo axm pkg-add [PACKAGE]` to add packages, `axm pkg-rfsh` to refresh repos (built Sid version-drift proof so unstable mirror shifts don't ruin your day), `axm pkg-updt` to cache updates locally, and `axm apply` to install everything. It uses a memory-mapped binary search index (`packages.bin`) built weekly via GitHub Actions to resolve cross-distro package names in under 1ms. And yes, native system installs require a physical reach keyguard (`ctrl + ;`) and typing `<3 Proceed` (yes, Deltarune reference lmfao).

**`[02]` AXM Distropaks: Run Any Distro, Sandboxed & Containerized**
> Basically, you get to run software from literally any distro without installing their system junk or breaking your main OS libraries. Want Arch or CachyOS packages? Grab `rolling`. Fedora? `secure`. Rawhide? `latest`. Debian, Alpine, Gentoo? Just pick the tag. Distropaks integrate directly into your host system—exporting desktop shortcuts, icons, and binaries so they feel and launch just like native packages. Type `axm run [DISTROPAK]` to drop into a throwaway shell that nukes itself the second you exit.

**`[03]` Axiom-SOS, Blackbox & Emergency Rescue**
> Universal log diagnostics and emergency recovery. `Axiom-SOS` aggregates and hypersorts error logs across all containers and host layers by severity—so kernel panics sit at the very top and chatty driver warnings sit at the bottom where you can ignore them. If your system refuses to boot, mount your drive on another PC and run `axiom-blackbox` to get a clean tree of root errors that bricked it. And `axiom-rescue` gives you an initramfs prompt on boot: press `'R'` for a 1-key Ext4 snapshot rollback in under 5 seconds.

**`[04]` Axiom-Modhub & Throttled Background Updates**
> Hardware, driver, and kernel integration center. `axiom-modhub` manages proprietary GPU drivers, firmware, and motherboard BIOS updates. It includes `axiom-modhub -kS` (Kernel Swap) which brings up an eselect-like kernel list to instantly swap kernels in 3 seconds using `kexec` without rebooting your motherboard! Plus, background updates (`axm apply --idle`) run inside cgroups with `ionice` low-priority scheduling so your game or video compilation never loses a single frame.

**`[05]` Axiom-Locker, CVE Shield & Cryptographic Auditor**
> Total permission and security control. `axiom-locker` is a TUI/CLI permission manager for Flatpaks, Snaps, and Distropaks, automatically tweaking Flatpak permissions on install to act like native apps out of the box. `axiom-shield` runs on a timer to check your installed packages against live zero-day CVE databases, while `axm audit` scans system binary hashes against official GPG signatures to make sure nothing was tampered with.

**`[06]` Axiom-Welcome, TUI Appstore & Real-Time Theme Engine**
> First-boot setup, visual browsing, and desktop styling. `axiom-welcome` launches a clean TUI wizard right after install to help you pick drivers and distropaks. `axiom-appstore` gives you a keyboard-navigable terminal storefront (inspired by Pamac and Shelly). If an APT package dependency collides on Sid, `axm resolve` automatically offers 1-click alternative Distropak paths. And `axiom-theme` translates your wallpapers, cursors, and GTK/Qt/XFCE themes across all installed DEs in real-time so your desktop looks cohesive everywhere.

**`[07]` Shadow VMs, Time-Machine & State Portability**
> Test risky stuff and control system state safely. Run `axm check` for dry-run validation. Want to test a sketchy package? `axm try [PACKAGE]` (Shadow VM) spins up a temporary microVM overlay of your live desktop that completely evaporates when you close it. `axm revert` (Axiom Time-Machine) rolls back Ext4 OverlayFS & rsync state without touching your personal home files. Inspect color-coded state changes with `axm diff`, or export your exact setup to a Live ISO with `axm export --iso`.

**`[08]` Pristine Debian Base & Archinstall-Style Setup**
> Deeply debloated Debian Sid core with custom kernel tuning—you need superpowers to break it. Includes `axiom-install`, a paginated CLI dashboard modeled after the ease of archinstall so you don't have to manually bootstrap unless you want to. Automatically configures Ext4 single partitions, ESP/Swap, and GRUB supporting both Legacy BIOS (MBR/GPT) and UEFI. Includes `axiom-live-desktop` for an instant LXQt live environment. Prepackaged with Waterfox for a good browser on everything from rust-buckets to supercomputers.

**`[09]` Centrist Philosophy & About the Dev**
> Axiom is an independent passion project architected and programmed from scratch by a 13-year-old developer. Made by a coder, for coders. Yes, you read that correctly. I am 13 years old, solo-deving Axiom. Sure, things like the roadmap and certain elements required the help of AI/vibecoding, but all ideas, MOST of the code, and all the love is from me. Axiom is a 'centrist distribution'—giving you options to use an install script or bootstrap, cutting-edge rolling packages or rock-solid enterprise stability, and pristine host isolation alongside containerized Distropaks.

**`[10]` Non-Destructive Migrator & Seamless /home Transfers**
> Transitioning to Axiom without wiping your personal life. The `axiom-migrate` installer migrates from your existing Linux distro directly into Axiom without losing any of your personal files, game saves, or dotfiles. It shrinks your old host OS filesystem, creates a temporary `TRANSFER` cache partition, moves your `/home` directory and browser profiles over, and then installs Axiom's pristine core. On first boot, the wizard automatically reconciles permissions and links your home data back cleanly. Zero data loss, zero manual USB backup hassle, and absolutely zero bullshit.

**`[11]` Auto-Healing Config Watcher**
> Your system fixes itself. `axiom-autoheal` is a background daemon that periodically compares your host filesystem and configuration state against the `/etc/axiom/axm/packages.d/` blueprint. If a file drifts or becomes corrupted, the daemon automatically runs a silent transaction to heal the file back to its declared state. Configuration drift doesn't stand a chance and will fear you.

**`[12]` Boot Performance Diagnostic Console**
> Know exactly what's slowing you down. `axm boot-profile` wraps `systemd-analyze blame` and `systemd-analyze critical-chain` into an interactive terminal dashboard. It identifies bottlenecks—slow service starts, network handshakes—and suggests systemd profile adjustments to optimize your startup times.

**`[13]` Cross-Distro Metadata Translation Database**
> The magic behind sub-1ms package resolution. A weekly GitHub Actions cron job fetches official repository metadata from every supported distro (no web scraping), normalizes packages by shared homepage URLs, binaries, and source archive names, and compiles them into a flat binary table (`packages.bin`). On your machine, `axm` maps this file into memory using `mmap()` and runs an O(log N) binary search on sorted structs. If a package has no homepage or fails correlation, it falls back to name-similarity checks or the fuzzy-matching resolution prompt.

**`[14]` Smart Dependency Resolver**
> Package collision? Axiom saves. `axm resolve` kicks in when host APT package dependencies conflict during Sid updates. It scans Flatpak and active Distropak containers (Arch, Alpine, Fedora) and suggests 1-click alternative sandboxed installation routes so you never get stuck.

**`[15]` Visual State Diff Viewer**
> See exactly what changed. `axm diff` generates a color-coded terminal view highlighting package manifest changes and configuration file alterations relative to previous timestamps or transaction IDs. Think `git diff`, but for your entire system state.

**`[16]` Restricted Raw Package Manager Access**
> Users are blocked from running raw `apt` commands directly. The `axm` wrapper manages all underlying apt and flatpak operations to prevent system pollution and keep package tracking clean. Userland packages are strictly prohibited from being installed to the host system—all userland packages must run inside sandboxes or containerized Distropaks. The host OS remains completely pristine.

---

### `axm pkg-add --source-select`

| Source Tag | Distribution | Description |
|---|---|---|
| `(1) latest` | Fedora Rawhide | Absolute latest upstream development packages |
| `(2) sandbox` | Flatpak / Snap / AppImage | Universal sandboxed desktop applications |
| `(3) stable` | Debian Stable | Rock-solid long-term release packages |
| `(4) secure` | Fedora Linux | Enterprise-grade packages with SELinux hardening |
| `(5) rolling` | Arch Linux / CachyOS | Bleeding-edge rolling release, AUR access |
| `(6) fast` | Alpine Linux | Ultra-lightweight musl-based micro containers |
| `(c) compile` | Gentoo Linux | Source-compiled binaries tuned for your CPU |
| `(ctrl + ;) !system!` | Axiom Native Host | Direct host install (keyguard protected) |

---

### `cat /home/axiom/architecture.txt`

```
+-----------------------------------+
|      ELEVATED SYSTEM LAYER        |
| (Declarative Apps, Containers)    |
+-----------------------------------+
                  |
                  v
+-----------------------------------+
|       STABLE DEBIAN BASE          |
|      (Simple, Rock-Solid)         |
+-----------------------------------+
```

---

### `axiom-install --quick-start`

1. Grab the latest ISO from the [downloads mirror](https://axiom.bottlecat.xyz/downloads/index.html)
2. Flash it to a USB with `dd` (linux), Ventoy (any), or Rufus (windows)
3. Boot into the live environment → type `axiom-live-desktop` for the LXQt live session
4. Run `axiom-install` and follow the paginated CLI dashboard
5. Reboot and you're in. kablamo

---

### `cat /home/axiom/community.txt`

- 🌐 **Website**: [axiom.bottlecat.xyz](https://axiom.bottlecat.xyz)
- 💬 **Discord**: [discord.gg/9YHAZUZ4PX](https://discord.gg/9YHAZUZ4PX)
- 🎵 **TikTok**: [@axiomlinux](https://tiktok.com/@axiomlinux)
- 📦 **ISO Mirror**: [axiom.bottlecat.xyz/downloads](https://axiom.bottlecat.xyz/downloads)
- More to come!

---

<p align="center">
  Axiom GNU/Linux is open-source software under the AGPLv3 License.<br>
  Made with love by <a href="https://github.com/bluebottlecat">bluebottlecat</a>
</p>
