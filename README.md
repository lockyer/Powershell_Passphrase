# Powershell Passphrase
Generate Diceware inspired passphrases using Powershell

## Motivation
I've been using [Diceware](http://world.std.com/~reinhold/diceware.html) the traditional way for a while now, but there are a couple things that have been bothering me about it:
* Many of the words are not alphanumeric. These are harder to type and remember. I believe this is done to shorten the average word length, but it's just not the tradeoff I'd make.
* There are obvious swear words. I don't care about them for my personal use, but if you're using this to create temporary passwords to share with others it can make things awkward.
* Rolling physical dice takes longer than I would like.
* There is a suggested minimum character count of 17, but it's easy to forget to check this.

There are many free Diceware like tools and apps out there, but I really want to be able to audit the source because:
* I'd like to verify that it's not doing anything malicious like making network connections.
* I'd like to verify it's not doing anything dumb like [exhibiting modulus bias](http://stackoverflow.com/questions/10984974/why-do-people-say-there-is-modulo-bias-when-using-a-random-number-generator), or using a non-cryptographic number generator.

In particular [1Password](https://1password.com/) has a Diceware like implementation, but I dislike it because it uses a larger word list which means more of the words fall outside my vocabulary. This increases the effective entropy for the same number of words, but makes them difficult to spell, type and, remember. Again, not the tradeoff I would make.

Finally, I'd like it to run without having to install any dependencies on my machine.

## Implementation
Words in the original [Diceware](http://world.std.com/~reinhold/diceware.html) list have an average length of 4.2 characters, this list has an average of 4.8. The tradeoff is that this list contains only alphanumeric characters, and I've also removed common swear
words. I've observed that people usually re-roll when they encounter these issues. I think it's a better user
experience, and slightly more secure to generate passwords people will actually use every time. This list uses the most
popular words from [Google's Ngram List](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html) with the above exceptions, so they should be mostly familiar to english speakers.

If you find offensive words in here I've missed, let me know. I do nothing to guarentee that you won't get an offensive phrase, as this would be much more complicated, and a bad implementation could greatly reduce the effective entropy of the phassphrases. Use your own discression.

## Caveats
This script is easily auditable, but auditing some of the underlying dependencies may be incredibly difficult. Dice still have the advantage of being dead simple. This script requires you to trust Microsoft's benevolence and competence. If you're running their operating system I assume this is something you've already made peace with!
