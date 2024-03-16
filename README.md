# Color Deducto Activity Flatpak

Color Deducto is a learning activity to help children learn the art of
inductive logic through pattern recognition.

To know more refer https://github.com/sugarlabs/colordeducto

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.ColorDeducto.git
cd org.sugarlabs.ColorDeducto
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.ColorDeducto.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.ColorDeducto
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.ColorDeducto.json
```