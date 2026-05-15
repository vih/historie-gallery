export PATH=~/.npm-global/bin:$PATH
source ~/.profile  # or source ~/.bashrc

## Hack for at thumbsup kan vise title

exiftool -r -ImageDescription= \
         '-ImageDescription<BaseName' \
         '-ImageDescription<${BaseName}: ${XMP-dc:Title}' \
         '-UserComment<XMP-dc:Description' \
         '-Artist<Source' \
         -overwrite_original "images"

thumbsup --config config.json