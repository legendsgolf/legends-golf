# Golf Tournament System - Administrator's Guide

## QUICK START

### Your First Tournament (10 minutes)

1. **Open** `golf-tournament-SIMPLE-SETUP.html`
2. **Click** "ONE-CLICK SETUP" 
3. **Open** `admin-controls.html`
4. **Set** number of rounds (1-6)
5. **Open** Round 1
6. **You're ready!**

---

## FILE OVERVIEW

### Core Admin Files
- **`index.html`** - Start here! Navigation hub
- **`admin-controls.html`** - Master control panel (toggles, rounds, notices)
- **`golf-tournament-admin.html`** - Main admin (setup, players, scorecards)
- **`presentation.html`** - Winner announcements (password: `admin-presentation-2026`)

### Setup & Groups
- **`golf-tournament-SIMPLE-SETUP.html`** - Test data generator
- **`team-management.html`** - Create Best Ball/Ambrose teams
- **`group-generator.html`** - Auto tee times by score

### Viewing Results (Admin)
- **`stableford-leaderboard.html`** - Stableford results
- **`skins-leaderboard.html`** - Skins with hole lookup
- **`team-results.html`** - Team competition results
- **`eclectic.html`** - Best per hole across rounds
- **`special-prizes.html`** - Long drives & nearest pin

### Player Files (Give to Players)
- **`golf-tournament-player.html`** - Score entry
- **`player-leaderboard.html`** - Live standings (if enabled)
- **`reveal-leaderboards.html`** - Final results (if revealed)

### Documentation
- **`player-guide.html`** - What players see (show them this!)
- **`TESTING-GUIDE.md`** - Testing checklist

---

## COMPLETE TOURNAMENT WORKFLOW

### PRE-TOURNAMENT SETUP

#### Step 1: Configure Tournament
1. Open `golf-tournament-admin.html`
2. Go to **Tournament Setup** tab
3. Enter:
   - Tournament name
   - Number of rounds (1-6)
   - Max players (up to 48)
4. Click **Save Tournament Settings**

#### Step 2: Configure Course
1. Go to **Course Setup** tab
2. Enter:
   - Course name
   - Slope rating (default 113)
   - Course rating (default 72)
   - Par (default 72)
3. Click **Save Course Settings**
4. Customize each hole:
   - Par (3, 4, or 5)
   - Stroke Index (1-18)
5. Click **Save Hole Configuration**

#### Step 3: Add Players
1. Go to **Players** tab
2. For each player, enter:
   - Name
   - GA Handicap Index
3. Click **Add Player**
4. System auto-calculates playing handicap

**OR** use test data:
1. Go to **Data Management** tab
2. Click **Generate Test Players**
3. Select number (4-16 players)

#### Step 4: Set Up Admin Controls
1. Open `admin-controls.html`
2. Set **Number of Rounds** (1-6)
3. Click **Apply Day Configuration**
4. **Open Round 1** for scoring
5. Keep other rounds **closed**

---

### ROUND DAY WORKFLOW

#### Morning: Before Play

##### 1. Generate Groups (Optional but Recommended)
1. Open `group-generator.html`
2. Select round
3. Choose group size (2/3/4-ball)
4. Set first tee time
5. Set interval (usually 10 min)
6. Click **Generate Groups**
7. Click **Save Groups**
8. Click **Export as Text** for printing

**How it works:**
- **Round 1**: Groups by handicap (high → low)
- **Round 2+**: Groups by cumulative score (worst → best)
- Worst scores tee off first, best scores last

##### 2. Post Notice (If Needed)
1. Open `admin-controls.html`
2. Scroll to **Admin Notice Board**
3. Enter title & message
4. Click **Post Notice**
5. Players see it immediately

##### 3. Enable Live Leaderboard (Optional)
1. In `admin-controls.html`
2. Toggle **Live Leaderboard** to ON
3. Players can now track standings during play

---

#### During Play: Score Entry

**Players enter scores on their phones:**
1. Open `golf-tournament-player.html`
2. Select name and round
3. Select playing partner
4. Enter scores (auto-saves)
5. Stableford points appear instantly

**Anti-cheat system:**
- Player A enters: Their scores + Partner B's scores
- Player B enters: Their scores + Partner A's scores
- Must match before you can accept

