# Voidstrap Overlay

Gentoo overlay for [Voidstrap](https://github.com/KloBraticc/Voidstrap), a Roblox bootstrapper for Linux that launches Roblox through Sober.

## Gentoo

First, make sure the repository module for `eselect` and Git are installed:

```console
$ emerge app-eselect/eselect-repository dev-vcs/git
```

Then add the Voidstrap overlay:

```console
$ eselect repository add "Voidstrap-Overlay" git https://github.com/Pedrodroks34/voidstrap-overlay.git
$ emaint sync
```

Then emerge Voidstrap:

```console
$ emerge -av games-action/voidstrap
```

### Live ebuild

The overlay provides a live `9999` ebuild that follows the latest version from the `main` branch.

To allow the live ebuild, create:

```text
/etc/portage/package.accept_keywords/voidstrap
```

with:

```text
games-action/voidstrap **
```

Then emerge:

```console
$ emerge -av =games-action/voidstrap-9999
```

### .NET SDK

Voidstrap currently requires a .NET 10 SDK. This overlay also provides the `10.0.400` `dotnet-sdk-bin` ebuild used to build the live version:

```console
$ emerge -av dev-dotnet/dotnet-sdk-bin
```

After adding the overlay, Portage will be able to resolve the required SDK when installing Voidstrap.
