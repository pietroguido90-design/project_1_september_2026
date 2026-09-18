================================================================================
           ROCK-PAPER-SCISSORS RPG: DESIGN PROCESS & MENTAL WORKFLOW
================================================================================

1. DEFINE THE CORE CONCEPT & TWIST
   - Take classic Rock-Paper-Scissors rules as the base mechanic.
   - Add an RPG progression structure: 3 sequential Boss encounters (5 HP each).
   - Give the player 8 starting HP that carries over across all encounters.

2. ESTABLISH TURN LOGIC & DAMAGE MECHANICS
   - Win: Boss takes damage equal to your symbol's current damage power level.
   - Loss: Player takes 1 fixed damage from the Boss.
   - Tie: Neutral outcome—no damage to either side, round resets.

3. DESIGN THE PROGRESSION & UPGRADE SYSTEM
   - Maintain persistent Player HP across fights to create risk-versus-reward tension.
   - Reward defeating Boss 1 and Boss 2 by prompting the player to pick one symbol 
     (Rock, Paper, or Scissors) to gain +1 damage power for future turns.

4. STRUCTURE PLAYER INPUT & VALIDATION
   - Support both single-letter shortcuts ('r', 'p', 's') and full words ('rock', etc.).
   - Clean raw input using lowercase conversion and whitespace trimming.
   - Enforce a repeating validation loop (while True) to handle invalid inputs 
     without wasting a turn or breaking the program.

5. BUILD THE COMBAT LOOP
   - Make the Boss generate a hidden random choice before prompting the player.
   - Compare choices using standard Rock-Paper-Scissors win conditions.
   - Subtract calculated damage from either player_hp or boss_hp.
   - Repeat turns continuously as long as both player_hp > 0 and boss_hp > 0.

6. IMPLEMENT THE OUTER GAME LOOP
   - Wrap combat in a main loop running exactly 3 boss encounters.
   - Reset boss_hp back to 5 at the beginning of each encounter.
   - Handle post-fight checks: trigger Game Over if player_hp <= 0, or launch 
     the symbol upgrade sequence before starting the next encounter.

================================================================================
