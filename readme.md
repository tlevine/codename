Codename
===

Here we adapt Twelfth Night to modern (2012, 2013) American communication
methods like Facebook.

The original script (`gutenberg.txt`) comes from project gutenberg. The page on
Project Gutenberg is [here](http://www.gutenberg.org/ebooks/1526), and the file
we downloaded is [here](http://www.gutenberg.org/cache/epub/1526/pg1526.txt).

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

