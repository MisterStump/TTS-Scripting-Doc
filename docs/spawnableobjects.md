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
            
!!!info "Custom_AssetBundle"
    * **Table parameters**: A Table of parameters which determine the properties of the Object.
        * <div id='string'></div>**assetbundle**: The path/url for the AssetBundle. 
        * <div id='string'></div>**assetbundle_secondary**: The path/url for the secondary AssetBundle property. 
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
<div class="test">Test</div>
<h2 class="test">Test</h2>




###Custom Dice

###Custom Figurine

###Custom Model

###Custom Tile

###Custom Token
