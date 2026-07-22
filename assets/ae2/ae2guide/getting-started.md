---
navigation:
  title: 始めよう (1.20.1 +)
  position: 10
---

<div class="notification is-info">
　この情報はApplied Energistics 2 (Minecraft 1.20.1)以降のみに適応されます。
</div>

# 始めよう

## 物資を集めよう

<GameScene zoom="4" background="transparent">
  <ImportStructure src="assets/assemblies/meteor_interior.snbt" />
</GameScene>

Applied Energisticsを始めるには、[隕石](ae2-mechanics/meteorites.md)を見つける必要があります。よくあり、地形に大きな変化が見られるため、旅の途中で見つけられるかもしれません。
もし見つけられなくても、最寄りの<ItemLink id="meteorite_compass" />を指す、<ItemLink id="meteorite_compass" />をクラフトできます。

隕石を見つけたら、中央を掘ってみましょう。ケルタスクォーツとケルタスクォーツの芽、さまざまな種類の[芽生えたケルタスクォーツブロック](items-blocks-machines/budding_certus.md)、そして中央にある不思議なキューブが見つかるでしょう。

ケルタスクォーツとケルタスクォーツブロックを掘りましょう。芽生えたケルタスクォーツブロックも掘るとよいですが、シルクタッチがないと1ティア下がってしまいます。

完璧なケルタスクォーツブロックは破壊しないでください。たとえシルクタッチで破壊しても必ず1ティア下がります。そして完璧なケルタスクォーツブロックに戻す手段はありません。

そして不思議なキューブを破壊して4つ(すべて)の金型を得ましょう。

## ケルタスクォーツを成長させよう

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_1.snbt" />
</GameScene>

 ケルタスクォーツは、[芽生えたケルタスクォーツブロック](items-blocks-machines/budding_certus.md)からアメジストのように芽生えます。成長する前に破壊した場合、
<ItemLink id="certus_quartz_dust" />をドロップしますが、運が良ければ変化しません。もし成長しきった結晶を破壊したら、
<ItemLink id="certus_quartz_crystal" />がドロップします。確率でドロップする数が変化します。

ケルタスクォーツブロックには4つの段階があります。
完璧な、傷ついた、角のかけた、壊れかけ

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_blocks.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

ケルタスクォーツの芽は成長し、「ケルタスクォーツブロック」になるまで、確率でブロックは1ティア低下します。
<ItemLink id="charged_certus_quartz_crystal" />といっしょにケルタスクォーツブロックを水の中に投げると、ケルタスクォーツブロックを修復することができます。

<RecipeFor id="damaged_budding_quartz" />

完璧なケルタスクォーツはティアが下がらないので無限にケルタスクォーツを生成します。しかしながらクラフトできませんし、シルクタッチを使っても移動できません。
([空間ストレージ](ae2-mechanics/spatial-io.md)を使えば移動できます)

これらのブロックはゆっくりとケルタスクォーツの芽を成長させます。
<ItemLink id="growth_accelerator" />を成長しているケルタスクォーツブロックの隣に置いて使用使用することで、ケルタスクォーツの成長を加速できます。
初めにいくつか作っておくと良いでしょう。

<GameScene zoom="4" background="transparent">
<ImportStructure src="assets/assemblies/budding_certus_2.snbt" />
<IsometricCamera yaw="195" pitch="30" />
</GameScene>

<ItemLink id="energy_acceptor" />または<ItemLink id="vibration_chamber" />を作るための十分なケルタスクォーツがない場合、
<ItemLink id="crank" />を作り、成長加速器に取り付けてください

ケルタスクォーツの自動化については[このページ](example-setups/simple-certus-farm.md)を参照してください

## A Quick Aside on Fluix

Another material you will need is Fluix, which you have already encountered in making growth accelerators. It is made by throwing charged certus, redstone, and nether quartz in water. Doing this automatically is "left as an exercise for the reader."

The <ItemLink id="charger" /> is required to produce <ItemLink id="charged_certus_quartz_crystal" />., if you haven't made one already.

## Inscribing Some Processors

In your looting of a meteorite, you will have found four "presses" from breaking the Mysterious Cube. These are used in the <ItemLink id="inscriber" /> to make the three types of processor.

<ItemGrid>
  <ItemIcon id="silicon_press" />

  <ItemIcon id="logic_processor_press" />

  <ItemIcon id="calculation_processor_press" />

  <ItemIcon id="engineering_processor_press" />
</ItemGrid>

