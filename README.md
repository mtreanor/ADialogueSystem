# Things you need to know to use ADialogueSystem:

1. Duplicate [this spreadsheet](https://docs.google.com/spreadsheets/d/1V3YKhQapRcWOKAzGfee9DFqRJWpwLx6dlvYStOst500/edit?usp=sharing) this spreadsheet into your google Google Drive. Please do not modify the spreadsheet until you have copied your own version!

2. Change the permissions on your duplicated scene so that anyone with that scene can view the link (click the "Share" button in Google Sheets).

3. In Unity, drag the DialogueManager prefab into your scene, and provide the last part of your own google sheet (i.e. the `1wlWYeWrr-wAScjgJxtmpGl_1R6v3ONrYK5Kg9tPPuyM` part - don't include the "/edit" and all that - it shouldn't have any '/' in there at all).

4. To modify the initial state, you can add to the LoadInitialSCCState function inside of DialogueManager.cs. See the commented line of code in that function for an example.

	To get a line of dialogue, all you need to do is call `DialogueManager.scc.getSCCLine("some name");` It will return a string, and update the SCC state with the effect of the line that was selected.

5. You may want to have non-dialogue actions change the state (e.g. when you collide with a key, you may want to change the state for "hasKey"). You can also modify the state directly yourself in non-dialogue areas of your game by something like:

	`DialogueManager.scc.setGameStateValue("hasKey", "equals", true);`