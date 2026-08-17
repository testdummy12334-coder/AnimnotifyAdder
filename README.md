AnimNotify Transfer Tool
A standalone C# / .NET Windows Forms tool designed to automate transferring and managing AnimNotify and AnimNotifyState (ANS_) assets between Unreal Engine animation sequence files (.uasset / .uexp).

What's New in This Update
Custom Placement and Fallback Timing: Added bidirectional timing controls (Seconds / Frame) driven by automatically detected animation frame rates. Enable "Use Original Time" to retain exact native timestamps, or uncheck it to position a notify at a custom frame or second.

Dedicated Remove Notifies Tab: Added a third tab to inspect all notifies currently inside the loaded target asset. Supports multi-selection to delete specific notifies or wipe the entire track cleanly.

In-Place File Overwrite with Automated Backups: Assets overwrite directly in-place without generating extra _Modified duplicate files. Safety backups are generated automatically:

.uasset.og / .uexp.og: Created once as a permanent copy of the original unmodified asset.

.uasset.bak / .uexp.bak: Overwritten on each save to capture the most recent working state.

Name Map Serialization Fix: Fully resolved the Attempt to add name to name map during serialization crash by pre-registering property types and source name references before saving.

AnimNotifyState and Repeated Notify Detection: Fixed parsing logic to detect and list every single notify instance, duration-based states, and repeated notifies accurately.

Clear Asset Buttons: Added dedicated "Clear" buttons beside each drop zone to unload assets and reset UI listboxes instantly.

Features
Multi-Version Support: Compatible with assets from Unreal Engine 4.24 up through Unreal Engine 5.4.

Multi-Selection: Supports Shift-Click and Ctrl-Click to transfer or remove multiple notifies in batches.

ANS / Attack-Cancel Matching: Automatically matches and synchronizes Class and Template import index numbers to existing notify structures within the target file.

Projectile Mode: Dedicated tab configured to duplicate and mirror structural import chains for projectile notify templates.

Clean Binary Footprint: Generates exports with sanitized dependency arrays (CreateBeforeSerializationDependencies, etc.) to prevent engine crashes.

How to Use
1. Load Assets
Select the correct Engine Version from the top dropdown menu.

Drag and drop your Source Animation (.uasset) into the Source drop panel.

Drag and drop your Target Animation (.uasset) into the Target drop panel.

2. Transfer Notifies
Standard Notifies:

Open the Standard / General Notifies tab.

Select one or more notifies from the source list.

Leave Use Original Time checked to preserve exact source timestamps, or uncheck it to type a specific Second / Frame.

Optionally check Enable ANS / Attack Cancel Import Matching if transferring combat/duration notifies into an asset with existing setups.

Click Transfer Selected Notify(ies) or Transfer ALL Notifies.

Projectile Mode:

Open the Projectile Mode tab.

Select the projectile notify template detected from the source.

Adjust the timing or leave it on original timing.

Click Transfer Projectile Notify.

3. Remove Notifies
Open the Remove Notifies tab.

Select one or more notifies from the target list.

Click Remove Selected Notify(ies), or click Clear ALL Notifies to wipe the entire track.
