# Tripwire_Redux

The concept in one line is 
"1v1 bomberman inspired battle royale"

Do read the Manual

Old changelogs
(since first outside test)

12.04.2020
+ Enemy health bar fixed
+ GetUserWidgetObject does not work in constructor
+ Fixed Lobby widget. Removed the delay and validity check.
+ Fixed repeated hosting failure. Added Destroy Session, before creating and joining.
+ Removed all material instances. //packaging issue solved for 4.25.6
+ Added "(test only)" to "Solo"
+ Set fps to 60. Enabled vsync
+ OMG! Internet play is working on PC.

11.04.2020
+ Server is building
+ Added Internet server IP input.
+ Added HUD Gauge Cluster. With 2 health bars and HP
+ Made all outside texture "256 x 256"
+ Added exit button to lobby.
+ Fixed entering stairs camera jerk (check and only then switch off crouch)


24.11.2019
+ Finally decided to stop trying to get lighting work. Now all rooms are statically lit and using black material for lights off.
+ Now all rooms are default lit.
+ Fixed “deices” not dropping properly (now using camera channel for line trace). 
+ The camera misbehave only happens on “Solo”. (I think)
+ Fixed. Pistol damage making enemy health bar disappear.
+ Fixed! Bomb doing multiple damage/on hit kill (Do once).
+ Fixed own overhead health bar being visible in succeeding match.
+ Fixed winner declaration.

23.11.2019
+ Decreased all texture sizes (256 x 256 from 512 x 512). To fit Google .abb size limit. (Nope! no effect).
+ Improved HUD reliability. (this caused enemy name to not appear again).+ Improved lobby lighting.
- Days of experiments has yielded the result that lights won’t work. We have to use dynamic lights and not more than 3 can ever overlap (excluding Directional Light). Hence the only way to get it to work without any ugly light bleeds is to use one light per room. This itself is ugly.
- Possible solution is to change textures of room and all objects to black, instead of switching light. Or change all room and stairs meshes for slightly better fit. 
- Stationary lights are also bugged.
- All this is because of limits of OpenGL ES and Unreal. Has always worked well on DX.
- Camera jumps if player jumps when crouched and other combos. Lighting is 🤮 Let’s just focus on gameplay now. If no solution, will have to completely remove it and add uniform light to all rooms, alway on.

22.11.2019
+ Finally fixed light bleeding through walls! (Nope!)
+ Fixed not being able to go up stairs if entered stairs while crouching.

21.11.2019
+ Fixed. Moving away from “PickUp” after “Trap” effect is over, closes it.
- Closing “PickUp” overrides “Trap”
+ If “PickUp” canceled, it is now becomes immediately available.
+ Crouching does not affect camera.
+ Jumping does not affect camera! (Slight jitter when jumped on stars ramp).
+ Mine (nee Bomb) size decreased. Easier to avoid for planter.
+ Fixed devices being deployed bellow floor on crouch and in air on jump. Using “Line Trace”. (Sometimes get deployed face high)
+ Lasers can now be jumped over.
+ Smoke revealing exploaded bombs maybe fixed.

19.11.2019
+ Fixed! Other player data correctly displays on “Lobby Wall”
+ “Room and PickUp” switch reliability improved.
+ Fixed “Sprint and Stealth” meters not resetting before the round change.
+ Fixed “Room” state not resetting on round change.
+ Fixed “Enemy Name” in HUD.
- Light bleed 😰
- Enemy overhead health bar disappears sometimes.
- “Nade” sometimes does one-hit kill.

18.11.2019
+ Fixed. Post “Trap” vision, the room light state reverts to pre “Trap” vision state.
+ In “Scope”, camera can now be controlled by the joystick.
+ Fixed. “Trap” not visible in “Room” type 3 
+ Removed useless “Punch”
+ Improved weapon switching and firing.
+ Added PickUp type colours in the flyout.
+ In “Scope”, “Device Dock” is hidden.
+ Added slight “Ability” on/of indicator.
+ “Sprint” meter stops drain on crouch.
+ Reworked “Stealth” calculation and application.
+ Added few sounds
+ Different animations for ”Run” and “Sprint” (reverted)
+ Less falling off stairs.

17.11.2019
+ Improved “PickUp” open click reliability. (Increased touch area)
+ Added “Kill Cam”
+ Modified “Levels” UI. 
+ Added “Grenade”
+ “Grenade destroys “Devices”, removes "Smoke"

16.11.2019
+ Fixed room lights not resetting on the next match (they retained their on match state).
+ Room lights changed.
+ Removed all “stairs” light
+ Added simple room textures
+ In absence of any material based indication of stealth activation on owner, using the same effect as used for remote players.
+ Improved all three room and two stair types meshes and UVs.
+ Improved stair and room fit and alignment.
+ Match data store fixed.
+ Pistol added!


15.11.2019
+ Added “crouch”
+ Fixed trap not being invisible on lights off.
+ Duplication of walk sound fixed.
- Smoke reactivates all old blasted “Bombs”
- Sprint broken

