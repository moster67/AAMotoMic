# AAMotoMic - Android Auto Microphone Router for Motorcycles - version 6.0 (Beta) - January 31, 2026
# Author - tillekesoft aka tilleke/moster67

## The Problem: Why Voice Commands Fail on a Bike

If you ride a motorcycle and use Android Auto with a Bluetooth interphone (Sena, Cardo, or similar), you've probably run into this:

**You say "Hey Google" or press the voice button on your interphone, but nothing happens. Or Android Auto tries to use the microphone on your bike's head unit instead of your interphone mic.**

### Why This Happens

Android Auto is designed for cars. When you connect your phone to your bike's Android Auto head unit (Carpuride or similar), Android Auto assumes:

- The bike has a built-in microphone (like cars do)
- That microphone is the best one to use for voice commands

**On a motorcycle, this is usually wrong.**

- Your bike's microphone (if it even has one) is exposed to wind noise, engine noise, and is far from your mouth
- Your interphone mic is right by your mouth, designed for riding, and usually has noise cancellation
- Android Auto doesn't know this, so it routes your voice commands to the wrong microphone

**Result:** Voice commands often fail or are hit‑and‑miss.

### Head Unit Audio Modes (BT‑Trans / Dual Bluetooth)
Some head units (e.g., Carpuride models) offer their own audio‑routing modes like **BT‑Trans** or “dual Bluetooth.” These can work, but often introduce extra quirks:

- **BT‑Trans mode** connects your interphone directly to the head unit. In practice, this can require mic‑gain adjustments during a call, and some users report lower or less consistent mic quality. Audio also gets encoded twice (phone→head unit→interphone), which can degrade sound quality since each Bluetooth compression step loses information.
- **iPlay/Auto mode** connects your interphone to your phone instead (which is the mode this app is designed for).  
- If you use BT‑Trans, you often need to **remove the headset pairing from the phone** to avoid conflicts, and vice‑versa in iPlay/Auto mode.

In short: **BT‑Trans/dual‑BT can be a useful fallback**, but a **direct phone‑to‑interphone Bluetooth connection usually gives more reliable voice control**. This app targets that setup because it keeps the routing simpler and more consistent.

## The Solution: AAMotoMic

