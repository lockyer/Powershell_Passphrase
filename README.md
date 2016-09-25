# Passphrase
Generate Diceware inspired passphrases using powershell

Words in the original [Diceware](http://world.std.com/~reinhold/diceware.html) list have an average length of 4.2 characters, this list has an average of 4.8. The tradeoff is that this list contains only alphanumeric characters, and I've also removed common swear
words. I've observed that people usually re-roll when they encounter these issues. I think it's a better user
experience, and slightly more secure to generate passwords people will actually use. This list uses the most
popular words from [Google's Ngram List](http://storage.googleapis.com/books/ngrams/books/datasetsv2.html) with the above exceptions, so they should be mostly familiar to english speakers.

If you find offensive words in here I've missed let me know, I don't personally care about them for my personal use, but if
you're using this as an administrator to create temporary passwords to share with others you'd rather not send them
something that gets HR involved :P

I do nothing to guarentee that you won't get an offensive phrase, as this would be much more complicated, and a bad 
implementation could greatly reduce the effective entropy of the phassphrases. Use your own discression.