**What if players don't have phones?**
- Set up tablet/laptop at clubhouse
- Players enter scores after their round
- Still works perfectly!

---

#### After Play: Scorecard Review

##### 1. Review Scorecards
1. Open `golf-tournament-admin.html`
2. Go to **Scorecard Acceptance** tab
3. Select the round
4. Review each scorecard:
   - Green = scores match
   - Red = mismatch (investigate)

##### 2. Accept Scorecards
- Click **Accept** for validated cards
- Cards lock immediately
- Players can't edit after acceptance

##### 3. Close the Round
1. Go to **Rounds** tab
2. Click **Close Round**
3. Confirms: "Round X is now closed"
4. ALL scores permanently locked

---

#### Evening: Presentations

##### 1. View Results (Your Preview)
Check each leaderboard:
- `stableford-leaderboard.html` - Main competition
- `skins-leaderboard.html` - Skins winners
- `team-results.html` - Team competitions
- `eclectic.html` - Best holes
- `special-prizes.html` - Long drives, NTP

##### 2. Enter Special Prizes
1. Open `special-prizes.html`
2. **Long Drive** tab:
   - Set handicap cutoff (default 18)
   - Enter winner below cutoff + hole
   - Enter winner above cutoff + hole
3. **Nearest to Pin** tab:
   - Click **Add NTP Hole**
   - Enter hole, winner, distance
   - Repeat for each par 3
4. Click **Save**

##### 3. Present to Players
1. Open `presentation.html` (password: `admin-presentation-2026`)
2. Select **Daily Results**
3. Select the round
4. Click through each competition:
   - Net Stableford (podium display)
   - Gross Stableford
   - Net Skins (with hole details)
   - Gross Skins
   - Best Ball teams
   - Eclectic leaders
   - Special prizes
5. Click **Print Presentation** for handouts

##### 4. Reveal to Players (Optional)
If you want players to see results on their devices:

1. Open `admin-controls.html`
2. Toggle **Daily Final Leaderboard** to ON
3. Players can now view `reveal-leaderboards.html`
4. Creates excitement!

---

### MULTI-ROUND TOURNAMENTS

#### Before Round 2

##### 1. Open Next Round
1. Open `admin-controls.html`
2. Find "Round 2"
3. Click **Open Round**
4. Status changes to 🔓 OPEN

##### 2. Generate Groups
1. Open `group-generator.html`
2. Select Round 2
3. Click **Generate Groups**
4. System automatically ranks by cumulative scores
5. Worst total scores tee off first

##### 3. Post Schedule Notice
Example notice:
```
Title: Round 2 Tee Times
Message: Round 2 starts tomorrow at 8am.
Check the notice board for your tee time.
Groups are based on Round 1 standings.
```

#### After All Rounds

##### 1. View Overall Results
1. Open `presentation.html`
2. Click **Overall Tournament** tab
3. Shows cumulative winners:
   - Overall Net Stableford
   - Overall Gross Stableford
   - Overall Net Skins
   - Overall Gross Skins
   - Overall Eclectic

##### 2. Reveal Overall Results
1. Open `admin-controls.html`
2. Toggle **Overall Final Leaderboard** to ON
3. Players can view final standings

---

## TEAM COMPETITIONS

### Best Ball (4BBB)

**Setup:**
1. Open `team-management.html`
2. Click **Best Ball Teams** tab
3. Select round
4. Check 2-4 players
5. Click **Create Team**
6. Repeat for all teams

**How it works:**
- Uses individual player scores (already entered)
- System takes best Stableford score per hole
- Auto-calculates team total

**View results:**
- Open `team-results.html`
- Select round
- See team rankings

### Ambrose/Scramble

**Setup:**
1. Open `team-management.html`
2. Click **Ambrose Teams** tab
3. Select round
4. Check **Enable Ambrose Skins** (optional)
5. Check 2-4 players
6. Click **Create Team**
7. System auto-calculates team handicap:
   - 2 players: Total HCP ÷ 4
   - 3 players: Total HCP ÷ 6
   - 4 players: Total HCP ÷ 8

**Note:** Ambrose requires manual team score entry (coming soon)

---

## TROUBLESHOOTING

