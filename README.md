# FS3 Combat HUD (Blu Style)
This repository gives you all the edits you need to update your FS3 Combat HUD to match those found on Empty Night and Aegis Company.

The only thing that this repository does not provide you is access to custom Font Awesome icons or Font Awesome Pro icons. You must have a Font Awesome Pro account to utilize custom icons or icons not in their free catalog.

![alt text](https://github.com/girlcalledblu/FS3-Combat-Hud-Blu-Style/blob/main/FS3-Combat-Hud-Example.png)

## Step 1: Updates to Aresmush

In `aresmush/plugins/fs3combat/helpers/general_helper.rb`, you will need to locate the `damage_boxes` on line 281 and update `5` to `6`. So, the final line should look something like this:

```damage_boxes: ([-combatant.total_damage_mod.floor, 6].min).times.map { |d| d },```

Once that is done, you will need to `git pull` from the game's client if you use GitHub first, and then `load fs3combat` on the game's client. This will add an additional damage box.

## Step 2: Updates to Ares-Webportal

To make this all easier, just replace the entire contents of `ares-webportal/app/components/fs3-combat-hud.hbs` with the file found in this repository.

If you are not using GitHub to keep your game up to date, you will want to navigate to the `app/components` folder in the `ares-webportal` directory and run this command to remove the contents of the fs3-combat-hud.hbs file, `truncate -s 0 fs3-combat-hud.hbs`. You will then be able to edit the file using `nano fs3-combat-hud.hbs` and copy and paste the entire contents of the file in this repository into that now empty file.

Once you have updated that file either through GitHub or the shell, you will need to `git pull` from the game if you used git, and run `website/deploy`.

## Step 3: Add CSS

Use the combat-hud.scss file in this repository to add the CSS styling to your game.

## That's it!
