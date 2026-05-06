# rblx_game_asset_downloader
this is a downloader so you can easily download game assets from a rblx game file into obj files with image files and mtl files.

## features
here are some features that are neat for downloading these games:
- note all downloads are in a primary folder ( the place file's name ) with these file folders inside: `meshes`, `sounds`, `animations`, `textures`.
### meshes
all meshes are downloaded with the texture belonging with it and the mtl file. their name is the mesh's name in the game or the
marketplace and is lowercase and under snake_case with a primary folder with the mesh's name. meshes are always an obj.
#### models
* models are a file folder when downloading, so if a mesh part is under a model there will be a folder with the model's name
  and the mesh inside it. this can stack with multiple models inside each other.
* if a model with the property tag 'downloadable_model', it will convert the model into like a combined obj with every mesh, model, or part inside. to set this tag just add a StringValue inside the model named 'downloadable_model' and the downloader will see it.
#### parts
* parts can be downloadable with the property tag 'downloadable_part', doing the same as models when download but converts it into a obj to be able to download. just add a StringValue inside the part named 'downloadable_part'.
* when converting a part into a obj it will download the material texture ( that is built into the game ) with the part's color.
### audios
audios are downloaded with the name from the game or the marketplace as an ogg or an mp3.
* also note: they are extracted from scripts and anything that is a sound file.
### texture
any texture in the game but not the mesh's texture. they are a `.png` file
* note: like audios, they can be extracted from scripts or anything that is an image file.
### animations
animations are downloaded as `.rbxm` files from the game file. the downloader will extract any AnimationTrack or Keyframe data and export them.
* note: animations are extracted from the place file's internal asset storage.

## usage
yes you just need the place file! just run the downloader with your `.rbxlx` file and it will download everything for you. i do recommend to use it a simpler way though - make a new roblox place with the assets you want to download 
inside without the baseplate and the spawn point. make sure the files are organized in folders so the downloader respects the hierarchy. or if you just want to be lazy, just download it in the `.rbxlx` file format and just put it in ( only for people like me that are lazy 🙄 )

important notes to remember:
 - it can only work with .rbxlx files
 - you might have to use your .ROBLOSECURITY cookie 🍪, i do recommend if you don't want to use your cookie just use an alt account.
 - organize your place file in folders first for best results, like: Folder > Model > MeshPart

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
    car_drive.mp3
  animations/
    walk.rbxm
  textures/
    metal.png
```

example place file organization ( before downloading ):
```
Workspace
  Tesla ( Folder )
    Wheel ( Model )
      MeshPart
        SpecialMesh
```

longer one ( sorry 😢 ):
```
my_game_place/
├── meshes/
│   ├── tesla/
│   │   ├── wheel_front/
│   │   │   ├── wheel_front.obj
│   │   │   ├── wheel_front.mtl
│   │   │   └── wheel_front.png
│   │   ├── wheel_back/
│   │   │   ├── wheel_back.obj
│   │   │   ├── wheel_back.mtl
│   │   │   └── wheel_back.png
│   │   └── body/
│   │       └── car_body/
│   │           ├── car_body.obj
│   │           ├── car_body.mtl
│   │           └── car_body.png
│   └── trees/
│       └── tree1/
│           ├── trunk/
│           │   ├── trunk.obj
│           │   ├── trunk.mtl
│           │   └── trunk.png
│           └── leaves/
│               ├── leaves.obj
│               ├── leaves.mtl
│               ├── leaves.png
│               └── part_color.json
├── sounds/
│   └── background_music.mp3
├── textures/
│   └── metal_texture.png
└── download_log.json
```

example place file organization ( before downloading ):
```
Workspace
  Tesla ( Model )
    Wheel_Front ( MeshPart )
    Wheel_Back ( MeshPart )
    Body ( Model )
      CarBody ( MeshPart )
  Trees ( Folder )
    Tree1 ( Model )
      Trunk ( MeshPart )
      Leaves ( MeshPart with downloadable_part tag )
  BackgroundMusic ( Sound )
  MetalTexture ( Texture in ReplicatedStorage )
```

## download_log.json example
the downloader saves a log file so you can track what was downloaded and avoid duplicate downloads. each asset is stored with its roblox id so the downloader can check if it already downloaded it before:

```json
{
  "place_file": "my_game_place.rbxlx",
  "timestamp": "2026-05-06T21:45:30Z",
  "total_downloaded": {
    "meshes": 3,
    "textures": 1,
    "sounds": 1,
    "animations": 0
  },
  "meshes": [ 12345678, 12345679, 12345680 ],
  "sounds": [ 11111111 ],
  "textures": [ 99999999 ],
  "animations": [ 88888888 ]
}
```

the downloader will check these lists and only download assets that are not already in the log. this way if you run it again it wont download the same stuff twice.

## how to use
1. create a place file with your assets organized in folders/models
2. run the downloader: `python3 game_asset_downloader.py your_place_file.rbxlx`
3. wait for it to finish downloading
4. check the output folder with your downloaded assets!

optional: set your .ROBLOSECURITY cookie if you need to download private textures
```bash
export ROBLOSECURITY="_|WARNING:-DO-NOT-SHARE-THIS..."
python3 game_asset_downloader.py your_place_file.rbxlx
```

## security
yes i am a good person and will not steal your data, this just downloads assets from your game file and uses roblox's api to
download the assets. nothing is sent anywhere except to roblox's cdn servers.

## next updates
maybe something like this [link](https://github.com/clay-rip/robloxAssetDownloader) to redirect you to another developer doing the same. add features like batch downloading multiple place files or converting to other formats like gltf.