The inscriber is a sided machine, much like the vanilla furnace. Inserting from the top or bottom places items in the top or bottom slots, and inserting from the side or back inserts into the center slot. Results can be pulled from the side or back.

To facilitate automation with hoppers (and possibly reduce pipe spaghetti), inscribers can be rotated with a <ItemLink id="certus_quartz_wrench" />.

Produce a few of each type of processor in preparation for the next step, making a very basic ME system. Automating processor production is "[left as an exercise for the reader](example-setups/processor-automation.md)".

## Matter Energy Tech: ME Networks and Storage

### What is ME Storage?

Its pronounced Emm-Eee, and stands for Matter Energy.

Matter Energy is the main component of Applied Energistics 2, it's like a mad scientist version of a Multi-Block chest,
and it can revolutionize your storage situation. ME is extremely different than other storage systems in Minecraft, and
it might take a little out of the box thinking to get used to; but once you get started vast amounts of storage in tiny
space, and multiple access terminals are just the tip of the iceberg of what becomes possible.

### What do I need to know to get started?

First, ME Stores items inside of other items, called [Storage cells](items-blocks-machines/storage_cells.md); there are 5 tiers with ever increasing amounts of
storage. In order to use a Storage Cell it must be placed inside either an <ItemLink id="me_chest" />,
or an <ItemLink id="drive" />.

The <ItemLink id="me_chest" /> shows you the contents of the Cell as soon as its placed inside, and you
can add and remove items from it as if it were a <ItemLink id="minecraft:chest" />, with the exception that the items are
actually stored in the Storage cells, and not the <ItemLink id="me_chest" /> itself.

The <ItemLink id="me_chest" /> is quite situational and limited in utility. To really
take advantage of AE2, you need to set up an [ME Network](ae2-mechanics/me-network-connections.md).

## Your Very First ME System

Now that you have all of the basic materials and machines for Applied Energistics 2, you can make your first ME (Matter Energy) system. This will be a very basic one, no autocrafting, no logistics, just nice, simple, searchable storage.

<GameScene zoom="6" interactive={true}>
<ImportStructure src="assets/assemblies/tiny_me_system.snbt" />

</GameScene>

*   Your ingredients list:
    * 1x <ItemLink id="drive" />
    * 1x <ItemLink id="terminal" /> or <ItemLink id="crafting_terminal" />
    * 1x <ItemLink id="energy_acceptor" />
    * A few [cables](items-blocks-machines/cables.md), either glass, covered, or smart, but not dense
    * A few [storage cells](items-blocks-machines/storage_cells.md), recommended of the 4k variety for a good mix of
    capacity and types (it would be more efficient to [partition](items-blocks-machines/cell_workbench.md) a mix of 4k and 1k but that's a complexity we won't go into now)
---
1.  Place the drive down.
2.  The energy acceptor (and several other AE2 [devices](ae2-mechanics/devices.md)) comes in 2 modes, cube and flat. They can be switched between in a crafting grid. If your energy acceptor is a cube, place it down next to the drive. If it's a flat square, place a cable on the drive and place the acceptor on that.
3.  Run energy into the energy acceptor with a cable/pipe/conduit from your favorite energy-generation mod.
4.  Place a cable on top of the drive (or otherwise at eye level) and place your terminal or crafting terminal on it.
5.  Put your storage cells into the drive
6.  Profit
7.  Fiddle with the terminal's settings
8.  Bask in your ultimate power and ability
9.  Realize that this network is, in the grand scheme, rather small

### Expanding your Network

So you have some basic storage, and access to that storage, it's a good start, but you'll likely be looking to maybe
automate some processing.

A great example of this is to place a <ItemLink id="export_bus" /> on the top of a furnace to
dump in ores, and a <ItemLink id="import_bus" />
on the bottom of the furnace to extract furnaced ores.

The <ItemLink id="export_bus" /> lets you export items from the network, into the attached
inventory, while the <ItemLink id="import_bus" /> imports items from the attached inventory into
the network.

### Overcoming Limits

At this point you probably getting close to 8 or so [devices](ae2-mechanics/devices.md), once you hit 9 devices you'll have to start
managing [channels](ae2-mechanics/channels.md). Many devices but not all, require a channel to
function.

By default a network can support 8 channels, once you break this limit, you'll have to add
an <ItemLink id="controller" /> to your network. this allows you to expand your network greatly.
[Smart cables](items-blocks-machines/cables.md) will allow you to see how channels are routed through your network. Use them extensively when starting out to learn how channels act, or if you have a lot of redstone and glowstone.
