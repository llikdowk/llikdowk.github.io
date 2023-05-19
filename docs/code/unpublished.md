
## UI Buttons & Triggering input actions
I've noticed that if I put a `CommonButton` on a `CommonActivatableWidget`, I assign them a `TriggeringInputAction` and I use them to close the widget, when I open it again their actions no longer work: these actions work only once.

The workaround I found is to disregard these `TriggeringInputAction` completely and handling them in the activatable widget instead. Basically, I'm connecting the buttons OnClick & different actions to the same method, so they behave the same. 