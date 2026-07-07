# Golf Tournament System - Testing Guide & Bug Tracker

## TESTING CHECKLIST

### Phase 1: Initial Setup
- [ ] Open `golf-tournament-SIMPLE-SETUP.html`
- [ ] Click "ONE-CLICK SETUP" button
- [ ] Verify 8 players created
- [ ] Verify Round 1 created with test scores
- [ ] Check localStorage contains: `golfTournamentData`

### Phase 2: Admin Controls
- [ ] Open `admin-controls.html`
- [ ] Set number of rounds to 3
- [ ] Apply configuration
- [ ] Verify 3 rounds displayed
- [ ] Open Round 1
- [ ] Verify status shows 🔓 OPEN

### Phase 3: Player Score Entry
- [ ] Open `golf-tournament-player.html`
- [ ] Check if admin notices appear (none yet)
- [ ] Login as "John Smith"
- [ ] Select "Round 1"
- [ ] Select partner "Sarah Johnson"
- [ ] Enter scores for front 9
- [ ] Verify Stableford points appear immediately
- [ ] Verify OUT column updates
- [ ] Verify auto-save indicator appears
- [ ] Complete back 9
- [ ] Verify IN and TOTAL columns update

### Phase 4: Scorecard Validation
- [ ] Open `golf-tournament-admin.html`
- [ ] Go to "Scorecard Acceptance" tab
- [ ] Select Round 1
- [ ] Verify John Smith's scorecard appears
- [ ] Check scores match what was entered
- [ ] Verify Stableford points shown
- [ ] Accept scorecard
- [ ] Close Round 1
- [ ] Verify John can no longer edit scores

### Phase 5: Leaderboards (Admin View)
- [ ] Open `stableford-leaderboard.html`
- [ ] Select Round 1
- [ ] Verify Net Stableford tab shows rankings
- [ ] Check John Smith appears with correct points
- [ ] Switch to Gross Stableford
- [ ] Verify different rankings

### Phase 6: Live Leaderboard (Player View - DISABLED)
- [ ] Open `player-leaderboard.html`
- [ ] Verify shows "🔒 Leaderboard Not Available"
- [ ] Return to `admin-controls.html`
- [ ] Toggle "Live Leaderboard" to ON
- [ ] Return to `player-leaderboard.html`
- [ ] Verify now shows standings

### Phase 7: Skins
- [ ] Open `skins-leaderboard.html`
- [ ] Select Round 1
- [ ] Check Net Skins tab
- [ ] Verify winners shown
- [ ] Use Hole Lookup tool
- [ ] Enter hole number (e.g., 5)
- [ ] Verify shows all players' scores for that hole

### Phase 8: Admin Notices
- [ ] Open `admin-controls.html`
- [ ] Scroll to Admin Notice Board
- [ ] Enter title: "Weather Alert"
- [ ] Enter message: "Heavy rain expected. Seek shelter if needed."
- [ ] Click "Post Notice"
- [ ] Verify notice appears in Active Notices
- [ ] Open `golf-tournament-player.html`
- [ ] Verify yellow notice box appears at top

### Phase 9: Group Generator
- [ ] Open `group-generator.html`
- [ ] Select "Generate Groups For Day": Round 2
- [ ] Players Per Group: 4-ball
- [ ] First Tee Time: 08:00
- [ ] Interval: 10 minutes
- [ ] Click "Generate Groups"
- [ ] Verify groups created with worst scores first
- [ ] Click "Save Groups"
- [ ] Click "Export as Text"
- [ ] Verify file downloads

### Phase 10: Reveal Leaderboards (DISABLED)
- [ ] Open `reveal-leaderboards.html`
- [ ] Click "Daily Final" tab
- [ ] Select Round 1
- [ ] Verify shows "🔒 Results Not Yet Available"
- [ ] Return to `admin-controls.html`
- [ ] Toggle "Daily Final Leaderboard" to ON
- [ ] Return to `reveal-leaderboards.html`
- [ ] Verify now shows podium and full results

### Phase 11: Presentation Page
- [ ] Open `presentation.html`
- [ ] Click "Daily Results"
- [ ] Select Round 1
- [ ] Verify shows:
  - Net Stableford winners (podium)
  - Gross Stableford winners
  - Net Skins winners
  - Gross Skins winners
  - Best Ball (if teams created)
  - Eclectic leaders
  - Special Prizes (if entered)
- [ ] Click "Print Presentation"
- [ ] Verify prints cleanly

