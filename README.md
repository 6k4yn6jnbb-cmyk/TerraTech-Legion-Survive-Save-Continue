TerraTech Legion Survive Save/Continue v0.6.4

Save Survive runs with F8, Continue Latest or an earlier checkpoint, or start a fresh run with a saved Tech. This release supersedes v0.5.9.

## Changes

- Banned-block and tag row names now use Unreal FName-style ASCII case-insensitive comparison. Stable block GUID remains authoritative. Case-only differences such as `HWK_Sniper_marksman` / `HWK_Sniper_Marksman` resolve without rewriting saved spelling. Missing identities, genuine conflicts and ambiguous matches still fail before mutation.
- Includes the intervening inventory GUID/FName identity fixes, corrected MasterBlockTable traversal, and optional cumulative run-summary statistics. Legacy checkpoints remain supported; unavailable historical statistics are not fabricated.

## Validation and limits

- October 26, 2026 acceptance: Tech, progression and inventory Continue passed; F8 checkpoint publication passed; staged ban persistence passed.
- The latest session committed core restoration with 16 coordinator events, staged 57 banned blocks / 8 tags, and saved them with `PASS:STAGED_PENDING_PRESERVED blocks=57 tags=8`.
- Native activation of those 57 bans was **not exercised**: the session never reached an applicable reward-selection/shop constructor. No ban terminal/refusal event occurred. This is neither a demonstrated activation success nor evidence of a runtime ban-restoration defect. An earlier 0.6.1 trace successfully activated 56 blocks / 8 tags; that is separate evidence.
- All 275 pre-existing checkpoint-owned files matched their recorded hashes. Two new five-file checkpoint packages were created. The latest checkpoint held level 33 and loose inventory of 19 identities / total quantity 33.
- The separately reported driver issue is outside this mod's acceptance verdict. This release does not claim to fix it or establish its cause.
- Tested on one Windows PC and one exact game executable; other builds and machines are unverified. Visible post-Continue filtering for the latest 57-ban state remains unverified.

## Installation

Requires Windows, TerraTech Legion and UE4SS installed separately. Extract the entire ZIP, close the game, open PowerShell in the extracted folder, and run:

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Verify-Package.ps1"
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Install-LegionSurviveResume.ps1"
```

For an existing mod, add `-ReplaceExisting`; it backs up and replaces the prior mod transactionally. If automatic Steam discovery fails, add `-GameDirectory "D:\SteamLibrary\steamapps\common\TerraTech Legion"` using your own path. See README.md for backup, usage and uninstall instructions. UE4SS and game files are not included.

Unofficial hobby mod, supplied as-is without compatibility guarantees or promised ongoing support. Back up your saved runs before installing.

This is shared as a hobby project without compatibility guarantees or promised maintenance.

If you report a problem, please include your exact TerraTech Legion game version, UE4SS version, and relevant logs.

The mod is provided as-is for other players who may find it useful.
