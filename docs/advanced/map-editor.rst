.. NHSE Documentation:  Map Editor
   Covers topics related to the field item editor

=======================
Map (Field Item) Editor
=======================

This section covers topics related to map editing in NHSE.  This includes:

* Field items (adding/removing)
* Building manipulation (adding/moving/removing)
* Bridge/incline manipulation (adding/moving/removing)
* Terrain manipulation

To access the Field Item Editor, in the main NHSE window, go to the **Map** tab, click on **Edit Map...** and then
click on **Edit Field Items**.

**Note:**  It is recommended that you toggle on the 'Snap to nearest Acre on Click' option in the Field Item Editor.

Field Item Editing
==================

Field items are items (dropped, placed, planetd, etc.) on your island map.  The item editing functions can be found
in the **Items** tab in the Field Item Editor.

You can use the field item editor to do several item-related tasks, including:

* Add or remove a particular item to or from a particular tile on the map
* Bulk spawn items or DIYs
* Bulk removal from current acre or whole map
* Water all of your flowers

It is suggested that you read the :doc:`../basics/item-editor` documentation before continuing.

Per-Tile Item Editing
----------------------

Item editing on a per-tile basis functions very similarly to the inventory/storage editing functionality.  You
will see the item editor on the right.  You should make sure that the **Tile Editor Mode** option is set to
**Items**.

To **load** the item on a particular tile into the item editor, **left-click** the tile on the map preview.

To **clear** the item on a particular tile, **alt + left-click** the tile on the map preview.

To **set** the item on a particular tile to the item specified in the editor, **shift + left-click** the tile
on the map preview.

Alternatively, you can right-click the tile and choose **View** (load), **Set**, or **Reset** (clear).

Bulk Item Spawning
------------------

NHSE includes a basic bulk spawner that you can use to bulk-add items to your map.  To access the bulk spawner,
click on the **Remove Items...** button, and then click on the **Spawn...** option at the bottom.

The options available in the bulk spawner are as follows:

* **Spawn Type** (dropdown 1)

  * **ItemFromEditor** - bulk spawn the item currently loaded into the item editor
  * **SequentialDIY** - bulk spawn DIY recipes in sequential internal ID order

* **Spawn Layout** (dropdown 2)

  * **Square** - bulk spawns the item(s) in a square(ish) shape on the map
  * **Horizontal** - bulk spawns the item(s) in 2 rows on the map

* **X/Y** - the X/Y coordinate of the first item to spawn (upper-left coner for square layouts)
* **Count**

  * For **ItemFromEditor** spawn type, this is how many tiles to place the item/stack on
  * For **SequentialDIY** spawn type, this is how many of each DIY to generate

* **Start/Stop** (SequentialDIY only)

  * The (inclusive) start and end ID of the DIYs you wish to spawn

    * To spawn all DIYs, use the default of 0 to 9999; non-existent DIYs will not spawn
    * You can find resources with the DIY item IDs on the :doc:`../links` page

Bulk Item Removal
-----------------

NHSE provides functionality to bulk-remove items of a specific type (furniture, flowers, etc.) or of all types
from your map.

To access the bulk removal options, click on the **Remove Items...** button, and choose the type of item you
wish to clear from the map.  By default this will only remove items from the visible portion of the map.  To
remove the selected item type from the *whole* map, hold the **Shift** key while clicking the item type in the
button dropdown.

Flower Watering
----------------

NHSE provides functionality to automatically water all of the flowers on your map.

To access the flower waterer, click on the **Remove Items...** button and choose **Water Flowers**.  By default
this will only water flowers on the visible portion of the map.  To water flows on the *whole* map, hold the
**Shift** key while clicking the **Water Flowers** option in the button dropdown.

Building Manipulation
=====================

The list of buildings on your island, including the building options, is found on the **Buildings** tab of the
Field Item Editor.  You will see a list of the buildings and the map coordinates where they are placed.  Choosing
a building from the list will load the properties into the fields below (the Building Editor).

