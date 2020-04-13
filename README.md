# Tripwire_Redux

The concept in one line is 
"1v1 bomberman inspired battle royale"

Do read the Manual

Old changelogs
(since first outside test)

**12.04.2020**

&#43; Enemy health bar fixed
 
&#43; GetUserWidgetObject does not work in constructor

&#43; Fixed Lobby widget. Removed the delay and validity check.

&#43; Fixed repeated hosting failure. Added Destroy Session, before creating and joining.

&#43; Removed all material instances. //packaging issue solved for 4.25.6

&#43; Added "(test only)" to "Solo"

&#43; Set fps to 60. Enabled vsync

&#43; OMG! Internet play is working on PC.


**11.04.2020**

&#43; Server is building

&#43; Added Internet server IP input.

&#43; Added HUD Gauge Cluster. With 2 health bars and HP

&#43; Made all outside texture "256 x 256"

&#43; Added exit button to lobby.

&#43; Fixed entering stairs camera jerk (check and only then switch off crouch)


**24.11.2019**

&#43; Finally decided to stop trying to get lighting work. Now all rooms are statically lit and using black material for lights off.

&#43; Now all rooms are default lit.

&#43; Fixed “deices” not dropping properly (now using camera channel for line trace). 

&#43; The camera misbehave only happens on “Solo”. (I think)

&#43; Fixed. Pistol damage making enemy health bar disappear.

&#43; Fixed! Bomb doing multiple damage/on hit kill (Do once).

&#43; Fixed own overhead health bar being visible in succeeding match.

&#43; Fixed winner declaration.

**23.11.2019**

&#43; Decreased all texture sizes (256 x 256 from 512 x 512). To fit Google .abb size limit. (Nope! no effect).

&#43; Improved HUD reliability. (this caused enemy name to not appear again).

&#43; Improved lobby lighting.

&#45; Days of experiments has yielded the result that lights won’t work. We have to use dynamic lights and not more than 3 can ever overlap (excluding Directional Light). Hence the only way to get it to work without any ugly light bleeds is to use one light per room. This itself is ugly.

&#45; Possible solution is to change textures of room and all objects to black, instead of switching light. Or change all room and stairs meshes for slightly better fit. 

&#45; Stationary lights are also bugged.

&#45; All this is because of limits of OpenGL ES and Unreal. Has always worked well on DX.

&#45; Camera jumps if player jumps when crouched and other combos. Lighting is 🤮 Let’s just focus on gameplay now. If no solution, will have to completely remove it and add uniform light to all rooms, alway on.

**22.11.2019**

&#43; Finally fixed light bleeding through walls! (Nope!)

&#43; Fixed not being able to go up stairs if entered stairs while crouching.

**21.11.2019**

&#43; Fixed. Moving away from “PickUp” after “Trap” effect is over, closes it.

&#45; Closing “PickUp” overrides “Trap”

&#43; If “PickUp” canceled, it is now becomes immediately available.

&#43; Crouching does not affect camera.

&#43; Jumping does not affect camera! (Slight jitter when jumped on stars ramp).

&#43; Mine (nee Bomb) size decreased. Easier to avoid for planter.

&#43; Fixed devices being deployed bellow floor on crouch and in air on jump. Using “Line Trace”. (Sometimes get deployed face high)

&#43; Lasers can now be jumped over.

&#43; Smoke revealing exploaded bombs maybe fixed.

**19.11.2019**

&#43; Fixed! Other player data correctly displays on “Lobby Wall”

&#43; “Room and PickUp” switch reliability improved.

&#43; Fixed “Sprint and Stealth” meters not resetting before the round change.

&#43; Fixed “Room” state not resetting on round change.

&#43; Fixed “Enemy Name” in HUD.

&#45; Light bleed 😰

&#45; Enemy overhead health bar disappears sometimes.

&#45; “Nade” sometimes does one-hit kill.

**18.11.2019**

&#43; Fixed. Post “Trap” vision, the room light state reverts to pre “Trap” vision state.

