This help file contains need to know information and references regarding class creation.
Please see the contents below and use Ctrl + F to find what you are looking for.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Contents:
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

01. How to Start building your first class
02. Assigning your Class Weapons (includes weapon reference list)
03. Other class data you need to edit
04. Assigning Perks for your Class
05. Training Centre Duplicate XCOM ability Fix
06. Assigning Class level up stat gains
07. Assigning Class Name & Information
08. Disabling Classes & Using Other Modders Resources
09. Final Notes & Other Information


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
01/ "How to Start Building your first class"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

First off when creating a class you need to think of what role your class is going to serve.
It's especially important to consider its secondary weapon as this will limit you to certain perks.
The Primary weapon usually doesn't matter (unless you have a mod like Primary Pistols) but try and pick one that suits your class.
It's not good having all the weapons though so just pick the most important one (unless you are going for something like a jack of all trades).

First thing which you will need to do for each new class you create is to enable the class.
Go to the Config Folder and open up XComClassData.ini
You will want to find the first section and change ";+SoldierClasses="TemplateClass01" to "+SoldierClasses="TemplateClass01".
Removing the ";" comment allows code to activate, so this enables TemplateClass01 to appear in your game. (Don't worry about the name you get to change it')
However it doesn't have any weapons or abilities yet so you will need to assing it some (see contents for help on where to go next)
Tts also worth looking at the ExampleTemplateClass (in XComClassData) for some notes I left there.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
02/ "Assigning your Class Weapons (includes weapon reference list)"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

There are 2 parts to giving your class a weapon.
The First part is to sort out its loadout weapons. These are the weapons the class will always spawn with.

Go to the Config Folder and open up "XComGameData.ini" then edit the weapon loadout based on the class template you are building on.
The ExampleTemplateClass equips a Assault Rifle & Claymore by default
+Loadouts=(LoadoutName="SquaddieExampleTemplateClass", Items[0]=(Item="AssaultRifle_CV"), Items[1]=(Item="Reaper_Claymore"))

LOADOUT WEPAON LIST - PRIMARY (ShardGauntlet is Templar Blades)
AssaultRifle_CV
Bullpup_CV
Cannon_CV
ShardGauntlet_CV
Shotgun_CV
SniperRifle_CV
VektorRifle_CV

LOADOUT WEPAON LIST - SECONDARY (Sidearm is Templar Uzi, WristBlade is Skirmisher secondary)
Gremlin_CV
GrenadeLauncher_CV
Pistol_CV
PsiAmp_CV
Reaper_Claymore
Sidearm_CV
SparkBit_CV
Sword_CV
WristBlade_CV

The Second part is to add weapons to the class template you are building on, so go back to XComClassData.ini in the Config folder and find the class you are working on.
On each class template I have left for you these lines;
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="")

The first line allows for Primary weapons the class can use. The first one should always be the primary weapon that you assigned in XComGameData.ini for your loadout.
However you can add additional primary wepaons to your class, you jsut need to add more +AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="") lines under the first one.
The weapons here have different reference names to that of XComGameData however so see below for full list.

XCOM CLASS DATA WEAPON LIST - PRIMARY (note that "rifle" is actually the assault rifle)
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="rifle")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="bullpup")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="cannon")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="gauntlet")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="shotgun")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="sniper_rifle")
+AllowedWeapons=(SlotType=eInvSlot_PrimaryWeapon, WeaponType="vektor_rifle")

The second line +AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="") is for the secondary weapon. This should match the secondary weapon you assigned in XComGameData.ini for your loadout.
Please note that you should only try to have 1 secondary weapon, having multiple secondary weapons can make a lot of your perks not work as most perks are specific for gremlin or sword for example.

XCOM CLASS DATA WEAPON LIST - SECONDARY (Note that the Sidearm which is the Templars Uzi looks weird on normal soldiers when fired)
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="gremlin")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="grenade_launcher")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="pistol")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="psiamp")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="claymore")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="sidearm")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="sparkbit")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="sword")
+AllowedWeapons=(SlotType=eInvSlot_SecondaryWeapon, WeaponType="wristblade")


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
03/ "Other class data you need to edit"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In XComClassData.ini where you just assigned your weapons you will have noticed other lines there.
The important ones you need to change are;
+ClassPoints=4
+IconImage="img:///UILibrary_Common.class_"
+KillAssistsPerKill=4

