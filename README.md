A guide on how to **download** and **install mods** in [Lethal Company](https://store.steampowered.com/app/1966720/Lethal_Company/) on PC.

Lethal Company runs on [Unity](https://unity.com/), so almost every mod for it is a [BepInEx](https://github.com/BepInEx/BepInEx) plugin. The overwhelming majority of them live on [Thunderstore](https://thunderstore.io/c/lethal-company/) rather than Nexus Mods, which is the opposite of what most people expect coming from something like Skyrim or Fallout.

We cover three mod managers plus the manual method, and we use [MoreCompany](https://thunderstore.io/c/lethal-company/p/notnotnotswipez/MoreCompany/) as the worked example throughout.

[**View Guide On TMC (Recommended Due To Better Formatting)**](https://moddingcommunity.com/blog/how-to-install-mods-in-lethal-company/)

## Table Of Contents
* [Requirements](#requirements)
* [How Lethal Company Modding Works](#how-lethal-company-modding-works)
    * [Everyone In The Lobby Needs The Same Mods](#everyone-in-the-lobby-needs-the-same-mods)
* [Picking A Mod Manager](#picking-a-mod-manager)
* [Installing With Thunderstore Mod Manager](#installing-with-thunderstore-mod-manager)
* [Installing With Gale](#installing-with-gale)
* [Installing With r2modman](#installing-with-r2modman)
* [Installing Manually](#installing-manually)
    * [Installing BepInEx](#installing-bepinex)
    * [Installing MoreCompany](#installing-morecompany)
* [Installing With The TMC App](#installing-with-the-tmc-app)
* [Checking Your Mods Loaded](#checking-your-mods-loaded)
* [Updating And Removing Mods](#updating-and-removing-mods)
* [Troubleshooting](#troubleshooting)
* [Conclusion](#conclusion)
* [See Also](#see-also)

## Requirements
* A PC running **Windows 10** or later, **Linux**, or **macOS**.
* A copy of **Lethal Company** on Steam.
* Around **1 GB** of free space for a typical mod list. Big content packs can push this much higher.
* A program that can extract `.zip` files if you plan to install manually. Windows 11 handles this on its own, and [7-Zip](https://www.7-zip.org/) works everywhere.

**NOTE** - Lethal Company has no anti-cheat, so there is no ban risk in modding it. It is still worth keeping a clean copy of the game folder around if you like to experiment.

## How Lethal Company Modding Works
Nearly every Lethal Company mod is a `.dll` file that gets loaded by BepInEx, a general purpose mod loader for Unity games. Nothing loads without it, so [BepInExPack](https://thunderstore.io/c/lethal-company/p/BepInEx/BepInExPack/) is the first thing you install and the thing every other mod depends on.

The install order is always the same:

1. BepInEx goes into the game folder and hooks the game on launch.
2. Mods go into `BepInEx/plugins`.
3. BepInEx loads every plugin it finds in that folder when the game starts.

Some mods also depend on other mods. MoreCompany only needs BepInEx, but plenty of bigger mods pull in shared libraries. Mod managers resolve those dependency chains for you, which is the single best reason to use one.

### Everyone In The Lobby Needs The Same Mods
This trips up more people than anything else in this guide.

Lethal Company is a co-op game, and most gameplay mods have to be installed by **every player in the lobby**, not just the host. MoreCompany is a good example: it raises the player cap, and a player without it installed will not be able to join a lobby that is using the raised cap.

The clean way to handle this is a shared profile. Thunderstore Mod Manager, Gale and r2modman can all export your mod list as a code or a file that your friends import in one click, which gets everybody onto an identical setup without anybody reading a list of thirty mod names out loud.

**TIP** - Cosmetic and client-side mods are the exception. Those only affect your own game and do not need to match.

## Picking A Mod Manager
All three of these do the same core job. Pick based on how you like your software.

| Manager | Runs on | Notes |
| ------- | ------- | ----- |
| [Thunderstore Mod Manager](https://www.overwolf.com/app/Thunderstore-Thunderstore_Mod_Manager) | Windows | Official, built on Overwolf. The most common recommendation and the one mod pages link to first. |
| [Gale](https://thunderstore.io/c/lethal-company/p/Kesomannen/GaleModManager/) | Windows, Linux | Lightweight and fast, no Overwolf account needed. A good pick if Overwolf annoys you or you are on Linux. |
| [r2modman](https://thunderstore.io/c/lethal-company/p/ebkr/r2modman/) | Windows, Linux, macOS | The original. Thunderstore Mod Manager is built on it. Still the only one of the three with a proper macOS build. |

Nexus Mods and [Vortex](https://www.nexusmods.com/about/vortex/) technically support Lethal Company, but the catalogue there is tiny compared to Thunderstore and most authors do not mirror their work. If you are looking for a specific mod, check Thunderstore first.

## Installing With Thunderstore Mod Manager
1. Download and install [Thunderstore Mod Manager](https://www.overwolf.com/app/Thunderstore-Thunderstore_Mod_Manager).
2. Open it and pick **Lethal Company** from the game list. Tick **Set as default** if this is the only game you plan to mod, which skips this screen next time.
3. Select a profile. The **Default** profile is fine to start with. Making a second profile per playthrough is worth doing once you have a few mod lists you want to keep apart.
4. Click **Get mods** in the left sidebar to browse the Thunderstore catalogue inside the app.
5. Search for **MoreCompany**, open it, and click **Download**.
6. The manager will show you a dialog listing MoreCompany's dependencies. BepInExPack will be in there. Leave everything ticked and confirm.
7. Go back to **Installed mods** and check that both MoreCompany and BepInExPack are listed and enabled.
8. Click **Start modded** at the top right.

That last step matters. **Start modded** is what actually launches the game with your profile attached. Launching Lethal Company from Steam directly starts it vanilla, with none of your mods loaded, which is the cause of about half the "my mods aren't working" posts you will ever read.

## Installing With Gale
Gale works the same way with a lighter interface.

1. Download Gale from its [Thunderstore page](https://thunderstore.io/c/lethal-company/p/Kesomannen/GaleModManager/) or its [GitHub releases](https://github.com/Kesomannen/gale/releases).
2. Launch it and choose **Lethal Company**.
3. Open the **Browse mods** tab and search for **MoreCompany**.
4. Click **Install**. Gale pulls in BepInExPack automatically as a dependency.
5. Hit **Launch game (modded)**.

Gale's profile import and export lives under the **Profile** menu, and it reads the same profile codes that Thunderstore Mod Manager produces. You and your friends can be on different managers and still share a mod list.

## Installing With r2modman
1. Grab r2modman from its [Thunderstore page](https://thunderstore.io/c/lethal-company/p/ebkr/r2modman/) or [GitHub](https://github.com/ebkr/r2modmanPlus/releases).
2. Select **Lethal Company**, then pick or create a profile.
3. Open **Online**, search for **MoreCompany** and click **Download with dependencies**.
4. Click **Start modded**.

If you are on macOS, r2modman is your only real option out of the three.

## Installing Manually
Manual installation is worth knowing even if you use a manager, because it tells you where everything actually lives and makes troubleshooting far less mysterious.

First, find your game folder. In Steam, right-click **Lethal Company** in your library, then **Manage** followed by **Browse local files**. On a default Windows install it will be here:

```
C:\Program Files (x86)\Steam\steamapps\common\Lethal Company
```

You should see `Lethal Company.exe` and a `Lethal Company_Data` folder. That is the right place.

### Installing BepInEx
1. Open the [BepInExPack page](https://thunderstore.io/c/lethal-company/p/BepInEx/BepInExPack/) on Thunderstore and click **Manual Download**.
2. Extract the zip somewhere that is **not** your game folder, such as your Downloads folder.
3. Open the extracted folder and then open the `BepInExPack` folder inside it.
4. Copy **the contents** of `BepInExPack` into your Lethal Company folder. You are copying `BepInEx`, `doorstop_config.ini` and `winhttp.dll` so they sit next to `Lethal Company.exe`.
5. Launch the game once and then close it.

**WARNING** - Copy the *contents* of `BepInExPack`, not the folder itself. If you end up with `Lethal Company\BepInExPack\BepInEx`, nothing will load. The `BepInEx` folder has to be directly inside the game folder.

That first launch is what makes BepInEx generate its folder structure, including the `BepInEx/plugins` folder you need next.

### Installing MoreCompany
1. Open the [MoreCompany page](https://thunderstore.io/c/lethal-company/p/notnotnotswipez/MoreCompany/) and click **Manual Download**.
2. Extract the zip.
3. Copy the `.dll` file into `Lethal Company\BepInEx\plugins`.

Most mods are a single `.dll` and this is all there is to it. Some ship a whole folder with assets and a config, in which case copy the entire folder into `plugins`. BepInEx searches subfolders, so either layout works.

**NOTE** - Thunderstore zips also contain `manifest.json`, `icon.png` and `README.md`. Those are packaging files for the website. They do no harm in the plugins folder, but they do nothing either.

## Installing With The TMC App
One more option, and the one closest to home: [the TMC App](https://moddingcommunity.com/tmc-app) is our own mod manager and server browser. Its **sandboxes** are the same idea as the profiles above, named mod lists per game with their own load order and deployment method, and switching between them re-downloads nothing.

**Lethal Company is not in its supported games list yet.** Adding a game to the app is four JSON files rather than any code, so it is not a big job, and it is on our list.

It is worth being straight with you about where the app is, though. **It is in very early development.** Its own README says as much: much of it is only partially tested, and right now it is something to try alongside a Thunderstore manager rather than instead of one. If you do give it a go, that genuinely helps us, and telling us what broke helps more.

The app is **open source** under GPL-3.0 at [github.com/modcommunity/tmc-app](https://github.com/modcommunity/tmc-app). Bug reports and feature requests are very welcome in [the issue tracker](https://github.com/modcommunity/tmc-app/issues), pull requests even more so, and the repository documents the per-game format if you fancy adding Lethal Company support yourself.

Installing it:

* **Linux**: one line, no root and no package manager.

```bash
curl -fsSL https://raw.githubusercontent.com/modcommunity/tmc-app/main/scripts/install.sh | sh
```

* **Windows**: the `setup.exe` or `setup.msi` from the [releases page](https://github.com/modcommunity/tmc-app/releases). There is a portable build too, though it does not register the launcher entry or the `tmc://` link handler.
* **macOS**: the `.dmg` from the same releases page.

## Checking Your Mods Loaded
BepInEx opens a console window alongside the game by default. Watch it while the game boots and you will see a line for the loader itself and then one line per plugin, something like:

```
[Info   :   BepInEx] Loading [MoreCompany 1.14.0]
```

If the console never appears, BepInEx is not loading at all, which usually means the files ended up in the wrong folder or you launched from Steam instead of through your mod manager.

For MoreCompany specifically, the check is easy. Start a lobby and look at the player slots on the ship monitor. Vanilla caps you at four, and with MoreCompany installed you will see more.

## Updating And Removing Mods
Mod managers make this trivial. Every one of the three flags outdated mods in your installed list and updates them in a click, and uninstalling removes the mod's files without touching anything else.

Doing it by hand means deleting the `.dll` or folder out of `BepInEx/plugins`. To strip everything back to vanilla, delete the `BepInEx` folder, `doorstop_config.ini` and `winhttp.dll` from the game folder. Steam's **Verify integrity of game files** will not do this for you, since those files are not part of the game and Steam does not know they exist.

**TIP** - Lethal Company updates regularly, and a game update will usually break BepInEx mods until authors catch up. If everything stops working the day after a patch, that is why. Give it a few days.

## Troubleshooting
**The game launches but no mods are loaded.** You almost certainly launched from Steam. Use **Start modded** in your mod manager instead.

**No BepInEx console window.** BepInEx is not installed correctly. Check that `winhttp.dll` and `doorstop_config.ini` sit directly next to `Lethal Company.exe`, not in a subfolder.

**The game crashes on the loading screen.** Usually a mod conflict or a mod built for an older game version. Disable mods in halves to narrow down which one is at fault rather than removing them one at a time.

**I can't join my friend's lobby.** Your mod lists do not match. Have the host export their profile and import it on your end.

**Mods work in singleplayer but not in multiplayer.** Some mods have to be installed by the host to take effect at all. Check the mod's Thunderstore page, which normally says whether it is host-only, client-side or required by everyone.

**Linux and Proton.** BepInEx needs a DLL override to load under Proton. Set your Steam launch options for Lethal Company to `WINEDLLOVERRIDES="winhttp=n,b" %command%`. Gale and r2modman both handle this themselves when you launch through them.

## Conclusion
The short version: install a mod manager, let it pull in BepInEx for you, and launch the game through the manager rather than through Steam. That covers the vast majority of Lethal Company mod installs.

The one thing genuinely worth the extra effort is sharing a profile with the people you play with. It takes a minute and it saves an evening of comparing mod lists in Discord.

If you want to help with something, the [TMC App](https://github.com/modcommunity/tmc-app) is open source and in early development, and feedback on it is worth a lot to us right now.

## See Also
* [Lethal Company on Thunderstore](https://thunderstore.io/c/lethal-company/)
* [Lethal Company Modding Discord](https://discord.gg/XeyYqRdRGC)
* [Lethal Company Modding Wiki](https://lethal.wiki/)
* [BepInEx documentation](https://docs.bepinex.dev/)
* [TMC App](https://github.com/modcommunity/tmc-app)

This guide is kept up-to-date as much as we can manage, but games, mod loaders and mod managers all move quickly. If you find an instruction that no longer matches what you are seeing, please report it or open a [pull request](https://github.com/modcommunity/how-to-install-mods-in-lethal-company/pulls) on this guide's GitHub repository.

Join our [Discord server](https://discord.moddingcommunity.com) if you have any questions or want a hand with anything modding related!