&#43; In “Scope”, camera can now be controlled by the joystick.

&#43; Fixed. “Trap” not visible in “Room” type 3 

&#43; Removed useless “Punch”

&#43; Improved weapon switching and firing.

&#43; Added PickUp type colours in the flyout.

&#43; In “Scope”, “Device Dock” is hidden.

&#43; Added slight “Ability” on/of indicator.

&#43; “Sprint” meter stops drain on crouch.

&#43; Reworked “Stealth” calculation and application.

&#43; Added few sounds

&#43; Different animations for ”Run” and “Sprint” (reverted)

&#43; Less falling off stairs.

**17.11.2019**

&#43; Improved “PickUp” open click reliability. (Increased touch area)

&#43; Added “Kill Cam”

&#43; Modified “Levels” UI. 

&#43; Added “Grenade”

&#43; “Grenade destroys “Devices”, removes "Smoke"

**16.11.2019**

&#43; Fixed room lights not resetting on the next match (they retained their on match state).

&#43; Room lights changed.

&#43; Removed all “stairs” light

&#43; Added simple room textures

&#43; In absence of any material based indication of stealth activation on owner, using the same effect as used for remote players.

&#43; Improved all three room and two stair types meshes and UVs.

&#43; Improved stair and room fit and alignment.

&#43; Match data store fixed.

&#43; Pistol added!

**15.11.2019**

&#43; Added “crouch”

&#43; Fixed trap not being invisible on lights off.

&#43; Duplication of walk sound fixed.

&#45; Smoke reactivates all old blasted “Bombs”

&#45; Sprint broken

**11.11.2019**

&#43; Increased “Trap” vision time from 2s to 4s. Added “Green” light indicator.

&#43; “PcikUps” don’t emit light anymore. Hide when room light off.

&#43; Readded windowless room. Added 9th room.

&#43; Room textures changed (actually later removed) // check file size!

&#43; Replaced death explosion, with death animation (found several free packs)

&#43; WOW. Camera on respawn fixed. (it was simple, but where to was the trick)

&#43; 2s camera attached to “Laser”

&#43; Fixed: While one has opened “PickUp”, others don’t get “PickUP”

&#43; Fixed: Only “PickUps” marked “Help” opened. Hack fixed it.

&#43; Added fire crackling sound on “Fire”

&#43; Finally found lighting effect closer to vision (sharp dark and light) (using light channels) 

&#43; Room switch is useful because it can turn a player’s weapons against them. 

&#43; Simplified “Bomb” particle effects.

**11.10.2019**

&#43; Increased “Equip”, “Cancel” button sizes

&#43; Fixed HUD not showing on solo Local play.

&#43; Fixed some light issues on mobile

&#43; Fixed helper text appearing way behind the room switch. (attached to it)

&#43; Lobby Wall Display fixed using Delay nodes. Not confident of the fix.

&#43; “Ability” toggle reliability improved.

&#43; Fixed “Health” starting with 0 on respawn.

&#43; Added “Imersive Mode” on mobile

&#43; Increased the size of background wall.

&#45; On round change, the camera persists.

&#45; Some win situations "Lose" for both

&#45; By mistake switched ”Help" on all the pickup boxes.

**08.11.2019**

&#43; Major modularization. All levels (Main Menu, Lobby, Game) have there own GameModes. Player Controllers, PlayerCharacters.

&#43; All most all code went through and some refactored 

&#43; Removed all UI code from Characters to their Controllers

&#43; Stealth should also camo foot sound.

&#43; “Line cross” alarm and announcement sounds.

&#43; Jump has sound now. No more “Bunny Hop” for a silent walk.

&#43; Game rounds added.

&#43; Options has different types of quits.

&#43; HUD stores relevant inventory and used for loop with a break to keep from always reaccess of the array from controller.

&#45; On round change, the camera persists.

**06.11.2019**

&#43; Scope is now consumable.

&#43; Stealth/Sprint activation/deactivation is more reliable

&#43; Individual HUD element refresh.

&#43; Sprinting is smoother.

