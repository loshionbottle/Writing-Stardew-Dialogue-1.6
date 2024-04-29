Author's Note
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
THIS IS NOT A MODPACK WHICH ADDS ANY SORT OF CONTENT TO THE GAME.
This is simply a FRAMEWORK which other people can use to edit NPCs dialogue.
This was written with romancable characters in mind, so if the character you're writing for is NOT romancable, consider deleting a lot.


Important Links
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Stardew Valley Wiki Modding:Dialogue section: https://stardewcommunitywiki.com/Modding:Dialogue
ContentPatcher Wiki: https://github.com/Pathoschild/StardewMods/blob/develop/ContentPatcher/docs/author-guide.md
More Indepth Guide to Writing Dialogue written by yours truly: 

Short but Simple Guide to the Modpack:
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Though most files have inline comments exlaining what to change, you might want to read here first in case you're confused 


DO NOT EDITS: (Or at least you really have no need to edit)
    1. readMe.txt - You are here 
    2. CheatSheet.txt 
        - Contains commands, formatting examples, portrait commands, replacers, etc. to help write the actual dialogue.
        - This is simply a shorter version of the Stardew Valley WIKI, I would not recommend using my cheatsheet as an end all be all.

DO EDIT: 
    1. manifest.json 
        - This should be the first thing you edit.
        - The "Name" field should be the name of YOUR pack
        - The "Author" field should be YOUR name or username
        - The "Description" field should be a SHORT description of YOUR modpack
        - The "Version" field should originally be 1.0.0, but edit at your own discression as you update.
        - The "UniqueID" field should follow this format: YOURUSERNAME.THENAMEOFYOURMODPACK
        - The "UpdateKeys" field, if using Nexus Mods to upload your mod should contain "Nexus:YOURUNIQUEID"
            - Here is info on how UpdateKeys works: https://stardewcommunitywiki.com/Modding:Modder_Guide/APIs/Update_checks
            - To get your own uniqueID, this forum should help: https://forums.stardewvalley.net/threads/nexus-update-key.14368/
        - "ContentPackFor" should not be changed, unless you're adding to the section
            - This Skeleton is meant for ContentPatcher
    2. content.json
        - Includes the ConfigSchema & Includes the files for this schema right below
        - I've included prompts on where you should edit, though again, I recommend reading the ContentPatcher WIKI
        - This modpack is already setup in case you want to add more character.jsons, Character_Festival.jsons, etc. 
            - Just be sure to edit content.json appropriately
    3. Assets/Dialogue/Character_NotMarried.json
        - This is the beefy part of the dialogue lines, I've already included prompts on where to edit the name of the Character
        - If your character is not romancable, I would suggest editing/deleting some keys 
    4. Assets/Dialogue/Character_Married.json
        - Edits marriage-related dialogue for the character
    5. Assets/Dialogue/Character_Festival.json
        - Edits Festival Dialogue for the character
        - Again, added prompts on where to edit the name
        - Again, if your character is not romancable, I would suggest getting rid of the dating/marriage parts
    6. Assets/Dialogue/Character_Gift.json
        - Edits gift responses for the character
        - A lot of keys were added in 1.6, so PLEASE look at the Stardew WIKI's 1.6 changelog 

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Thank you for reading & downloading! If you have any questions feel free to DM me on Discord or on Nexus. My username for both is: loshionbottle
