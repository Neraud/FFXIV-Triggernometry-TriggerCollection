# Pull

## Filters

Zones : All

Jobs : All

## Triggers

In-game countdown messages are a bit inconsistent.

Depending on the countdown duration used, different reminders appear in-game.

For example, `/cd 15` will display :

```markdown
15
10
5 4 3 2 1
```

However It appears that the game only reminds when at least 5 seconds have passed. So `/cd 14` will display :

```markdown
14
5 4 3 2 1
```

These triggers are built together to announce a pull countdown with forced reminder (even if the game doesn't have a reminder for it):

- the initial countdown
- a forced 15 sec reminder
- a forced 10 sec reminder
- a forced 7 sec reminder for RDM

### Battle commencing in X seconds

Detects : The start or update of a countdown

Actions : Says `Pulling in [x]`

### Battle commencing in 10 seconds

Detects : When a countdown has 10 seconds remaining

Actions : Says `10`

### Countdown cancelled

Detects : When a cooldown is cancelled

Actions : Says *Pull cancelled*
It also cancels the other forced reminders.

**Warning** : if you change the forced reminders, you will need to update the actions of this trigger to make sure it cancels the updated forced reminders

### RDM/Battle commencing in 7 seconds

Jobs filter : RDM only

Detects : When a countdown has 7 seconds remaining

Actions : Says `7`
