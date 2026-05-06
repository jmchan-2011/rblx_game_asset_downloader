# rblx_game_asset_downloader
this is a download so you can easily download game assets from a rblx game file into a obj with image files a mtl files.

## usage
i do reconmend to use it a simpler way. a new roblox place with the assets you want to download 
inside without the baseplate and the spawn point. make sure the files are organised.

important notes to remeber:
 - it will only make folders if the mesh is in a model or a folder
 - all image files will be an png, meshes will be a obj, sounds will be a mp3.
 - it can only work with .rblxlx
 - you might have to use your .ROBLOSECURITY cookie 🍪, i do reconmened if you dont want to use your cookie just use an alt.

example file layout of the asset downloader:
```
your_place_file_name_here/
  meshes/
    tesla/
      wheel/
        wheel.obj
        wheel.png
        wheel.mtl
  sounds/
    car_drive.mp4
```

## security
yes i am a good person and will not steal your data, this just downloads assets from your game file and uses roblox's api to
download the assets.

## next updates
maybe somthing like this [link](https://github.com/clay-rip/robloxAssetDownloader) to redirect you to another developer doing the same and ask Claude to make one like the same for yours's. add features like animation downloads ( really don't know how to do that but the download does ), sounds, part downloading, texture / images, and update meshes so they can download textures inside of the mesh's properties. also maybe make it so parts can download the material and the color if needed. parts will have to have a tag ( downloadable_part ) inside of it's properties as well to download models a tag ( downloadable_model ) will turn it into a mesh and download it as an obj like a part with each of the colors and materials.
