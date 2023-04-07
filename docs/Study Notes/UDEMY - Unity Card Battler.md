- When doing some of the UI placement on a card, changed camera from perspective to isometric
  - mentioned some reasoning, but reminder to look into this more for later to 
    understand why

- Wanted to have background image for image section of card
  - turned on perserve aspect ratio, but image wasn't perfect size for card
  - Added another UI->Image, turned of maskable, added component 'Mask', and 
    sized the rect so it covered the image area
  - Next moved background image to be a child of the mask
  - This let's us resize the image so it covers the mask area without going out of the bounds we want

- Set z rotation on cards so if you have a lot of cards in hand, they don't overlap and look bad

- Can hold control when moving something in scene view to move in increments

- Can pause before pressing play so that you can unpause after scene has finished compiling
  which allows you to see stuff without the stutter that compiling can cause

- Added each song/sound effect as an audio source in the scene 
  - can add a window->audio->audio mixer and have groups for master/soudtrack/sfx/etc where
    you can set overall volume for each group and control them that way
  - Will look more into using this on my own
  - I've done have one audio source with a list of audio clips
    - maybe do some research on difference and pros/cons

- Used an object with a custom audio manager script on it to play songs by taking in
  a reference to different audio sources

- Made this into a singleton and used DontDestroyOnLoad so that the audio manager would persist
  across different scene transitions

- To not have to have this large audio manager object with each song need to be packaged in each scene 
  and loaded each time, we have a audiomanagerloader script we created which checks if 
  audio manager doesn't exist in scene and if so, instantiates the audio manager that we added as 
  as reference from the scene we did create the audio manager in 
  This allows us to still have an audio manager even if the main scene isn't the first one loaded