&#43; Bomb causes area damage (switched all custom damage handling to Engine’s system)

&#43; This also directly allowed “Sword” attack to work with no messy code.

&#43; Knife is now one time use. Otherwise it was OP.

**03.11.2019**

&#43; No more falling after death.

&#43; Enemy health

**02.11.2019**

&#43; “PickUp” loop is optimized (by calling HUD refresh at the very last). 

&#43; Found and removed the pickup open count print.

&#43; “Fire” causing repeated damage even after death fixed.

&#43; Added “PickUp” widget. Stops input as a penalty.

&#43; “PickUp” awarding is now random (for now all at 0.5)

&#43; “PickUp” after opening becomes deactivate for (5-10 seconds) //would later make it disappear

&#43; “Is pending kill” bug on “Trap Vision” fixed.

&#43; “PickUp” UI devices use fixed.

&#43; Reliability of stairs improved. Less chances of getting stuck.

&#43; “Laser” and “Trap” announcer sound added

&#43; “Smoke” time increased to 20s from 40s

&#43; “Smoke” coughing sound readded. 


**31.10.2019**

&#43; “Smoke” screen works. Turns weak for the dropper, stays strong on others. 10 seconds

&#43; “Camera” works independently on clients now!

&#43; Room, stairs collisions improved. Hopefully less going awry. 

&#43; Content files are now compressed. A very slight decrease in size.

&#45; Device Drop is unreliable when rooms are next to each other.

&#45; Joining LAN session works in Editor, not on phones

**30.10.2019**

&#43; “Camera” added

&#43; “Stealth” on/off reliability improved

&#43; “Scope” stops movement, hides “Drop Devices”, angle tilted. (what say?)

&#43; Redesigned Level selection UI.

&#43; LAN Host/Join added.

&#43; “Sword” attack has no more replication disparity issue.

&#43; “Health” is now exclusively calculated by the server. (maybe will increase server costs)

&#45; adding multiple "Camera" is glitchy. "Camera" feed is shared to all (shouldn't)

&#45; "Camera" is missed in "Trap" view

&#45; LAN hosting tested. "Joining" failed on computer, will test with another Android in morning

**28.10.2019**

&#43; “Trap” size decreased. Can be jumped over comfortably.

&#43; First room has help text on PickUps and Switch

&#43; Player name, matches (played, won, lost) saveing.

&#43; Duplicate weapon spwan fixed

&#43; Sward now damages only when attacked. No standing damage.

&#43; Seperate (placeholder) animation for punch and sword attack.

 
**27.10.2019**

&#43; Fixed all menu flow

&#43; Added "Main Menu" button in HUD

&#43; Added offline map to try, in map list

&#43; Changed "Pickup Box" textures for on/off to be more apparent

&#43; Room light on/off state replicates to all clients. Earlier it only affected local client.

&#43; Jumping works. Now you can avoid your own traps!

&#43; Scope toggle works

&#43; Increased all HUD widget size. It was very small on mobile

&#43; Added working "Fire" and "Smoke" (locally for now, ie. useless) placeholders.

&#43; "Trap" has colour change to indicate the state

&#43; Added colour to HUD to better indicate action/switch button relations (they would be icons in future)

&#43; Added emissive trim to doors to improve the mental map of stage

&#43; Proper "Match Over". Loser gets "Lost" UI. In 2 seconds players back in "Main Menu". No more need to restart app.

&#43; Server now resets itself after every match. No remnants from the previous match

&#43; Jump on touch fixed. It is aware of context. No double meaning.

&#43; “PickUp Box“ colour hints enhanced. When it is ready to be opened. 

&#45; Removed all particle effects for time being (except "Bomb"). They work fab on the desktop, but have issues with mobile.

&#45; All touches (for light, open pickup box) leed to jumps! (? long touch)?

&#45; No indicator for "Stealth" active on the user, except progress bar

&#45; "Smoke" placeholder affects only the applier. No replication 

&#45; "Scope" once acquired is not expended ever.


Developed with Unreal Engine 4
