What it is:

Playerbot lets you add another character from your account as a bot that you can control and which will hopefully help you. Only characters from your account can be used, so you can have a maximum of 9 bots at one time.

This was taken from the Trinity site, and modified slightly by me to get some of the kinks out. I reworked the priest class and also added a mage class and a warrior class, which are still in crude form. Any class can be used as a bot - just don't expect much in the way of spells or abilities until someone writes the code for them.

Bots will only use abilities that they have - for example, a priest will only use the renew spell if it has been trained. Also, bot's equipment will lose durability like any other character. So every so often you'll need to log in and repair and train your bot.

For Mangos 7800+

Commands:

/s .bot add BOTNAME (add character to world)
/s .bot remove BOTNAME
/invite BOTNAME (bot will auto accept invite)
/t BOTNAME attack (bot will attack selected target, similar to the way a pet can attack)
/t BOTNAME follow (orders bot to follow player; will also revive bot if dead or teleport bot if far away)
/t BOTNAME stay
/t BOTNAME assist (you'll need to be attacking something and the bot only does melee atm)
/t BOTNAME spells (replies with all spells known to bot)
/t BOTNAME cast <SPELLID>
/t BOTNAME cast <SPELL SUBSTRING>
/t BOTNAME use <ITEM LINK>
/t BOTNAME equip <ITEM LINK>
/t BOTNAME reset (will reset states, orders and loot list)
/t BOTNAME report (bot reports all items needed to finish quests)

If specifying a spell substring, the spell chosen will be in priority of exact name match, highest spell rank, and spell using no reagents. Case does not matter. Here's some examples:
/t BOTNAME cast greater heal
/t BOTNAME cast pain
/t BOTNAME cast poly
/t BOTNAME cast fort
/t BOTNAME cast SPELLID

Also all commands can be broadcast to the party. For example:
/p follow
/p spells

To trade items/money with your bot simply initiate a trade and the bot will tell you how much money and items are available. To request an item simple whisper the bot and shift click the link of the item you would like. You can link multiple items on the same line. You can also request money in the following manner when the trade window is open:
/w BOTNAME 10g <-- request that the bot give you 10 gold
/w BOTNAME 6g500s25c <-- request 6 gold, 500 silver, and 25 cooper

To use or equip items for your bot say:
/w BOTNAME use <ITEMLINK1> <ITEMLINK2>
/w BOTNAME equip <ITEMLINK1> <ITEMLINK2>

If you inspect your bot, your bot will tell you what items you have in your inventory that you can equip. To create a link in the chat window, hold the shift key and press the left mouse button when clicking the link.


Changes from Trinity to Mangos:

I added the following in SharedDefines.h.

enum SpellCategory
{
	SPELL_CATEGORY_FOOD             = 11,
	SPELL_CATEGORY_DRINK            = 59
};

I also had to add the following to Player.h:

enum PlayerStateType
{
	PLAYER_STATE_NONE              = 0,
	PLAYER_STATE_SIT               = 1
};



Some Problems:

The bots don't always face in the right direction. Sometimes when a bot makes the kill, the corpse is not lootable. The mage bot sometimes get stuck when he begins to cast a spell (but this is corrected the next time he enters combat).
