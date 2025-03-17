# Proton with Wayland

I've built these with Tk-Glitch's Wine/Proton [here](https://github.com/Frogging-Family/wine-tkg-git), and wish to provide an easier way to access them. I'll split them out between Steam and Lutris use cases, and provide the current configs I'm using as to improve them further, and if there is an interest, should be able to create specific ones if needed. This is using Wine Expirimental, so it is at the absolute edge in terms of what's available, but I've had some good results, so wish to share them.

I will only be providing the relavent configs that I've adjusted in this repo, and releases as I make them. This is to provide transparancy and allow others to review my adjustments to recommend improvements, or make suggestions for specific use case builds, or make builds themselves. 

As there seems to be some confusion, likely due to my wording, these are mainly proof of concept builds, and painfully bleeding edge. There is no guarantee of anything working, no guarantee that I can fix anything, and likely the vast majority will be "as is" with very little I can tweak as most proton patches will not be able to be applied to these builds which are needed for a wide variety of compatibility.

# How to install

For the steam ones, they go in\
`/home/user/.local/share/Steam/compatibilitytools.d`\
For the Lutris ones, they go in\
`/home/user/.local/share/lutris/runners/wine/`

Simply extract the .tar.gz's in their respective folders, you can delete them at this point, then if either Lutris or Steam is running, shut them down and start them up, and they should be available to select.

# Warnings

These builds are technically worse than alpha, and they are customized, do not report any issues to Wine, or TKG. Some issues may be unresolvable, and there will be a few oddities here and there.

# The Edit I don't know how to provide
Because TKG's script is quite extensive, I needed to slot in a way to apply the registry edit during initial prefix generation, so that the registry is updated within the build. The edit looks like this
```
# Apply Wayland registry settings
echo "Applying Wayland registry settings..."
WINEPREFIX="$_nowhere/proton_tkg_$_protontkg_version/files/share/default_pfx" "$_nowhere/proton_tkg_$_protontkg_version/files/bin/wine" regedit /s "$_nowhere/proton-tkg-userpatches/wayland.reg" >>"$_logdir"/proton-tkg.log 2>&1

# default prefix
echo ''
echo "Generating default prefix..."
python3 "$_nowhere"/proton_template/default_pfx.py "$_nowhere/proton_tkg_$_protontkg_version/files/share/default_pfx" "$_nowhere/proton_tkg_$_protontkg_version/files" >>"$_logdir"/proton-tkg.log 2>&1

wine_is_running
```

This is likely the best way I'm going to be able to show you how this is done, as the line this edit occurs changes quite frequently. The wayland.reg goes into the user patches, and I apply it to the existing prefix using this edit.