11.11.2019
+ Increased “Trap” vision time from 2s to 4s. Added “Green” light indicator.
+ “PcikUps” don’t emit light anymore. Hide when room light off.
+ Readded windowless room. Added 9th room.
+ Room textures changed (actually later removed) // check file size!
+ Replaced death explosion, with death animation (found several free packs)
+ WOW. Camera on respawn fixed. (it was simple, but where to was the trick)
+ 2s camera attached to “Laser”
+ Fixed: While one has opened “PickUp”, others don’t get “PickUP”
+ Fixed: Only “PickUps” marked “Help” opened. Hack fixed it.
+ Added fire crackling sound on “Fire”
+ Finally found lighting effect closer to vision (sharp dark and light) (using light channels) 
+ Room switch is useful because it can turn a player’s weapons against them. 
+ Simplified “Bomb” particle effects.

11.10.2019
+ Increased “Equip”, “Cancel” button sizes
+ Fixed HUD not showing on solo Local play.
+ Fixed some light issues on mobile
+ Fixed helper text appearing way behind the room switch. (attached to it)
+ Lobby Wall Display fixed using Delay nodes. Not confident of the fix.
+ “Ability” toggle reliability improved.
+ Fixed “Health” starting with 0 on respawn.
+ Added “Imersive Mode” on mobile
+ Increased the size of background wall.
- On round change, the camera persists.
- Some win situations "Lose" for both
- By mistake switched ”Help" on all the pickup boxes.

08.11.2019
+ Major modularization. All levels (Main Menu, Lobby, Game) have there own GameModes. Player Controllers, PlayerCharacters.
+ All most all code went through and some refactored 
+ Removed all UI code from Characters to their Controllers
+ Stealth should also camo foot sound.
+ “Line cross” alarm and announcement sounds.
+ Jump has sound now. No more “Bunny Hop” for a silent walk.
+ Game rounds added.
+ Options has different types of quits.
+ HUD stores relevant inventory and used for loop with a break to keep from always reaccess of the array from controller.
- On round change, the camera persists.

06.11.2019
+ Scope is now consumable.
+ Stealth/Sprint activation/deactivation is more reliable
+ Individual HUD element refresh.
+ Sprinting is smoother.
+ Bomb causes area damage (switched all custom damage handling to Engine’s system)
+ This also directly allowed “Sword” attack to work with no messy code.
+ Knife is now one time use. Otherwise it was OP.

03.11.2019
+ No more falling after death.
+ Enemy health

02.11.2019
+ “PickUp” loop is optimized (by calling HUD refresh at the very last). 
+ Found and removed the pickup open count print.
+ “Fire” causing repeated damage even after death fixed.
+ Added “PickUp” widget. Stops input as a penalty.
+ “PickUp” awarding is now random (for now all at 0.5)
+ “PickUp” after opening becomes deactivate for (5-10 seconds) //would later make it disappear
+ “Is pending kill” bug on “Trap Vision” fixed.
+ “PickUp” UI devices use fixed.
+ Reliability of stairs improved. Less chances of getting stuck.
+ “Laser” and “Trap” announcer sound added
+ “Smoke” time increased to 20s from 40s
+ “Smoke” coughing sound readded. 


31.10.2019
+ “Smoke” screen works. Turns weak for the dropper, stays strong on others. 10 seconds
+ “Camera” works independently on clients now!
+ Room, stairs collisions improved. Hopefully less going awry. 
+ Content files are now compressed. A very slight decrease in size.
- Device Drop is unreliable when rooms are next to each other.
- Joining LAN session works in Editor, not on phones

30.10.2019
+ “Camera” added
+ “Stealth” on/off reliability improved
+ “Scope” stops movement, hides “Drop Devices”, angle tilted. (what say?)
+ Redesigned Level selection UI.
+ LAN Host/Join added.
+ “Sword” attack has no more replication disparity issue.
+“Health” is now exclusively calculated by the server. (maybe will increase server costs)
- adding multiple "Camera" is glitchy. "Camera" feed is shared to all (shouldn't)
- "Camera" is missed in "Trap" view
- LAN hosting tested. "Joining" failed on computer, will test with another Android in morning

28.10.2019
+ “Trap” size decreased. Can be jumped over comfortably.
+ First room has help text on PickUps and Switch
+ Player name, matches (played, won, lost) saveing.
+ Duplicate weapon spwan fixed
+ Sward now damages only when attacked. No standing damage.
+ Seperate (placeholder) animation for punch and sword attack.

 
27.10.2019
+ Fixed all menu flow
+ Added "Main Menu" button in HUD
+ Added offline map to try, in map list
+ Changed "Pickup Box" textures for on/off to be more apparent
+ Room light on/off state replicates to all clients. Earlier it only affected local client.
+ Jumping works. Now you can avoid your own traps!
+ Scope toggle works
+ Increased all HUD widget size. It was very small on mobile
+ Added working "Fire" and "Smoke" (locally for now, ie. useless) placeholders.
+ "Trap" has colour change to indicate the state
+ Added colour to HUD to better indicate action/switch button relations (they would be icons in future)
+ Added emissive trim to doors to improve the mental map of stage
+ Proper "Match Over". Loser gets "Lost" UI. In 2 seconds players back in "Main Menu". No more need to restart app.
+ Server now resets itself after every match. No remnants from the previous match
+ Jump on touch fixed. It is aware of context. No double meaning.
+ “PickUp Box“ colour hints enhanced. When it is ready to be opened. 
- Removed all particle effects for time being (except "Bomb"). They work fab on the desktop, but have issues with mobile.
- All touches (for light, open pickup box) leed to jumps! (? long touch)?
- No indicator for "Stealth" active on the user, except progress bar
- "Smoke" placeholder affects only the applier. No replication 
- "Scope" once acquired is not expended ever.



Developed with Unreal Engine 4