+ClassPoints=4 dictates how hard or easy it is to level up, the higher this value the longer it will take to level up.
Characters like Grenadiers and Sniper tend to have a value of 5 ot 6 here as its easier for them to rack up kills.
On the other side of this weaker characters like a specialsit would have a value of 3 as they get less kills on average.
Change this to suit your class idea, if your going for a powerful class make it as high as possible so other classes have a chance.

+KillAssistsPerKill=4 dictates how many assist kills count as a full kill. An assist kill is where this class damages an enemy and another class finsihes them off.
The class that dealt damage gets an assist point. If your character has a lot of overwatch abilities you might want to make this higher but 4 seems to be the average.

Finally +IconImage="img:///UILibrary_Common.class_" dictates the class icon for your class.
For this you will be able to assign class icons from the base xcom game and even use icons from classes you are subscribed too!
Below is a list of XCOM Class icons and a list of Icons from my WotC class pack if you are subbed to that.

XCOM CLASS ICONS
"img:///UILibrary_Common.class_rookie"
"img:///UILibrary_Common.class_ranger"
"img:///UILibrary_Common.class_sharpshooter"
"img:///UILibrary_Common.class_grenadier"
"img:///UILibrary_Common.class_specialist"
"img:///UILibrary_Common.class_psiop"

XCOM HERO CLASS ICONS
"img:///UILibrary_XPACK_Common.Faction_Skirmisher_flat"
"img:///UILibrary_XPACK_Common.Faction_Reaper_1_sm"
"img:///UILibrary_XPACK_Common.Faction_Templar_flat"

RICHARDS WOTC CLASS PACK ICONS [ONLY IF YOU ARE SUBBED TO MY MOD] (note that you do not need the "" quotes for mine, if they dont show however try the quotes first)
img:///UILibrary_Richard.class_assassin
img:///UILibrary_Richard.class_demolitions
img:///UILibrary_Richard.class_gunner
img:///UILibrary_Richard.class_mage
img:///UILibrary_Richard.class_marksman
img:///UILibrary_Richard.class_medic
img:///UILibrary_Richard.class_raider
img:///UILibrary_Richard.class_rifleman
img:///UILibrary_Richard.class_scout
img:///UILibrary_Richard.class_survivalist
img:///UILibrary_Richard.class_swat
img:///UILibrary_Richard.class_technician


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
04/ "Assigning Perks for your Class"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The Perks for your class are the most important part of your class, these will dictate how your class plays and what experience you are going for.
You should consider that some abilities are more powerful than others so would be best unlocked later down the tree.
Another factor you want to consider is the ability choice at each rank, you want it to be a choice that is hard to make.
I feel like in the basegame there are no real "hard choices" there are obvious go to's such as Blademaster and Shredder.
You should try and make it more competitive like what if it was Shredder versus holotargeting for example.

Config > XComClassData.ini
You should start with the squaddie perks first, you have to have 1 but I have left space for up to 4 (I recommend 4 maximum as it fits the Training Centre nicely).
For squaddie you HAVE to have the perk for your secondary weapon in order to use it.

For a full list of basegame XCOM perks you can use (sorted by weapon type/restrction) open "XCOMPerks.txt"
For a full list of DLC XCOM perks you can use (sorted by weapon type/restrction) open "DLCPerks.txt"
For a full list of my custom perks (if you are subbed to my mod) open "RICHARDPerks.txt"


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
05/ "Training Centre Duplicate XCOM ability Fix"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In XCOM 2 the AWC (advanced warefare centre) introduced a mechanic where you gained a random xcom trait.
However due to the way the game works, on custom classes you would sometimes get assigned a perk your class already has.
In XCOM 2 WotC the Training Centre allows the expenditure of Ability Points to buy random XCOM Perks.
However sometimes these are rolled as a duplicate so its a waste of a potential random perk slot for your class.
To fix this for your class you need to find its template in "XComClassData.ini" and look at these lines:
+ExcludedAbilities=""				; AWC Disabled

That line allows you to specifiy an ability that cannot be gained by this class via the random XCOM abilities.
This is mostly useful for preventing duplicate perks, for example if you have Phantom you won't want Phantom to be rolled on your character.
So you would add:
+ExcludedAbilities="Phantom"