AAMotoMic is a simple Android app that tries to fix this. It runs in the background and when you activate Google Assistant (via "Hey Google" or your interphone's voice button), it routes the mic to your **interphone** instead of the bike's mic.

### How It Works (Simple Explanation)

Think of AAMotoMic as a traffic director for your phone's microphones:

1. **It watches for Google Assistant** - When you say "Hey Google" or press your interphone's voice button, the app tries to detect it
2. **It redirects the microphone** - Instead of letting Android Auto use the bike's mic, it switches to your interphone mic
3. **It keeps it connected** - The app keeps the connection for a short time after you finish speaking
4. **It usually runs automatically** - Once set up, you normally don't need to open the app

### Why People Use It

Unlike other solutions that require:
- Expensive hardware modules (like WHIM)
- Complex wiring
- Pairing your phone in specific ways
- Giving up features

**AAMotoMic is:**
- ✅ **Free**
- ✅ **No hardware needed** - works with your existing setup
- ✅ **Automatic** - starts when your interphone connects (if enabled)
- ✅ **Should work with common Bluetooth interphones** - Cardo, Sena, UClear, etc.
- ✅ **Should work with Android Auto head units** - Carpuride, etc.

## Who Needs This App?

You need AAMotoMic if you:

- Ride a motorcycle with an Android Auto head unit
- Use a Bluetooth interphone (Cardo Packtalk, Sena, etc.)
- Want to use Google Assistant voice commands while riding
- Want to make phone calls through your interphone
- Want to control music and navigation with your voice
- Are frustrated that voice commands don't work on your bike

**Important note:** Not all interphones support “Hey Google” voice activation. Interphones that can trigger voice commands via a physical button should work best, because Android Auto usually owns the microphone while connected. In practice, having a button to trigger voice commands is probably necessary for reliable use. See also the section below about Handlebar Bluetooth Remote devices which can be a convenient alternative. 

## Features

### Automatic Operation
- **Auto-Start**: Automatically starts when your interphone connects (can be disabled)
- **Background Service**: Runs silently in the background - no need to keep the app open
- **Smart Detection**: Automatically detects when Google Assistant is activated

### Easy Configuration
- **Simple Setup**: Just scan for your interphone and select it - that's it!
- **Fine-Tuning Options**: Advanced users can adjust timing settings for optimal performance
- **Diagnostic Logging**: Built-in diagnostic log viewer to help troubleshoot issues (access via the menu)

### Reliable Performance
- **Works with Music**: Special handling reduces music playback issues when changing songs
- **Battery Efficient**: Smart polling only when needed
- **Stable**: Handles disconnections and reconnections gracefully

## Installing the app

AAMotoMic is installed by opening an APK (sideload). You need to allow installs from outside the Play Store first.

1. **Get the APK** – Download from the Releases page.
2. **Allow install from unknown sources:**
   - **Android 8–9:** Settings → Security (or Apps & notifications) → **Unknown sources** or **Install unknown apps** → turn on. (Menu names vary by brand.)
   - **Android 10+:** Settings → Apps → **Special app access** → **Install unknown apps** → select the app that will open the APK (e.g. Chrome, Files) → **Allow from this source**.
3. **Install** – Open the APK (from Downloads or your file manager) and tap **Install**.

**Optional:** If the service stops when the app is in the background, set AAMotoMic’s battery option to **Unrestricted** (Settings → Apps → AAMotoMic → Battery). On some brands you may also need to allow the app to **Auto-start** or **Run in background**.

## How to Use

### Initial Setup (One Time)

1. **Install the app** (see **Installing the app** above if you haven’t yet).
2. **Open the app** – you’ll see the main screen.
3. **Grant permissions** when prompted: Bluetooth and Microphone.
4. **Tap "SCAN"** to find your interphone.
5. **Select your interphone** from the list (e.g. "Cardo Packtalk Bold" or "Sena 20S").
6. **Tap "SAVE & RESTART SERVICE"**.

Done. The app will work whenever your interphone connects.

### Daily Use

**With Auto-Start enabled (default):**
- Just turn on your interphone - the app starts automatically
- Use voice commands normally - they'll work through your interphone mic
- No need to open the app

**With Auto-Start disabled:**
- Open the app when you want to use voice commands
- Tap "START SERVICE" to activate
- Tap "STOP SERVICE" when done

## Settings Explained

### Check Interval
**What it does:** How often the app checks if Google Assistant is active when you're not using it.

**Recommendation:** Use "Default" (1000ms) for most users. Faster = quicker detection but uses more battery. Slower = better battery life but may take slightly longer to detect.

**Note:** Once Assistant is active, the app automatically checks very quickly regardless of this setting.

### Release Delay (Music Resume Speed)
**What it does:** How long the app keeps the microphone connection after Google Assistant finishes speaking.

**Why it matters:** When you ask to play a new song while music is playing, Android Auto might try to resume the old song if the connection drops too quickly. A longer delay gives the new song time to start before Android Auto interferes.

**Recommendation:** Use "Default" (5 seconds) for most users. If you want faster response, try "Standard" (3 seconds). If songs sometimes resume incorrectly, try "Very Safe" (10 seconds).

## Troubleshooting

### Install Blocked or "Can't install"
Allow **Install unknown apps** for the app that opens the APK (e.g. Chrome or Files). See **Installing the app** above.

### Voice Commands Still Don't Work

1. **Check the status** - The app should show "STATUS: ACTIVE" when your interphone is connected
2. **Verify your interphone is selected** - Make sure the correct device MAC address is shown
3. **Check permissions** - Ensure Bluetooth and Microphone permissions are granted
4. **Restart the service** - Tap "SAVE & RESTART SERVICE" to restart

### Service Won't Start

1. **Check Auto-Start setting** - Make sure the Auto-Start checkbox is enabled
2. **Verify interphone is paired** - Your interphone must be paired with your phone in Android Bluetooth settings
3. **Check diagnostic log** - Open the Diagnostic Log viewer (Menu > View Diagnostic Log) and look for error messages

### Music Issues When Changing Songs

1. **Increase Release Delay** - Try "Safe" (5 seconds) or "Very Safe" (10 seconds)
2. **Check diagnostic log** - Open the Diagnostic Log viewer and look for messages about device connection

### Navigation Announcements Cause Brief Audio Interruptions

When Android Auto plays navigation announcements (e.g., "Turn left ahead"), you may notice your music briefly mutes and you hear a beep when it resumes. This is expected behavior - the app cannot distinguish navigation audio from Google Assistant audio. The navigation still plays correctly through your interphone.

## Help Wanted: Gemini Live Testers

If you have access to **Gemini Live** ("Let's talk" feature) on Android Auto, I need your help!

Gemini Live is currently rolling out to users gradually (server-side). The app may not yet support Gemini Live conversations, and I need data about how Android signals when Live mode is active.

**If you have Gemini Live available:**
1. Make sure diagnostic logging is enabled (Menu > check that logging is not paused)
2. Start a Gemini Live session by saying "Let's talk" or "Let's talk Live"
3. Have a short conversation
4. Open the Diagnostic Log viewer (Menu > View Diagnostic Log)
5. Copy the log using the menu - you can choose "Copy Sanitized Log" for a privacy-safe version (MAC addresses and device names are anonymized) or "Copy Full Log" if you prefer
6. Share the log with me via GitHub Issues or the XDA thread

Your logs can help me add support for Gemini Live. Thank you!

## Compatibility

- **Android Version**: Android 7.0 (API 24) or higher
- **Android Auto**: Should work with Android Auto head units
- **Bluetooth Interphones**: Should work with Bluetooth headset/interphone (Cardo, Sena, UClear, etc.)
- **Phones**: Any Android phone that supports Android Auto

## Optional: Handlebar Bluetooth Remote

You can probably use a **Bluetooth handlebar remote** to trigger Google Assistant instead of (or in addition to) your interphone's voice button. These small remotes mount on your handlebar and are easier to reach while riding.

### How It Works

Handlebar remotes with a "voice assistant" button use the Bluetooth HFP protocol (specifically the AT+BVRA command) to trigger Google Assistant on your phone. AAMotoMic should detect when Assistant activates - regardless of how it was triggered - and routes the microphone to your interphone.

```
[Press voice button on handlebar remote]
              |
              v
[Google Assistant starts on your phone]
              |
              v
[AAMotoMic detects Assistant is active]
              |
              v
[Mic is routed to your interphone]
              |
              v
[You speak into your helmet mic as usual]
```

### Benefits

- **Easier to reach** - Button is on your handlebar, not on your helmet
- **Works with gloves** - Larger buttons are easier to press
- **Media controls** - Most remotes also have volume and track skip buttons
- **No code changes needed** - AAMotoMic should work with these remotes out of the box

### What to Look For

When buying a handlebar remote, make sure it has:
- A **voice assistant button** (often activated by long-pressing the main button)
- **Bluetooth HFP support** (most remotes that advertise "voice assistant" have this)
- **Waterproof rating** (IP65 or higher recommended for motorcycle use)

The remote connects to your phone via Bluetooth, while your interphone remains connected as well. Most modern phones handle multiple Bluetooth connections without issues.

## Known Limitations & Gemini Notes

- The app must be running for voice commands to work through your interphone
- Some very old Android versions may have limited functionality
- The app works best when your interphone is the primary Bluetooth audio device
- **Issue 1: Multi-turn conversations can be cut off**  
  If Gemini (or Google Assistant) asks a follow-up question (e.g., “Do you want a longer story?”), the app may release the mic after the configured Release Delay because it detects silence. This can cause the follow-up response to be missed. This is a platform limitation: Gemini doesn’t always signal that it is still waiting for you.
- **Issue 2: “Unlock phone” requests**  
  Even with “Making calls without unlocking” and “Sending messages without unlocking” enabled, Gemini can still require unlock for actions involving personal data (emails, calendar, sensitive searches, security devices, etc.). This is a Gemini policy, not an issue in the app.
- **Gemini Live (“Let’s talk”) may need longer delays**  
  Live conversations are continuous and can include natural pauses. The app currently uses a Release Delay and a 30‑second safety timeout when music was playing. This can interrupt long Live chats. Workarounds: increase Release Delay, avoid playing music during Live conversations, or be ready to re‑start the service if it drops.

## Support

If you encounter issues or have questions:

1. Check the diagnostic log (Menu > View Diagnostic Log) for error messages
2. Verify your interphone is properly paired with your phone
3. Ensure all permissions are granted
4. Try restarting the service

## Credits

AAMotoMic was created to solve a real-world problem faced by motorcycle riders who want to use Android Auto safely and effectively. The app is free to use.

**Ride safe, and enjoy hands-free voice control on your motorcycle!** 





## Technical Details (For Advanced Users)

### How It Works Technically

AAMotoMic uses Android's Bluetooth SCO (Synchronous Connection-Oriented) protocol to force "phone call mode" when Google Assistant activates. This mode has higher priority than Android Auto's media routing, allowing the app to override Android Auto's microphone selection.

The app monitors for:
- Audio recording activity (when Assistant is listening)
- Audio playback with Assistant usage IDs (when Assistant is speaking)
- Bluetooth device connections/disconnections

When Assistant activates, the app:
1. Forces Bluetooth SCO connection
2. Sets the communication device to your interphone
3. Maintains the connection until Assistant finishes
4. For music scenarios, holds the connection longer to prevent Android Auto from resuming old tracks

### Permissions Explained

- **Bluetooth**: Required to detect when your interphone connects and to route audio
- **Microphone**: Required to detect when Google Assistant is listening (the app doesn't record audio)
- **Modify Audio Settings**: Required to change which microphone Android uses
- **Foreground Service**: Required to keep the app running in the background

### Navigation Audio Ducking Behavior

You may notice that when Android Auto plays navigation announcements (e.g., "Alternative route available," "Traffic ahead") or beeps (e.g., when you deviate from the route), your music briefly mutes, you hear the announcement/beep clearly, then hear a beep when it ends and music resumes.

**What's happening technically:**

1. **Navigation audio starts** → Android Auto requests audio focus for the announcement/beep
2. **AAMotoMic interprets this as potential Assistant activity** → The app monitors audio playback and sees activity that resembles Google Assistant
3. **SCO connection opens** → AAMotoMic activates Bluetooth SCO (phone call mode) to route audio through your interphone
4. **Music gets ducked/muted** → SCO takes over the audio channel, muting your music
5. **Navigation plays through SCO** → This is why you hear it in "good quality" rather than normal media audio
6. **Release delay timer expires** → After the configured delay (default 3 seconds), AAMotoMic releases the connection
7. **SCO disconnects** → You hear the disconnect beep
8. **Music resumes** → Normal A2DP audio streaming returns

**Why this happens:**

AAMotoMic cannot reliably distinguish between Google Assistant speaking (which SHOULD trigger SCO routing for two-way conversation) and navigation announcements (which should NOT trigger SCO routing since no mic is needed). Both use similar Android audio APIs and attributes.

The app is designed to be aggressive about detecting Assistant activity to ensure voice commands work properly, which leads to these false positives during one-way navigation announcements.

**The technical dilemma:**

Android's audio system doesn't provide a clear signal to apps indicating "this audio expects a voice response" versus "this is just an announcement." AAMotoMic must make educated guesses based on indirect signals like audio recording activity and playback attributes, which inevitably leads to some false positives.

**Potential mitigation approaches (for future consideration):**

- **Check recording activity first** - Only activate SCO if `AudioManager.isRecording` returns true, indicating a microphone is actually needed. However, this might miss some legitimate voice command scenarios.
-wi
- **User-controlled navigation mode** - Allow users to temporarily disable the service when only navigating without needing voice commands.

This behavior is an inherent trade-off: ensuring reliable voice command routing means occasionally activating SCO for navigation audio that doesn't need it.

### Gemini Live Detection (Research in Progress)

Gemini Live ("Let's talk") presents a unique challenge because it's a continuous, free-flowing conversation rather than a single command-response cycle. The app needs to keep the microphone routed to the interphone for the entire Live session, which can last several minutes.

**Current detection approach:**
The app currently detects Assistant activity by monitoring:
- `AudioManager.isRecording` - Returns true when any app is recording audio
- Audio playback with specific usage attributes (e.g., `USAGE_ASSISTANT`)

**The challenge with Gemini Live:**
During a Live session, there are natural pauses in conversation where neither party is speaking. During these pauses, `isRecording` may return false and no Assistant audio is playing, causing the app to think the session has ended and release the microphone prematurely.

**Potential detection strategies being investigated:**
1. **Different AudioAttributes**: Gemini Live may use different audio usage flags or content types that distinguish it from regular Assistant interactions
2. **Longer active playback patterns**: Live sessions may have characteristic patterns in how audio is played back (longer durations, different intervals)
3. **Process/package detection**: Checking if specific Gemini Live processes or activities are running
4. **AudioFocus changes**: Live mode may request or hold audio focus differently than standard Assistant
5. **Notification or broadcast intents**: Google may broadcast intents when Live mode starts/stops

**How diagnostic logs help:**
The diagnostic logging captures audio state changes, playback usage flags, and timing information. By analyzing logs from users who have Gemini Live, we can identify unique signatures that indicate Live mode is active, allowing the app to extend the microphone hold time appropriately.



