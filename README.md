# Anki Mandarin Card Creator

A terminal program that creates Anki cards to study Mandarin Chinese.

![AMCC screencast](readme-resources/screencast.gif)

I wrote it for myself to save time. Before, I would have to enter the values
into the fields by hand, which gets tedious, especially with media files like
images and sounds.

It should be noted that as of now this is an ad hoc solution, since other
learners might need fields that are different from the ones
that I've included in this program, in another order or from other sources.

The cards consist of:
- Hanzi characters
- Pinyin
- English translations
- Stroke order animations
- Pronunciation audio

Example of a card after importing:

![Card demonstration](readme-resources/card.gif)

### How it works
The user inputs search queries, results of which are parsed for
hanzi, pinyin and translation. If a query returns multiple definitions, user
can select the one that he's looking for from a list. After selecting the
definition, the program downloads stroke animations.

Audio files are downloaded from [soundoftext.com](soundoftext.com), the website
provides a nice API to download audio generated by Google Translate.

##### Requirements
- [requests](https://pypi.org/project/requests/)
- [Beautiful Soup](https://pypi.org/project/beautifulsoup4/)
- [blessed](https://pypi.org/project/blessed/)

##### Output
Output is saved in a tsv file that later can be imported in Anki. The media
files are downloaded to a separate folder, contents of which should be manually
moved to the local `collection.media` folder
(`$HOME/.local/share/Anki2/User/collection.media` on Linux). 

Here is an example line of the output tsv file:

    好	hǎo​	good  / well  / proper  	<img src="22909.gif">	[sound:626ff390-cc30-11e7-b331-7d14f8ed1278.mp3]

##### Configuration
Configuration is done via a config file, in which output paths, number of
translation variants and keybindings can be configured.