### Players Can't See Leaderboard
**Check:**
1. Is it enabled in `admin-controls.html`?
2. Have they refreshed their browser?
3. Are they on the right URL?

### Scores Won't Save
**Check:**
1. Is round open in `admin-controls.html`?
2. Did player select a partner?
3. Is browser localStorage enabled?
4. Try refreshing page

### Leaderboard Shows Wrong Scores
**Check:**
1. Have you accepted scorecards?
2. Have you closed the round?
3. Try refreshing page
4. Check specific player in admin panel

### Data Lost After Browser Close
**Cause:** localStorage cleared or browser private mode
**Solution:**
1. Use **Data Management → Export to JSON**
2. Save file as backup
3. Import if needed

---

## BEST PRACTICES

### Daily Routine
✓ Generate groups night before
✓ Print groups + hand out
✓ Post morning notice with tee times
✓ Enable live leaderboard if desired
✓ Review scorecards after play
✓ Accept & close round same day
✓ Present winners at dinner
✓ Export data as backup

### Data Management
✓ Export JSON daily
✓ Keep backups on USB/email
✓ Test import before tournament
✓ Have backup laptop ready

### Player Communication
✓ Show them `player-guide.html` before tournament
✓ Explain partner validation system
✓ Tell them scores auto-save
✓ Remind about phone reception (doesn't matter!)
✓ Post notice if weather/changes

---

## ADMIN PASSWORDS & KEYS

**Presentation Page:** `admin-presentation-2026`
- Required to access `presentation.html`
- Keeps players from seeing early
- Session-based (resets when browser closes)

---

## ADMIN SHORTCUTS

### Quick Links (Bookmark These)
- **Primary:** `admin-controls.html` (your main hub)
- **Scoring:** `golf-tournament-admin.html` (scorecard acceptance)
- **Groups:** `group-generator.html` (tee times)
- **Present:** `presentation.html` (winner announcements)

### Keyboard Shortcuts
- **Ctrl+Shift+R**: Hard refresh (if page acts weird)
- **F12**: Open browser console (for troubleshooting)
- **Ctrl+P**: Print presentation page

---

## ADVANCED FEATURES

### Countback System
Automatic for Stableford ties:
1. Back 9 points
2. Back 6 points
3. Back 3 points
4. Last hole points

### Hole Lookup Tool
In `skins-leaderboard.html`:
- Enter any hole number
- See ALL players' scores
- Verify skins winners
- Resolve disputes

### Custom Export
In `group-generator.html`:
- Export as text file
- Print for posting
- Email to players

---

## SUPPORT

### If Something Goes Wrong
1. **Check** `TESTING-GUIDE.md`
2. **Try** different browser
3. **Refresh** the page
4. **Restart** from SIMPLE-SETUP
5. **Import** backup if you have one

### Browser Console Errors
1. Press **F12**
2. Click **Console** tab
3. Look for red errors
4. Take screenshot if needed

---

## SUCCESS CHECKLIST

Before tournament:
- [ ] Tournament configured
- [ ] Course configured  
- [ ] All players added
- [ ] Test with SIMPLE-SETUP
- [ ] Show players the player guide
- [ ] Backup data exported

During tournament:
- [ ] Rounds opened as needed
- [ ] Scorecards accepted daily
- [ ] Rounds closed after acceptance
- [ ] Groups generated for next day
- [ ] Notices posted as needed

After tournament:
- [ ] All scorecards accepted
- [ ] All rounds closed
- [ ] Winners presented
- [ ] Final data exported
- [ ] Files saved for records

---

## CONCLUSION

This system is designed to make tournament administration easy and professional. The key is:

1. **Open rounds** when ready for play
2. **Accept cards** after validation
3. **Close rounds** to lock scores
4. **Toggle visibility** for excitement
5. **Present winners** with confidence

Everything else is automatic!

**Questions? Check `TESTING-GUIDE.md` or start with `index.html`**

---

## ⚠️ CRITICAL WARNINGS & DON'T DOS

### 🚨 DATA LOSS PREVENTION

#### DON'T Clear Browser Data
**❌ NEVER:**
- Clear browser cache during tournament
- Clear browsing data/history
- Use "Clear site data" in browser settings
- Delete cookies if system is working

**✅ SAFE TO CLEAR:**
- Regular browsing history (other sites)
- Downloads folder
- Form data from other sites

**⚠️ IF YOU MUST CLEAR:**
1. **FIRST** export tournament data
2. Save JSON file somewhere safe
3. Then clear browser data
4. Re-import JSON file after

#### DON'T Use Private/Incognito Mode
**❌ NEVER** run tournament in:
- Incognito mode
- Private browsing
- Guest mode

**WHY:** These modes delete localStorage when closed = ALL DATA LOST

#### DON'T Switch Browsers Mid-Tournament
**❌ PROBLEM:**
- Tournament data in Chrome doesn't appear in Firefox
- Each browser has separate localStorage
- Data appears "lost" but it's just in different browser

**✅ SOLUTION:**
1. Pick ONE browser (Chrome/Edge recommended)
2. Use ONLY that browser for entire tournament
3. Bookmark ALL pages in that browser
4. If you must switch: Export → Switch → Import

#### DON'T Close Round Too Early
**❌ ONCE CLOSED, YOU CANNOT:**
- Reopen the round
- Edit any scores
- Add missing players
- Fix mistakes

**✅ BEFORE CLOSING, VERIFY:**
- [ ] All players have entered scores
- [ ] All scorecards accepted
- [ ] All scores are correct
- [ ] Special prizes entered (if applicable)
- [ ] Teams created (if applicable)

**🆘 IF YOU CLOSE BY MISTAKE:**
1. Export current data immediately
2. Open JSON file in text editor
3. Find the round's "locked" property
4. Change `"locked": true` to `"locked": false`
5. Save file
6. Import back into system
7. (This is advanced - test first!)

#### DON'T Accept Scorecard With Errors
**❌ ONCE ACCEPTED, YOU CANNOT:**
- Edit the scores
- Change who entered it
- Undo acceptance easily

**✅ BEFORE ACCEPTING:**
- [ ] Scores match between partners
- [ ] No blank holes (unless DNS/WDR)
- [ ] Numbers look reasonable
- [ ] Stableford points calculated correctly

**🆘 IF YOU ACCEPT BY MISTAKE:**
1. DON'T close the round yet
2. Export data
3. Manually edit JSON file (advanced)
4. Or: Have player re-enter via new partner pairing

#### DON'T Delete Players Mid-Tournament
**❌ NEVER DELETE A PLAYER WHO:**
- Has entered any scores
- Is in any team
- Has completed any round

**WHY:** Their historical scores will disappear from leaderboards

**✅ IF PLAYER WITHDRAWS:**
1. Keep them in system
2. Don't enter scores for remaining rounds
3. Their completed rounds stay in results

---

## 💾 DATA PRESERVATION & HISTORICAL RECORDS

### Automatic Data Storage

**What Gets Saved Automatically:**
✅ All player information (name, handicap)
✅ All course configuration (par, SI, ratings)
✅ All scores from all rounds
✅ All accepted scorecards
✅ Round status (open/closed/locked)
✅ Tournament settings
✅ Team configurations (Best Ball, Ambrose)
✅ Generated groups for each round
✅ Admin control settings
✅ Posted notices

**Where It's Stored:**
- Browser's localStorage
- Limit: ~5-10MB (enough for 48 players × 6 rounds)
- Persists until manually cleared
- Separate per browser

**What Does NOT Sync:**
❌ Data doesn't sync between devices
❌ Data doesn't sync between browsers
❌ Data doesn't upload to cloud
❌ Data doesn't auto-backup

**This means:**
- Each device is independent
- Admin's laptop has the "master" data
- Players' phones have their own entries
- Must export to combine or backup

---

### Historical Data Retention

#### All Past Rounds Are Kept
**✅ PRESERVED FOREVER:**
- Round 1 scores (even after closing)
- Round 2 scores (even after closing)
- Round 3, 4, 5, 6... all stay
- Cumulative totals calculated automatically
- Overall leaderboards include all rounds

**View Historical Data:**
1. **Overall Leaderboards:**
   - `stableford-leaderboard.html` → Overall tab
   - `skins-leaderboard.html` → Overall tab
   - Shows cumulative across all rounds

2. **Daily Results:**
   - `presentation.html` → Daily Results
   - Select any past round
   - See that specific round's winners

3. **Eclectic:**
   - `eclectic.html`
   - Shows best holes across ALL rounds
   - Updates automatically each round

**⚠️ Historical Data Only Safe If:**
- You don't clear browser data
- You export backups regularly
- You use same browser/device

---

### Backup Strategy (CRITICAL!)

#### Daily Export Routine
**🔴 DO THIS EVERY NIGHT:**

1. Open `golf-tournament-admin.html`
2. Go to **Data Management** tab
3. Click **Export to JSON**
4. File downloads: `tournament-data-YYYY-MM-DD.json`
5. Save to THREE places:
   - Computer's Documents folder
   - USB drive
   - Email to yourself
   - Cloud storage (Dropbox/Google Drive)

**WHY THREE COPIES:**
- Laptop crashes? → USB backup
- USB lost? → Email backup  
- Email deleted? → Cloud backup

#### Backup Naming Convention
```
tournament-data-2026-02-19-after-round-1.json
tournament-data-2026-02-20-after-round-2.json
tournament-data-2026-02-21-after-round-3.json
tournament-data-2026-02-22-FINAL.json
```

Benefits:
- Easy to identify which backup
- Can restore to specific point in time
- Can compare if issues arise

#### What Gets Exported
**JSON file contains:**
✅ Complete tournament configuration
✅ All players with handicaps
✅ Course setup (all holes)
✅ Every round's scores
✅ Scorecard validation status
✅ Round open/closed status
✅ Teams (Best Ball, Ambrose)
✅ Timestamp of export

**JSON file does NOT contain:**
❌ Admin control settings (toggles)
❌ Generated groups
❌ Special prizes (Long Drive, NTP)
❌ Posted notices

**To backup EVERYTHING:**
1. Export main JSON (as above)
2. Also export from `admin-controls.html`:
   - Take screenshot of toggles
   - Copy-paste notices to text file
3. Export from `group-generator.html`:
   - Click "Export as Text" for each round's groups
4. Export from `special-prizes.html`:
   - Take screenshot of prizes entered

---

### Disaster Recovery

#### Scenario 1: Browser Crashed
**Recovery:**
1. Reopen same browser
2. Data should still be there (localStorage persists)
3. If not: Import most recent JSON

#### Scenario 2: Computer Died
**Recovery:**
1. Use backup laptop
2. Open files on USB drive
3. Open `golf-tournament-admin.html`
4. Import JSON file
5. Continue tournament

#### Scenario 3: Accidentally Cleared Data
**Recovery:**
1. DON'T PANIC
2. DON'T enter anything new
3. Close browser immediately
4. Import most recent JSON
5. May lose only today's work

#### Scenario 4: Need to Move to Different Computer
**Planned Migration:**
1. Export JSON on Computer A
2. Copy JSON to USB/email
3. Open system on Computer B
4. Import JSON
5. ALL data restored exactly

---

### Multi-Device Coordination

#### Problem: Players Enter on Their Phones
**What Happens:**
- John's scores saved on John's phone
- Sarah's scores saved on Sarah's phone
- Admin laptop has NEITHER

**Solutions:**

**Option A: Single Device Entry (Recommended)**
- Everyone uses admin's laptop/tablet
- Set up at clubhouse
- Players enter after their round
- All data in one place automatically

**Option B: Export/Import from Phones**
- Each player exports their JSON after entering
- Player emails/texts JSON to admin
- Admin imports each JSON
- System merges the data
- (More complex, test this before tournament!)

**Option C: Share Admin Device Link**
- Put admin laptop on table
- Players enter on admin laptop
- One at a time
- Data stays centralized

---

### Long-Term Archival

#### After Tournament Ends
**Create Master Archive:**

1. **Export final JSON** with name:
   ```
   Spring-Championship-2026-FINAL-COMPLETE.json
   ```

2. **Create Archive Folder:**
   ```
   Spring-Championship-2026/
   ├── tournament-data-FINAL.json
   ├── round-1-groups.txt
   ├── round-2-groups.txt
   ├── round-3-groups.txt
   ├── special-prizes-notes.txt
   ├── final-presentation-screenshot.png
   └── README.txt (notes about tournament)
   ```

3. **Save Archive:**
   - Burn to DVD (lasts decades)
   - External hard drive
   - Cloud storage
   - Multiple locations

4. **Test Archive:**
   - Import JSON one year later
   - Verify all data intact
   - View historical leaderboards
   - Confirm everything works

#### Viewing Historical Tournaments
**To view old tournament:**
1. Open `golf-tournament-admin.html`
2. Import old JSON file
3. View all leaderboards
4. See all scorecards
5. Generate presentations
6. All data is there!

**⚠️ WARNING:**
- Importing REPLACES current data
- Export current tournament first if active
- Or use different browser for archives

---

## 🎯 PRE-TOURNAMENT CHECKLIST

**One Week Before:**
- [ ] Install system on tournament laptop
- [ ] Test SIMPLE-SETUP works
- [ ] Practice export/import
- [ ] Test on phone (if players using phones)
- [ ] Prepare USB backup drive
- [ ] Bookmark all admin pages
- [ ] Print player guide for handout

**Night Before:**
- [ ] Set up tournament (name, players, course)
- [ ] Export initial JSON backup
- [ ] Generate Round 1 groups
- [ ] Print group sheets
- [ ] Test admin controls toggles
- [ ] Post first notice (welcome message)

**Each Morning:**
- [ ] Verify yesterday's backup exists
- [ ] Open today's round
- [ ] Post tee times notice
- [ ] Set leaderboard visibility as desired
- [ ] Have laptop charged and ready

**Each Evening:**
- [ ] Accept all scorecards
- [ ] Close the round (verify first!)
- [ ] Export JSON backup (CRITICAL!)
- [ ] Save backup to USB + email
- [ ] Enter special prizes
- [ ] Present winners
- [ ] Generate next day's groups

**Final Day:**
- [ ] Close final round
- [ ] Export FINAL backup
- [ ] Present overall winners
- [ ] Create archive folder
- [ ] Save multiple backup locations
- [ ] Test archive import works

---

## 📋 ADMIN RESPONSIBILITIES

### What Admin MUST Do
✅ Export backups daily (non-negotiable)
✅ Verify scorecards before accepting
✅ Double-check before closing rounds
✅ Use same browser throughout
✅ Keep laptop charged
✅ Communicate clearly with players

### What Admin Should NOT Do
❌ Clear browser data during event
❌ Switch browsers mid-tournament
❌ Close rounds prematurely
❌ Delete players who have scores
❌ Accept unvalidated scorecards
❌ Forget to backup data

### Admin's Golden Rule
> **"If in doubt, export a backup first"**

Before ANY major action:
- Accepting many scorecards? Export first.
- Closing a round? Export first.
- Making changes? Export first.
- Trying something new? Export first.

---

## 🆘 EMERGENCY CONTACTS

**If System Fails:**
1. Check `TESTING-GUIDE.md`
2. Check `ADMIN-GUIDE.md` (this file)
3. Import most recent backup
4. Use backup laptop if hardware fails
5. Fall back to paper scorecards if needed

**Keep Ready:**
- Backup laptop with system installed
- USB drive with latest backup
- Paper scorecards (emergency fallback)
- Phone with backup email access

---

## ✅ ADMIN SUCCESS METRICS

**You're doing it right if:**
✓ Daily backups exist for every round
✓ All players can enter scores easily
✓ Scorecards validate correctly
✓ Leaderboards match your calculations
✓ Players are happy and informed
✓ Presentations go smoothly
✓ Data is preserved for history

**Warning signs:**
⚠️ Players report lost scores
⚠️ Leaderboards showing wrong data
⚠️ No backups created in 2+ days
⚠️ Switching browsers frequently
⚠️ Confusion about which version is current
⚠️ Players can edit closed rounds

---

## FINAL WORDS OF WISDOM

**This system is bulletproof IF:**
1. You backup daily (seriously, do this!)
2. You verify before accepting/closing
3. You use one browser consistently
4. You don't clear browser data

**Even if something goes wrong:**
- Backups let you restore to any point
- Historical data is never lost (if backed up)
- System can recover from most mistakes
- Paper scorecards are always a fallback

**Remember:**
> "Better to backup and not need it, than need it and not have it."

**Good luck with your tournament! 🏌️⛳🏆**
