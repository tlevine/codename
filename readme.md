Codename
===

Here we adapt Twelfth Night to modern (2012, 2013) American communication
methods like Facebook.

**If you want to edit the script/outline on GitHub, click
[here](https://github.com/tlevine/codename/edit/master/outline.md)**.

I called our script an "outline" because we don't intend for it to be as
precise as the word "script" might imply.

**Note to Aaron**: The outline is written in
[Markdown](http://daringfireball.net/projects/markdown/). If you have any
trouble with it, ignore the markdown syntax and write however you want;
I'll clean up the formatting. Also, if you are more comfortable with a
different markup language, I'm fine with switching.

## Characters
The edition from Project Gutenberg tells us of these characters.

    ORSINO, Duke of Illyria.
    SEBASTIAN, a young Gentleman, brother to Viola.
    ANTONIO, a Sea Captain, friend to Sebastian.
    A SEA CAPTAIN, friend to Viola
    VALENTINE, Gentleman attending on the Duke
    CURIO, Gentleman attending on the Duke
    SIR TOBY BELCH, Uncle of Olivia.
    SIR ANDREW AGUE-CHEEK.

    MALVOLIO, Steward to Olivia.
    FABIAN, Servant to Olivia.
    CLOWN, Servant to Olivia.

    OLIVIA, a rich Countess.
    VIOLA, in love with the Duke.
    MARIA, Olivia's Woman.

    Lords, Priests, Sailors, Officers, Musicians, and other
    Attendants.

## Code snippets
This finds characters in `gutenberg.txt`.

    grep -e '^[A-Z]*\.' gutenberg.txt | grep -v 'P. O. Box' | cut -d. -f1 | sort -u

This converts the list of scenes and characters from
[playshakespeare](http://www.playshakespeare.com/twelfth-night/scenes) to
something simple.

    sed -n \
      -e 's/<h3 class="scenetitle">/\n### /p' \
      -e 's/<p class="scenelocation">/\n**Location**: /p' \
      -e 's/<p class="scenepersonae">/\n**Characters**: /p' \
      Twelfth Night Scenes.html | cut -d\< -f1 |
      sed 's/### Scene 1/## Act\n\n### Scene 1/' >
      outline.md

## References

The original script (`gutenberg.txt`) comes from project gutenberg. The page on
Project Gutenberg is [here](http://www.gutenberg.org/ebooks/1526), and the file
I downloaded is [here](http://www.gutenberg.org/cache/epub/1526/pg1526.txt).

I took a character list from 
[playshakespeare](http://www.playshakespeare.com/twelfth-night/scenes).
