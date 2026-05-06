# rblx_game_asset_downloader
this is a download so you can easily download game assets from a rblx game file into a obj with image files a mtl files.

## features
here are some features that are neat for downloading these games:
- note all downloads are under a a primary folder with the type these are `meshes`, `sounds`, `animations`, `textures`
- the primary folder is where all of the main catorgeory's downloads are.
### meshes
all meshes are downloaded with the texture belonging with it and the mtl file. their name is the meshe's name in the game or the
marketplace and is lowercase and under snake_case with a primary folder with the mesh's name. meshes are always an obj.
#### models
* models are file folders so if a mesh part is under a model there will be a folder with the model's name
  and the mesh. this can stack.
* if a model with the property tag 'downloadable_model', doing the same as meshes when download but with everything under it.
#### parts
* parts can be downloadable with the property tag 'downloadable_part', doing the same as meshes when download but convert's it into a mesh
### audios
audios are downloaded with the name from the game or the marketplace as an ogg or an mp3.
* also note: they are extracted from scripts and anything that is a sound file.
### texture
any texture in the game but not the mesh's texture. they are a `.png` file
* note: like audios, they can be extracted from scripts or anything that is an image file.
### animations
i dont know about animations in a game but i will think of this later

## usage
i do reconmend to use it a simpler way. a new roblox place with the assets you want to download 
inside without the baseplate and the spawn point. make sure the files are organised.

important notes to remember:
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
