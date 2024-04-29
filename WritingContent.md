# Welcome to WritingContent.md 
Author's Note: I am by no means a professional at creating dialogue. However, I have accumulated a lot of knowledge that might benefit others like myself who want to create a dialogue pack but are unsure where to start! Please join [my discord server](https://discord.gg/WNEamREvKh) to let me know if you find any issues with this guide! 

# Contents
- [Creating a Dialogue Modpack](#creating-a-dialogue-modpack)
- [Dialogue Keys](#dialogue-keys)
  	- [Generic Dialogue](#generic-dialogue)
  	- [Location Dialogue](#location-dialogue)
  	- [Special Dialogue](#special-dialogue)
  	- [Marriage Dialogue](#marriage-dialogue)
  	- [Data Directory & Other Dialogue Locations](#data-directory-and-other-dialogue-locations)
- [Formatting Cheatsheet](#cheatsheet)
  	- [Formatting](#formatting) 
 	- [Portrait Commands](#portrait-commands) 
  	- [Dialogue Commands](#dialogue-commands)
   	- [Response IDs](#response-ids)
    - [Replacer Commands](#replacer-commands) 
- [How to use the Skeletons](#how-to-use-the-skeletons)


# Creating a Dialogue ModPack
This information comes directly from the [Content Patcher Author Guide](https://github.com/Pathoschild/StardewMods/blob/develop/ContentPatcher/docs/author-guide.md#introduction), which is a definite must to read! 

1. Install SMAPI and Content Patcher
2. Create an Empty folder and name it [CP] TheModName, replacing TheModName with your unique mod name.
3. Create a manifest.json file with this content:
```
{
	"Name": "Your Mod Name",
	"Author": "Your Name",
	"Version": "1.0.0",
	"Description": "One or two sentences about the mod.",
	"UniqueID": "YourName.YourModName",
	"UpdateKeys": [], // when you release the mod, see https://stardewvalleywiki.com/Modding:Modder_Guide/APIs/Update_checks
	"ContentPackFor": {
		"UniqueID": "Pathoschild.ContentPatcher"
	}
}
```
4. Create a content.json file with this format:
```
{
    "Format": "2.0.0",
    "Changes": [
	{
		"Action": "EditData",
		"Target": "Characters/Dialogue/YOURCHARACTERHERE", // Edit this here with your desired character
					   // This target will also be changed depending on what you're editing!
					  // See the Data Directory & Other Dialogue Locations below for more info!
		"Entries": {
	    		// Dialogue keys here, more information on these below
	    	}
    	}
    ]
}
```

6. Note: My skeleton is a bit more complex than this but generally follows the same structure!
	- See: [How to use the Skeletons](#how-to-use-the-skeletons) for more information on these.


# Dialogue Keys
This information comes directly from the [Stardew Valley WIKI](https://stardewvalleywiki.com/Modding:Dialogue), but I've also added in 1.6 Dialogue for your ease of viewing :)
## Generic Dialogue
[!WARNING]
Presedence is given to Special Dialogue, then Location, then Generic.

After Special and Location Dialogue, the game will choose dialogue using these key formats (in precendence order):
```
1. <season>_<key>_inlaw_<spouse>
	- Ex. "Spring_Mon_inlaw_Sam": "This is dialogue that will show up for any NPC reguardless if they're related to Sam on Mondays in Spring"
2. <season>_<key>
	- Ex. "Spring_Mon": "This is dialogue that will show up on Spring Mondays."
3. <key>_inlaw_<spouse>
	- Ex. "Mon_inlaw_Sam": "This is dialogue that will show up for any NPC regardless if they're related to Sam on Mondays"
4. <key>
   	These are shown below with their respective formats. 

	<dayOfMonth> - Shown on the given day of month in the FIRST YEAR ONLY
		- Example:
			"10": "This is dialogue which will show up on the 10th day of every month in the first year."

	<dayOfMonth>_<firstOrLaterYear> - Shown on the given day of month in the first or later years
		- Example:
			"2_2": "This is dialogue which will show up on the 2nd day of the month on the second year."

	<dayOfWeek><hearts>_<firstOrLaterYear> - Shown on given day of week if you have AT LEAST the amount of <hearts> with them.
			Will be checked in the order of 10, 8, 6, 4, 2 (no other values are recognized at this time)
		- Example:
			"Mon2_2": "This is dialogue which will show up on Mondays with at least 2 hearts of the given NPC on the second year."

	<dayOfWeek><hearts> - Shown on the day of week if you have at least the amount of <hearts> with them.
			Checked in the same order as above.
		- Example:
			"Mon2": "This is dialogue which will show up on Mondays with at least 2 hearts of the given NPC."

	<dayOfWeek>_<firstorLaterYear> - Shown on the given day of week in the first or later year
		- Example:
			"Mon_2": "This is dialogue which will show up on Mondays on the second year"

	<dayOfWeek> - Shown on given day of week, no matter the year
		- Example:
			"Mon": "This is dialogue which will show up on Mondays"
```

## Location Dialogue
[!WARNING] Precedence is given to Special Dialogue. 

After Special Dialogue, the game will check for variants in this order: 
```
1. <season><key>
	Ex. "springMountain": "This is dialogue that will show up when the NPC is in the Mountain and the season is Spring"
2. <key> 
   	These are shown below with their respective formats. 

 	<location>_<x>_<y> - Shown when the NPC is standing in the location at the exact position (x,y)
		- Example:
   			"Mountain_47_23": "This is dialogue that will show up when the NPC is at position (47,23) in the Mountains"
	<location>_<dayOfWeek> - Shown at the location on the day of the week
		- Example: 
			"Saloon_Fri": "This is dialogue that will show up when the NPC is at the Saloon on Fridays"
	<location><hearts> - Shown in the location if you have at least <hearts> with them
		- Example:
   			"Saloon8": "This is dialogue that will show up when the NPC is at the Saloon and you have 8 hearts with them"
	<location> - Shown at that location
		- Example:
   			"Saloon": "This is dialogue that will show up when the NPC is at the Saloon"
```

## Special Dialogue
## Marriage Dialogue
## Data Directory and Other Dialogue Locations

# CheatSheet
Formatting
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
	# - Separates two commands in a dialogue String
		EX. $l#$b - $l(loads in the love portrait)#(Separates)$b(Loads in a new dialogue box) 
	{ - Stands for "breakSpecialCharacter"
		Not really used unless for JSON formatting tbh
	^ - Gender Switching. Helpful for Gender-Based dialogue
		EX. Hello, Mr. @!^Hello, Ms. @!
	% - Turns dialogue box into generic text box
		EX. %Sam waves at you.
	* - Stands for "quickResponseDelineater"
		Not 100% sure what this does tbh
		

Portrait Commands
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
	Portrait commands go at the END of the line of dialogue. 
	EX. "Good_0": "You look really cute today. $l#$e Do you think I could have your number?$10"  

	$neutral or $0 - Neutral Portrait
	$h or $1 - Happy Portrait
	$s or $2 - Sad Portrat
	$u or $3 - Unique Portrait
	$l or $4 - Love Portrait
	&a or $5- Angry Portrait
	etc.


Dialogue Commands
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Basic Commands 
	$b - Inidates pauses in dialogue, player needs to click to load in the new box
	$e - Ends current Dialogue, closing the dialogue box. Will require a new interaction.
	$k - Kills Dialogue; Unsure how this one works tbh 
	$c <probability>#<text1>|<text2> - Show one dialogue with a probability (between 0 and 1) to show text1 over text2
	$d <state id>#<text1>|<text2> - Show dialogue if a condition has occured, if not, show text2
		E.G. (state ids) - kent (if kent has returned), bus (if bus is repaired), joja (if jojamart is still in business), 
                		cc/communitycenter (whether community center is accessible) 
	$y - Works like question, but simpler. 
		E.X. Sam: "$y 'Eat breakfast with me?_Yes please._I love when you spend time with me_No, get away from me_Whatever, 
                    you'll want me soon enough'"
                    (Can you tell who I originally started writing dialogue for LMAO)
	%fork - Mainly useful for reaction dialogue; Will update when I understand this one more
	[#, #, #] - Gives the player a random item from the pool of IDs (# being the item's ID)


### Question Commands
 
	$q <response IDs><fallback>#<text> - Basic Question format
	$r <response ID><friendship> <reaction>#<text> - Response format
	$p <response ID>#<match text>|<no match text> - Prerequisite text format


### Question Example: 
 
	summer_Fri:
		"I think I'm gonna go to the beach tomorrow!
		#$q 305/306 beachquestion_followup#Would you like to go with me?
			#$r 305 15 beachquestion_yes#Sure, I'd love to!
			#$r 306 0 beachquestion_sorry#Sorry, I already have plans...
			#$r 306 -15 beachquestion_no#No, you're ugly.",
		beachquestion_yes: "Awesome! It's a date.$h",
		beachquestion_sorry: "Oh, alright.$6",
		beachquestion_no: "Oh.$s",
		beachquestion_followup:
			"$p 305
				#Tomorrow should be a lot of fun!$h
				|Hmm, I wonder if I can get someone to go with me...$s",


Response IDs
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
There is a list of all current response ID's on the WIKI: https://stardewcommunitywiki.com/Modding:Dialogue


Replacer Commands
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
	@ - Farmer's Name
	%adj - Random Adjective
	%noun - Random Noun
	%place - Random Place
	%spouse - farmer's spouse
	%name - Random name
	%firstnameletter - First half of the farmer's name (rounded down)
	%time - Current time
	%band - Name of Sam & Seb's band
	%book - Title of elliot's book
	%rival - Random first name of the Farmer's gender. Won't match the farmer's name.
	%pet - Farmer's pet 
	%farm - Farm name
	%favorite - Farmer's favorite thing
	%kid1 - First kid
	%kid2 - Second kid

# How to use the Skeletons