Another use for this is disabling conflicting abilities, for example if you have Shadowstep you won't want Lightning Reflexes on your character.
So you would add:
+ExcludedAbilities="LightningReflexes"

I'm not entirely sure which of the base game abilities are allowed for the XCOM pool but it seems to be most of them.
Obviously specific abilities like Medical Protocol & Bladestorm don't show up for regular soldiers.
Your best bet is just to play your class a lot and see what random abilities pop up and then just disable the ones you don't want to show up from experience.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
06/ "Assigning Class level up stat gains"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In "XComClassData.ini" under your class template you will have noticed that at each promotion rank there are a series of stat gains.
I have just included the ones that the base game classes use as I'm not sure if you can add stats like dodge.
It's important to note that at Squaddie rank you must have StatType=eStat_CombatSims,StatAmount=1 to be able to use PCS chips.

Your main stats are:
eStat_Offense (aim)
eStat_HP
eStat_Strength (stunlance/mindspin resist)
eStat_Hacking

You should try and balance your soldiers carefully, the Base Game classes all have different stat gains but here are some average values:
eStat_Offense (2-3 per rank up to +15 for Colonel Ranger/Specialist but +10 for Colonel Grenadier with a total of +26 for Colonel Sharpshooter)
eStat_HP (1 per rank up to +10 for Colonel soldiers but the Colonel Sharpshooter gets about +8)
eStat_Strength (0-1 per rank, Most of the Colonel soldiers end up with only +1 or +2, I think the Grenadier has +3)
eStat_Hacking (0-5 per rank, Non-Specialist Colonels end up with +15 Hack while the Specialist gets about +75 as they get 45 @ Squaddie then 5 per rank)

You should also consider that class Stat gains are added on top of the rookie stats which are:
eStat_Offense (65)
eStat_HP (Depends on Difficulty, 6 on Easy, 5 on Normal, 4 on Harder Difficulties)
eStat_Strength (0)
eStat_Hacking (5)

PSIONIC CLASS STATS
If you are making a Psionic Class that works like a normal soldier you will need the Psi Offense stat to be able to increase in power.
Unfortuntately the game doesn't show Psi-Offense for normal soldiers so you will only see your stat when you try to use abilities like Insanity on enemies.
Psi Offense is basically AIM for Psionic Attacks, or success chance.

@Squaddie for Psionic Class you need;
aStatProgression=((StatType=eStat_Offense,StatAmount=0), (StatType=eStat_HP,StatAmount=0), (StatType=eStat_PsiOffense,StatAmount=0), (StatType=eStat_Strength,StatAmount=0), (StatType=eStat_Hacking,StatAmount=0), (StatType=eStat_CombatSims,StatAmount=1), (StatType=eStat_Will,StatAmount=5)),\\

Then for every other rank you need;
aStatProgression=((StatType=eStat_Offense,StatAmount=0), (StatType=eStat_HP,StatAmount=0), (StatType=eStat_PsiOffense,StatAmount=5,RandStatAmount=10,CapStatAmount=100)),\\


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
07/ "Assigning Class Name & Information"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This is probably the part you've been waiting for.
In the Localization folder open up "XComGame.int"
Then find the Template you were building your class on (for example ClassTemplate01)

CLASS NAME
To give your class a name write in the DisplayName line.
+DisplayName=""

CLASS DESRIPTION
To give your class a description (which shows up in the GTS & on the class itself) write in the ClassSummary line.
+ClassSummary="."

ABILITY TREE NAMES
To give ability tree names (which are disaplyed above your perks in the classic promotion screen) write in the AbilityTreeTitle lines.
+LeftAbilityTreeTitle=""
+RightAbilityTreeTitle=""

CLASS NICKNAMES
You can give your class custom nicknames when they reach SGT rank. You can assign random nicknames and male/female specific ones.
You can add as many nickname lines as you like but they must always start from 0.
I have provided templates for this (starting from 0)
+RandomNickNames[0]=""
+RandomNickNames_Male[0]=""
+RandomNickNames_Female[0]=""

CLASS RANKS
Did you know you can apply custom rank names to your soldiers?
You can see the ExampleTemplateClass for how this works but below I have provided the BaseGame Examples.
Note that this just applies to your class, it doesn't effect other classes.

CLASS RANKS - NORMAL

