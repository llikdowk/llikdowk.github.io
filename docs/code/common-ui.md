# CommonUI
!!! Note
    All the issues mentioned here have been found in UE5.1. They may have been solved in future engine versions.

CommonUI is a cool plugin. At least when it works. And when it doesn't, at least is better than what we had before in UE4 without it.

It's common for new features to have bugs, so it's ok.
I've found that the biggest issues I've come across are related with the action routing.

# "CommonBoundActionBar" or the trap that's wasted many hours of my time before ditching it
Beware you oh mortal from this eternal punishment! Get away of this (as of unreal 5.1 at least) if you don't want to perish.
Here's the [official documentation](https://docs.unrealengine.com/5.2/en-US/using-the-common-bound-action-bar-in-unreal-engine/)

This is not great. For two reasons:

1. Doesn't refresh if the game is paused (and it's quite likely that some UI screens that use this bar is going to be part of a menu that's gonna pause the game). The workarounds they offer don't make much sense.
1. Uses different kind of widgets for buttons. Meaning that if you want to have a consistent looking for your buttons for pc, you are going to be forced to duplicate logic & visuals. Not ideal.

I've decided to use a simple collapsable button configuration for my menus as it's not a feature I really need. Simpler & without bugs.

# A tricky "Common UI Input Settings" & "FGameplayTag" discovery 
I use a custom structure that holds all the gameplay tags I need so I can access them from anywhere in the codebase. However I noticed that the Input Actions configuration was disappearing every time I closed the editor. Turns out that any tags defined through this structure that I had set in the project settigs weren't loading at the right time, so the engine wasn't populating them.

The solution is to declare them in any file as:

`UE_DEFINE_GAMEPLAY_TAG(TAG_UI_ACTION_ESCAPE, "UI.Action.Escape");`

I'm not a huge fan of these definitions as they tend to scatter all the tags around but as it's a especial case I don't mind it as much.
