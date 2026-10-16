TerraTech Legion Survive Save/Continue v0.5.9

An unofficial Windows mod that adds persistent save and load functionality to Survive mode in TerraTech Legion.

Normally, Survive runs must be completed in a single session. This mod lets you save your progress, exit the game, and return later. You can also load an earlier checkpoint or start a completely new run using a previously saved Tech.

Features

Save your run: Press F8 during supported gameplay to create a checkpoint.

Continue Latest: Resume your most recently saved run, including your Tech and progression.

Continue an earlier save: Select a previous saved run or checkpoint instead of your latest save.

Start fresh with a saved Tech: Begin a new Survive run using a Tech from an existing save, without restoring that run's progression, resources, or encounter history.

Preserve your progress: Restore your Tech, elapsed time, level, partial XP, score, rerolls, encounter scheduling, boss history, loose inventory, collected unopened crates, earned reward opportunities, and banned-block state.

Save again after continuing: Continue playing, create additional checkpoints, and resume across multiple sessions.

Saved checkpoints are preserved rather than overwritten when creating new saves.

Important disclaimer

This is an unofficial hobby mod. It works on my PC, but I haven't tested it on other computers or game versions. It may stop working after game updates. Back up your files before installing. Install and use at your own risk. No compatibility guarantees or ongoing support are promised.

The mod is locked to the TerraTech Legion executable with SHA-256:

4F592D0D111C85A923DB2A38A5558A436595B7498D60E7AAA510B42FBEFF35E6

The installer refuses other builds instead of attempting an unsafe installation.

Required dependency: UE4SS

UE4SS is a separate modding framework. It is not part of TerraTech Legion and is not included in this ZIP.

Download and install UE4SS before installing this mod:

https://github.com/UE4SS-RE/RE-UE4SS/releases/

This mod was tested with UE4SS reporting v3.0.1 Beta #0, Git SHA f58e8f84. Other UE4SS versions have not been tested.

UE4SS must be installed in TerraTech Legion's:

TerraTech_Legion\Binaries\Win64

The installation must provide:

ue4ss\Mods\mods.txt

Follow UE4SS's own installation instructions. UE4SS and TerraTech Legion are not redistributed by this package.

Back up first

Close TerraTech Legion. Back up these locations if they exist:

Saved runs and checkpoints

%LOCALAPPDATA%\TerraTech_Legion\LegionSuspendContinue

Existing mod installation

<TerraTech Legion>\TerraTech_Legion\Binaries\Win64\ue4ss\Mods\LegionSurviveResume

The installer also creates a transactional backup of any replaced LegionSurviveResume installation. It does not delete saved runs.

Install

Install UE4SS and confirm ue4ss\Mods\mods.txt exists.

Extract the entire Save/Continue ZIP to a normal folder. Do not run scripts directly from inside the ZIP viewer.

Close TerraTech Legion.

Open PowerShell in the extracted TerraTech-Legion-Survive-Save-Continue-v0.5.8 folder.

Verify the downloaded package:

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Verify-Package.ps1"

Install the mod:

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Install-LegionSurviveResume.ps1"

The installer searches the normal Steam installation and all Steam libraries listed in libraryfolders.vdf.

If automatic discovery fails, specify the TerraTech Legion installation directory:

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Install-LegionSurviveResume.ps1" -GameDirectory "D:\SteamLibrary\steamapps\common\TerraTech Legion"

Replace the example path with your own Steam library location.

If another version is already installed

The installer refuses to overwrite an existing LegionSurviveResume folder unless explicitly authorized.

You can either uninstall the previous version using its own uninstaller or install with transactional replacement:

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Install-LegionSurviveResume.ps1" -ReplaceExisting

-ReplaceExisting backs up the previous mod and mods.txt before replacing them. If installation or validation fails, the transaction rolls back.

Using the mod

Save a Survive run

Play Survive normally.

Leave shop and modification screens and wait until normal gameplay is active.

Press F8 once.

Wait for the Run Saved confirmation.

The mod creates an immutable checkpoint containing the current supported run state.

If saving would produce an inconsistent checkpoint—for example, during certain boss encounters, transitions, or restoration—the mod refuses the request rather than publishing a partial save.

Checkpoints are stored at:

%LOCALAPPDATA%\TerraTech_Legion\LegionSuspendContinue

Continue your latest run

Start the normal Survive flow.

Select the same Pilot, World, and difficulty as the saved run.

Choose Continue Latest from the mod's Run Menu.

Your saved Tech will appear first, followed by restoration of the run's progression and resources.

A brief pause may occur during restoration. Do not press F8 until restoration is complete.

Continue an earlier saved run

You aren't limited to your most recent checkpoint.

Use the mod's Run Menu to select an existing saved run or earlier checkpoint and resume from that point.

This restores the selected checkpoint's Tech and saved run state rather than the most recent save.

Select the appropriate Pilot, World, and difficulty for that saved run.

Start a new run with a saved Tech

The mod also lets you use a Tech from a previous save as the starting vehicle for a new Survive run.

Choose the saved-Tech/new-run option from the mod's Run Menu and select the desired Tech.

This is not the same as continuing a saved run. You begin with fresh progression and encounter history rather than carrying over the previous run's elapsed time, level, XP, score, inventory, or rewards.

This is useful if you want to try a different strategy or restart Survive without rebuilding your Tech from scratch.

Uninstall

Close TerraTech Legion, then run this command from the extracted mod folder:

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Uninstall-LegionSurviveResume.ps1"

The uninstaller validates the installed immutable files and exact backup before changing anything. It restores the pre-install mod and mods.txt transactionally.

Known runtime state such as inventory-mode.txt is handled separately. Unexpected modifications to executable or script files cause the uninstaller to refuse safely.

Saved runs and checkpoints are intentionally retained.

If you want to remove your saved runs, back them up and delete them manually only after confirming you no longer need them.

Known limitations

Tested on one Windows PC and one specific TerraTech Legion executable build.

Tested with one UE4SS v3.0.1-compatible build; other UE4SS versions are unverified.

Game or UE4SS updates can break native hooks and signatures. The mod should refuse unsupported game executable builds.

Saved runs are scoped to their Pilot, World, and difficulty.

Continue reconstruction may cause a visible pause.

Banned-block identities and native activation are persisted and verified, but actual post-Continue shop choices were not separately recorded during testing.

Natural early crate-type generation may occur before the game's applicable block-selection ban map is initialized.

Saving may be unavailable during boss encounters, shop interactions, certain transitions, or while Continue restoration is incomplete.

Package contents

Mod\LegionSurviveResume\ — exact tested 0.5.8 gameplay payload

Install-LegionSurviveResume.ps1 — transactional portable installer

Uninstall-LegionSurviveResume.ps1 — transactional rollback/uninstaller

Verify-Package.ps1 — offline payload verification

package-manifest.json — runtime hashes and supported executable hash

THIRD-PARTY-NOTICES.md — dependency information

SHA256SUMS.txt — hashes of distributable files

Support expectations

This is shared as a hobby project without compatibility guarantees or promised maintenance.

If you report a problem, please include your exact TerraTech Legion game version, UE4SS version, and relevant logs.

The mod is provided as-is for other players who may find it useful.
