Objects can be spawned by any script using the [spawnObject()](base#spawnobject) function. These are the `type` Strings used to designate the type of Object to spawn. 

##Built-in Game Objects

###Boards


* backgammon_board
* CardBot_Board
* Checker_Board
* Chess_Board
* Chinese_Checkers_Board
* Go_Board
* Pachisi_Board
* reversi_board

###Containers

* Bag
* Bowl
* Cup
* go_game_bowl_black
* go_game_bowl_white
* Infinite_Bag

###Figurines

* Figurine_Card_Bot
* Figurine_Kimi_Kat
* Figurine_Knil
* Figurine_Mara
* Figurine_Sir_Loin
* Figurine_Zeke
* Figurine_Zomblor

###Game Pieces

* backgammon_piece_brown
* backgammon_piece_white
* BlockRectangle
* BlockSquare
* BlockTriangle
* Card
* Checker_black
* Checker_red
* Checker_white
* Chess_Bishop
* Chess_King
* Chess_Knight
* Chess_Pawn
* Chess_Queen
* Chess_Rook
* Chinese_Checkers_Piece
* Chip_10
* Chip_50
* Chip_100
* Chip_500
* Chip_1000
* Deck
* Die_4
* Die_6
* Die_6_Rounded
* Die_8
* Die_10
* Die_12
* Die_20
* Die_Piecepack
* Domino
* go_game_piece_black
* go_game_piece_white
* Mahjong_Coin
* Mahjong_Stick
* Mahjong_Tile
* Metal Ball
* PiecePack_Arms
* PiecePack_Crowns
* PiecePack_Moons
* PiecePack_Suns
* PlayerPawn
* Quarter
* reversi_chip

###RPG Figurines

* rpg_BARGHEST
* rpg_BASILISK
* rpg_BEAR
* rpg_BLACK_DRAGON
* rpg_CENTAUR
* rpg_CERBERUS
* rpg_CHIMERA
* rpg_CRASC
* rpg_CYCLOP
* rpg_DARKNESS_WARLORD
* rpg_DRAGONIDE
* rpg_EVIL_WATCHER
* rpg_GHOUL
* rpg_GIANT_VIPER
* rpg_GOBLIN
* rpg_GOLEM
* rpg_GRIFFON
* rpg_HYDRA
* rpg_KNIGHT
* rpg_KOBOLD
* rpg_LIZARD_WARRIOR
* rpg_MAGE
* rpg_MANTICORA
* rpg_MUMMY
* rpg_OGRE
* rpg_ORC
* rpg_RANGER
* rpg_RAT
* rpg_SKELETON_KNIGHT
* rpg_TEMPLATE
* rpg_THIEF
* rpg_TREE_ENT
* rpg_TROLL
* rpg_VAMPIRE
* rpg_WARRIOR
* rpg_WEREWOLF
* rpg_WYVERN

###Tilesets

* Tileset_Barrel
* Tileset_Chair
* Tileset_Chest
* Tileset_Corner
* Tileset_Floor
* Tileset_Rock
* Tileset_Table
* Tileset_Tree
* Tileset_Wall

###Tools

* Calculator
* Counter
* Digital_Clock
* Notecard
* Tablet

###Triggers

* ScriptingTrigger
    * A Scripting Zone, a zone used for scripting
* FogOfWarTrigger
    * A [Hidden Zone](http://berserk-games.com/knowledgebase/hidden-zones-2/)

###Other

* 3DText
    * The text that the [Text Tool](http://berserk-games.com/knowledgebase/1958/) spawns.

---



##Custom Game Objects
You can also spawn [custom Objects](http://berserk-games.com/knowledgebase_category/custom-content/) and then provide the custom content for them after spawning them by calling [setCustomObject()](object#setcustomobject). *(See setCustomObject for usage)*

You can also use setCustomObject along with [reload()](object#reload) to modify an existing custom Object.

###Custom AssetBundle

* Custom_AssetBundle
            
!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.
        * **assetbundle**: The path/url for the AssetBundle. 
        * **assetbundle_secondary**: The path/url for the secondary AssetBundle property. 
            * {>>Optional, is not used by default.<<}
        * **type**: An Int representing the Object's type.
            * {>>Optional, defaults to 0.<<}
            * **0**: Generic
            * **1**: Figurine
            * **2**: Dice
            * **3**: Coin
            * **4**: Board
            * **5**: Chip
            * **6**: Bag
            * **7**: Infinite bag
        * **material**: An Int representing the Object's material.
            * {>>Optional, defaults to 0.<<}
            * **0**: Plastic
            * **1**: Wood
            * **2**: Metal
            * **3**: Cardboard



###Custom Board

* Custom_Board

!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.
        * **image**: The path/url for the board.
   


###Custom Dice

* Custom_Dice

!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.
        * **image**: The path/url for the [custom die](http://berserk-games.com/knowledgebase/custom-dice/).
        * **type**: The type of die, which determines its number of sides.
            * {>>Optional, defaults to 1.<<}
            * **0**: 4-sided
            * **1**: 6-sided
            * **2**: 8-sided
            * **3**: 10-sided
            * **4**: 12-sided
            * **5**: 20-sided



###Custom Figurine

* Figurine_Custom

!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.
        * **image**: The path/url for the [custom figurine](http://berserk-games.com/knowledgebase/custom-figurines/).
        * **image_secondary**: The path/url for the custom figurine's back.
            * {>>Optional, defaults to "image".<<}



###Custom Model

* Custom_Model

!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.
        * **mesh**: The path/url for the .obj mesh used on the [custom model](http://berserk-games.com/knowledgebase/custom-models/).
        * **diffuse**: The path/url for the diffuse image.
        * **normal**: The path/url for the normals image.
            * {>>Optional, is not used by default.<<}
        * **collider**: The path/url for the collider mesh.
            * {>>Optional, defaults to a generic box collider.<<}
        * **convex**: If the object model is convex.
            * {>>Optional, defaults to false.<<}
        * **type**: An Int representing the Object's type.
            * {>>Optional, defaults to 0.<<}
            * **0**: Generic
            * **1**: Figurine
            * **2**: Dice
            * **3**: Coin
            * **4**: Board
            * **5**: Chip
            * **6**: Bag
            * **7**: Infinite bag
        * **material**: An Int representing the Object's material.
            * {>>Optional, defaults to 0.<<}
            * **0**: Plastic
            * **1**: Wood
            * **2**: Metal
            * **3**: Cardboard
        * **specular_intensity**: The specular intensity.
            * {>>Optional, defaults to 0.1.<<}
        * **specular_color**: The specular Color.
            * {>>Optional, defaults to {r=1, g=1, b=1}.<<}
        * **specular_sharpness**: The specular sharpness.
            * {>>Optional, defaults to 3.<<}
        * **freshnel_strength**: The freshnel strength.
            * {>>Optional, defaults to 0.1.<<}
        * **cast_shadows**: If the Object casts shadows.
            * {>>Optional, defaults to true.<<}



###Custom Tile

* Custom_Tile

!!!info "Custom Parameters"
    * **parameters**: A Table of parameters which determine the properties of the Object.



###Custom Token





* [<span class="ico_tab"></span>](typeandclass) **parameters**: Test of this feature.
* [<span class="ico_str"></span>](typeandclass) **image**: Test of this feature.
* [<span class="ico_int"></span>](typeandclass) **material**: Test of this feature.
* [<span class="ico_flo"></span>](typeandclass) **specular**: Test of this feature.
* [<span class="ico_nil"></span>](typeandclass) **nil**: Test of this feature.
* [<span class="ico_boo"></span>](typeandclass) **bool**: Test of this feature.





* Custom_Token

!!!info "Custom Parameters"
   * **parameters**: A Table of parameters which determine the properties of the Object.
