Icons generated by http://android-ui-utils.googlecode.com/hg/asset-studio/dist/icons-launcher.html

To create new icons use the following settings: 

Settings: Color 100%
Scaling: Center
Shape: Bevel
Background: White 
Padding: 5%
Trim: True
Color: #1e1c1c

In order to generate gray icons, you can use the following URL directly:

http://romannurik.github.io/AndroidAssetStudio/icons-launcher.html#foreground.type=image&foreground.space.trim=1&foreground.space.pad=0.05&foreColor=8a8e90%2C100&crop=0&backgroundShape=bevel&backColor=ffffff%2C100&effects=none

The code below was used in order to automatically process the downloaded icons and copy them to the res/ directory:

```
for i in `ls -1`; do
  cd $i
  for dir in `ls -1`; do mv $dir `echo $dir | sed 's:mipmap:drawable:g'`; done
  for file in `find -name *.png`; do mv $file `echo $file | sed "s:ic_launcher:${PWD##*/}:g"`; done
  cp -R * ../../res/
  cd ..
done
```