Buildings include actual buildings (resident services, Nook's Cranny, houses, etc.) as well as bridges and inclines.
For more information on using the Field Item Editor for bridges/inclines, see the next section.

Building Editor Fields
-----------------------

The following is a summary of the fields in the building editor and their purpose:

* **Building Type** - the type of building.  This is what distinguishes e.g. the museum from Nook's Cranny from a
  villager's house.  A mapping of the building IDs can be found at the end of this section.
* **X/Y** - the map coordinate of the building.  The origin (0, 0) of the map is the upper-left corner; that is,
  increasing Y will move the building towards the bottom of the map, and increasing X will move the building
  towards the right of the map
* **Angle** - the angle the building is placed at
  
  * This is only relevant for bridges and inclines; for actual buildings, it should be set to 0

* **Bit** - purpose unknown, recommended to leave at 0
* **Type** - the building subtype

  * This is only relevant for bridges and inclines, and determines what style of bridge/incline it is.  For actual
    buildings, it should be set to 0
  * Note that the same kind of bridge can have multiple subtypes; this is because bridges generally have a slightly
    different design based on how many tiles the bridge spans (4 v.s. 5)

* **TypeArg** - purpose unknown, recommended to leave at 0
* **UniqueID** - purpose unknown, recommended to leave at 0

Adding a Building
-----------------

To add a building to your map, select one of the empty building slots in the list.  An empty building slot will
appear as **000, 000 - None**.

Once you have the empty slot selected, fill in the building editor fields with the information for your new building.

It is not currently known if there are side effects to having e.g. multiple Nook's Crannys, multiple campsites, etc.

Modifying a Building
--------------------

To modify a building, select the building you wish to modify from the list.  This will populate the building editor
with the existing data for that building.  Then just edit the fields you want.  It is recommended that you only
modify the placement of buildings, since incorrect values for angle/subtype may glitch the building.

Removing a Building
-------------------

To remove a building, select the building you with to remove from the list.  This will populate the building editor
with the existing data for that building.  Set *all* of the fields in the building editor to 0 for this building.  You
will see the description in the list change to **000, 000 - None** which indicates a successful removal.

Currently there is no way to mass-remove buildings in NHSE.

Building Types
--------------

Below is a table that maps the building type ID to the description of the building

.. csv-table:: Building Type Descriptions
   :header: "Building Type ID", "Description"
   :align: center
   
   0, None
   1 - 8, Player 1 - Player 8 house
   9 - 18, Vilalger 1 - Villager 10 house
   19, Nook's Cranny
   20, Resident Services Building
   21, Museum
   22, Airport
   23, Resident Services Tent
   24, Able Sisters
   25, Campsite
   26, Bridge
   27, Incline
   28, Redd's Boat
   29, Harv's Studio
   30+, Unused
  
Bridge and Incline Manipulation
===============================

Bridges and inclines are considered buildings in-game and can be edited in the same manner.  It is strongly
recommended that you read through the previous section (Building Manipulation) for some background info.

Bridges have a building type of **26** while inclines have a building type of **27**.  Bridges and inclines
also have an **angle** (the orientation they are placed) as well as a **subtype** (the type of bridge/incline).
It is important to note that since bridges may span either 4 or 5 grid squares, individual bridge types have
multiple subtypes (e.g. the iron bridge can have a type of either 25 (4-tile bridge) or 40 (5-tile bridge)).

Lists for the bridge/incline subtypes and the orientation mapping are included at the end of this section.

Bridge and Incline ID Mappings
-------------------------------

Below are tables that map the subtype/angle value for bridges and inclines to a description of the bridge/incline
it will generate.  **This information may be incomplete/incorrect.**

.. csv-table:: Incline Subtypes and Descriptions
   :header: "Incline Type ID", "Description"
   :align: center

   WIP, WIP

.. csv-table:: Incline Angles and Descriptions
   :header: "Incline Angle ID", "Description"
   :align: center

   WIP, WIP
   
.. csv-table:: Bridge Subtypes and Descriptions
   :header: "Bridge Type", "Bridge Subtype = Small Bridge | Normal Bridge | Large Bridge"
   :align: center

   Straight Stone Bridges, 0 = 3 Spaces | 1 = 4 Spaces | 2 = 5 Spaces
   Diagonal Stone Bridges, 3 = 3 Spaces | 4 = 4 Spaces | 5 = 5 Spaces
   Straight Suspension Bridges, 7 = 3 Spaces | 6 = 4 Spaces | 8 = 5 Spaces
   Diagonal Suspension Bridges, 9 = 3 Spaces | 10 = 4 Spaces | 11 = 5 Spaces
   Straight Zen Bridges, 19 = 3 Spaces | 12 = 4 Spaces | 20 = 5 Spaces
   Diagonal Zen Bridges, 21 = 3 Spaces | 22 = 4 Spaces | 23 = 5 Spaces
   Straight Log Bridges, 14 = 3 Spaces | 13 = 4 Spaces | 15 = 5 Spaces
   Diagonal Log Bridges, 16 = 3 Spaces | 17 = 4 Spaces | 18 = 5 Spaces
   Straight Red Zen Bridges, 32 = 3 Spaces | 24 = 4 Spaces | 33 = 5 Spaces
   Diagonal Red Zen Bridges, 34 = 3 Spaces | 35 = 4 Spaces | 36 = 5 Spaces
   Straight Iron Bridges, 39 = 3 Spaces | 25 = 4 Spaces | 40 = 5 Spaces
   Diagonal Iron Bridges, 41 = 3 Spaces | 42 = 4 Spaces | 43 = 5 Spaces
   Straight Wooden Bridges, 44 = 3 Spaces | 37 = 4 Spaces | 45 = 5 Spaces
   Diagonal Wooden Bridges, 46 = 3 Spaces | 47 = 4 Spaces | 48 = 5 Spaces
   Straight Brick Bridges, 49 = 3 Spaces | 38 = 4 Spaces | 50 = 5 Spaces
   Diagonal Brick Bridges, 51 = 3 Spaces | 52 = 4 Spaces | 53 = 5 Spaces
   Straight Roped Off, 26 = 3 Spaces | 27 = 4 Spaces | 28 = 5 Spaces
   Diagonal Roped Off, 29 = 3 Spaces | 30 = 4 Spaces | 31 = 5 Spaces
   
.. csv-table:: Bridge Angles and Descriptions
   :header: "Bridge Angle ID", "Description"
   :align: center

   0, Straight Left to right OR Diagonal top light 45 degrees
   1, Straight top to bottom OR Diagonal bottom right -45 degrees
   2, Straight right to left OR Diagonal bottom left -135 degrees
   3, Straight bottom to top OR Diagonal top left 135 degrees

Terrain Manipulation
====================

NHSE allows you to modify the terrain of your island, to a certain extent.  It is strongly recommended that you
read the `NHSE wiki <https://github.com/kwsch/NHSE/wiki/Field-Item-Editor>`_ to get a sense of what is editable
(most island squares) and what is not (beach/ocean squares, airport dock, etc.)

It is very possible when editing the terrain that you will end up with glitched tiles.  Some of these may be
graphical glitches only (e.g. a sharp edge at the end of a river mouth) and others may impact playability (e.g.
tiles that cannot be walked over).

Because terraforming via NHSE is not likely to be significantly quicker than terraforming in-game and has a
high chance of causing glitches of some sort, this section will only cover a few common tasks.

Flattening Your Island
----------------------

