# Project2-ACP
Spell Checker in JavaFX

The goal of this project is to create a graphical spell checker program with Java, Eclipse, Maven, and JavaFX. 

## A. File Menu
The File menu has the three items shown. On Open, the program reads a text file (!) with the current directory set to the directory where your program is located. Save saves the current text in the window to the file selected over a dialog

## B. Edit menu
The Edit menu has one menu item: Spell Check.

###1. General instructions
When the program starts, it will open the dictionary file (name it "Words.txt"). Store the words in a Java Set. (https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Set.html). I'm using these words below and it's ok if you use them, too:

hello
world
how
are
you
neighbor
today
document
word
i
am
fine
labor
this
just
to
see
hope
having
a
good
day
the
weather
weekend
will
be
fabulous
we
spell
check

Include this file in the root directory of your Eclipse project!

###2. Menus
#### File --> Open
Use a File Selector to open a text file, read it and place the contents into a JavaFX TextArea in your application. Include this file in the root directory of  your Eclipse project

Here's is an example text full of misspelled words:
hello worl, how are you. We will spelll check this docuemnt just to see. I hope you are having a good day. The weather this weekend will be flabulous.

#### File --> Save
Saves the current contents of the TextArea into a file chosen over a File Selector.

#### File --> Exit
Terminates the program. You don't have to issue a warning of the contents of the TextArea hasn't been saved!

#### Edit --> Spell Check
Extract every word from the text one by one and find out if the word is in the dictionary. If a word is found that's not contained in the dictionary let the user know and provide a list of suggested words. This list is constructed by making the following modifications to the word and examining the dictionary again:

One letter missing. Assume that one letter has been left out of the word. Assemble new words to check by adding letters a..z in each of the positions in the word from the start to the end of the word.
One letter added. Assume the word has an extra letter. Scan through the word deleting each of the letters in turn, and looking up the word formed by the remaining letters.
One letter swapped with an horizontally adjacent letter (my favorite typo, especially on a cellphone). That requires you to store and analyze the current keyboard layout. Here it is for the USA:
download.png
No, it's not the same as - say! - a UK keyboard, but that shouldn't matter as long as you are concentrating on just the letters. Please note again that everything here only needs to work for lowercase letters, so you have to take into account the fact that q, a, z, p, l and m only have one neighbor. For example you can expect a misspelling docunent instead of document, but something like docu<ent can be ignored.
Each time a legal word is found from any of the three methods, it's added to the suggestion list, which is present to the user in a dialog box. 

#### User Interaction
No other user interaction is necessary. In particular the user doesn't have to make any modifications to the text before running the Spell Check again.

## Requirements
- Proper indentations, No magic numbers, Good Comments, Meaningful variable names, Factored (relatively small) methods.
- Builds dictionary using a class implementing the Set interface (HashSet or TreeSet)
- Correctly identifies misspellings in input text
- Analyzes all three options (1 letter missing, 1 letter added, adjacent letters on keyboard)
- Suggests words (or says none found) based on the 3 options
- Uses JavaFX with menubar and menus
- Properly functioning JavaFX textarea, menu bars, proper dialog boxes to open and save
