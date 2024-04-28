# Creating a ModPack

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
	BASIC COMMANDS
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
		[#, #, #] - Gives the player a random item from the pool of IDs


	QUESTIONS
		$q <response IDs><fallback>#<text> - Basic Question format
		$r <response ID><friendship> <reaction>#<text> - Response format
		$p <response ID>#<match text>|<no match text> - Prerequisite text format

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