+RankNames[0]="Rookie"
+RankNames[1]="Squaddie"
+RankNames[2]="Corporal"
+RankNames[3]="Sergeant"
+RankNames[4]="Lieutenant"
+RankNames[5]="Captain"
+RankNames[6]="Major"
+RankNames[7]="Colonel"
+RankNames[8]="Brigadier"

+ShortNames[0]="Rk."
+ShortNames[1]="Sq."
+ShortNames[2]="Cpl."
+ShortNames[3]="Sgt."
+ShortNames[4]="Lt."
+ShortNames[5]="Cpt."
+ShortNames[6]="Maj."
+ShortNames[7]="Col."
+ShortNames[8]="Brig."

CLASS RANKS - PSIONIC

+RankNames[0]="Rookie"
+RankNames[1]="Initiate"
+RankNames[2]="Acolyte"
+RankNames[3]="Adept"
+RankNames[4]="Disciple"
+RankNames[5]="Mystic"
+RankNames[6]="Warlock"
+RankNames[7]="Magus"

+ShortNames[0]="Rk."
+ShortNames[1]="Int."
+ShortNames[2]="Acl."
+ShortNames[3]="Adp."
+ShortNames[4]="Dsc."
+ShortNames[5]="Mys."
+ShortNames[6]="War."
+ShortNames[7]="Mag."

+RankIcons[0]= "UILibrary_Common.rank_rookie"
+RankIcons[1]= "UILibrary_Common.psirank_initiate"
+RankIcons[2]= "UILibrary_Common.psirank_acolyte"
+RankIcons[3]= "UILibrary_Common.psirank_adept"
+RankIcons[4]= "UILibrary_Common.psirank_disciple"
+RankIcons[5]= "UILibrary_Common.psirank_mystic"
+RankIcons[6]= "UILibrary_Common.psirank_warlock"
+RankIcons[7]= "UILibrary_Common.psirank_magus"

CLASS RANKS - SPARK

+RankNames[0]="Rookie"
+RankNames[1]="Squire"
+RankNames[2]="Aspirant"
+RankNames[3]="Knight"
+RankNames[4]="Cavalier"
+RankNames[5]="Vanguard"
+RankNames[6]="Paladin"
+RankNames[7]="Champion"

+ShortNames[0]="Rk."
+ShortNames[1]="Sqr."
+ShortNames[2]="Asp."
+ShortNames[3]="Knt."
+ShortNames[4]="Cav."
+ShortNames[5]="Vng."
+ShortNames[6]="Pal."
+ShortNames[7]="Chp."

+RankIcons[0]="UILibrary_Common.rank_rookie"
+RankIcons[1]="UILibrary_DLC3Images.rank_squire"
+RankIcons[2]="UILibrary_DLC3Images.rank_cavalier"
+RankIcons[3]="UILibrary_DLC3Images.rank_knight"
+RankIcons[4]="UILibrary_DLC3Images.rank_vanguard"
+RankIcons[5]="UILibrary_DLC3Images.rank_templar"
+RankIcons[6]="UILibrary_DLC3Images.rank_paladin"
+RankIcons[7]="UILibrary_DLC3Images.rank_champion"


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
08/ "Disabling Classes & Using Other Modders Resources"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

In this mod under "XComClassData.ini" there is a section for disabling the Vanilla classes.
If you want to disable other modders classes (if you are just using their resources) you can open their "XComClassData.ini" file and find the section:
[XComGame.X2SoldierClass_DefaultClasses]

In this section you can place a comment code ";" before any line that adds a class to disable the class completely.
EXAMPLE
;+SoldierClasses="ExampleTemplateClass" 

In terms of using other modders resources, the best thing to do is go to the Localization folder in their mod and open up "XComGame.int" to see a full list of their perks.
This will give a description of each of their perks plus the code call of what the perk is.
You should also be aware of how perks are applied so also check their "XComClassData.ini" to see how their class templates are setup.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
09/ "Final Notes & Other Information"
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Now you have just essentially made your own class. Give it a go in game to make sure it works, if not drop a comment on the mod page and someone will help you out.
You can repeat the process on the other templates here (there are 20 in total) so have fun and don't be afraid to try things.

Also, what might be fun is that if we get a bunch of good class ideas out of this we can make a community class pack.
That would be a seperate mod I'm willing to upload with peoples class builds.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
END FILE
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------