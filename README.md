# Proton with Wayland

I've built these with Tk-Glitch's Wine/Proton-tkg [here](https://github.com/Frogging-Family/wine-tkg-git), and wish to provide an easier way to access them. I'll split them out between Steam and Lutris use cases, and provide the current configs I'm using as to improve them further, and if there is an interest, should be able to create specific ones if needed. This is using Wine 9.0, so it is at the absolute edge in terms of what's available, but I've had some good results, so wish to share them.

I will only be providing the relavent configs that I've adjusted in this repo, and releases as I make them. This is to provide transparancy and allow others to review my adjustments to recommend improvements, or make suggestions for specific use case builds, or make builds themselves.

# How to install

For the steam ones, they go in\
`/home/user/.local/share/Steam/compatibilitytools.d`\
For the Lutris ones, they go in\
`/home/user/.local/share/lutris/runners/wine/`

Simply extract the .tar.gz's in their respective folders, you can delete them at this point, then if either Lutris or Steam is running, shut them down and start them up, and they should be available to select.

# Warnings

These builds are technically worse than alpha, and they are customized, do not report any issues to Wine, or TKG. Some issues my be unresolvable, and there will be a few oddities here and there.