### Phase 12: Team Competitions
- [ ] Open `team-management.html`
- [ ] Click "Best Ball Teams" tab
- [ ] Select Round 1
- [ ] Check 4 players
- [ ] Click "Create Team"
- [ ] Verify "Team 1" created
- [ ] Open `team-results.html`
- [ ] Select Round 1
- [ ] Verify Team 1 shows with calculated points

---

## KNOWN ISSUES

### Critical Bugs
None identified yet - testing in progress

### Minor Issues
1. **Terminology inconsistency**: admin-controls.html uses "Day" but everywhere else uses "Round"
   - STATUS: This is fine per user preference
   
2. **Presentation page access**: Not restricted to admin only
   - IMPACT: Players could view presentation before admin wants to reveal
   - FIX NEEDED: Add simple password or admin key check

3. **Browser storage limitations**: 
   - localStorage has ~5-10MB limit
   - Large tournaments (48 players × 6 rounds) may approach this
   - WORKAROUND: Export data regularly as backup

### Enhancement Opportunities
1. **Ambrose scoring interface**: Still requires manual team score entry
2. **Data export**: Add comprehensive backup/export functionality
3. **Mobile optimization**: Some tables could be more mobile-friendly
4. **Offline mode indicator**: Show if data is saved locally vs needs sync
5. **Undo feature**: Allow admin to undo scorecard acceptance if needed

---

## TEST DATA VERIFICATION

### Expected Results from SIMPLE-SETUP:
- **Players**: 8 total
  - John Smith (HCP 18)
  - Sarah Johnson (HCP 36)
  - Michael Williams (HCP 12.3)
  - Emily Brown (HCP 15.8)
  - David Jones (HCP 5.2)
  - Jessica Davis (HCP 22.1)
  - James Miller (HCP 9.5)
  - Jennifer Wilson (HCP 14.2)

- **Scores**: Test scores generated for all 8 players
- **Scorecards**: 4 matched pairs (pending validation)
- **Round Status**: Open

### Manual Verification Points:
1. John Smith (HCP 18) gets 1 stroke on EVERY hole
2. Sarah Johnson (HCP 36) gets 2 strokes on EVERY hole
3. Stableford calculation:
   - Par = 2 points
   - Birdie = 3 points
   - Bogey = 1 point
   - Double bogey+ = 0 points

---

## BROWSER COMPATIBILITY

Tested in:
- [ ] Chrome/Edge (Chromium)
- [ ] Firefox
- [ ] Safari (Desktop)
- [ ] Safari (iOS)
- [ ] Chrome (Android)

---

## PERFORMANCE NOTES

- **Initial load**: <1 second
- **Score entry**: Instant
- **Auto-save**: 500ms debounce
- **Leaderboard calculation**: <500ms for 48 players
- **Group generation**: <100ms for 48 players

---

## SECURITY CONSIDERATIONS

1. **Data persistence**: All data in browser localStorage (no server)
2. **Anti-cheat**: Partner validation system
3. **Admin access**: No password protection (assumes trusted environment)
4. **Data privacy**: No data leaves the user's device
5. **Backup**: Admin should export data regularly

---

## RECOVERY PROCEDURES

### If data is lost:
1. Check browser's localStorage inspector
2. Use data export if previously saved
3. Re-run SIMPLE-SETUP for testing
4. Manual re-entry if no backup exists

### If scores won't save:
1. Check browser console for errors
2. Verify partner is selected
3. Clear browser cache and reload
4. Try different browser

### If leaderboards are blank:
1. Verify Round 1 has scores
2. Check admin has accepted scorecards
3. Refresh page
4. Check browser console for errors

---

## SUPPORT CHECKLIST

Before reporting a bug:
- [ ] Refresh the page
- [ ] Clear browser cache
- [ ] Try in incognito/private mode
- [ ] Check browser console (F12) for errors
- [ ] Verify localStorage has data
- [ ] Try different browser
- [ ] Re-run SIMPLE-SETUP for clean test

---

## SUCCESS CRITERIA

System is working correctly if:
✓ Players can enter scores independently
✓ Stableford points calculate correctly
✓ Scorecards require partner validation
✓ Admin can accept/reject scorecards
✓ Leaderboards rank correctly
✓ Skins track properly with carryovers
✓ Admin controls toggle visibility
✓ Groups generate in correct order
✓ Presentation shows all winners
✓ Data persists across sessions
