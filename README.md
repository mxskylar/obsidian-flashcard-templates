# Obsidian Flashcard Templates
This project provides templated [Obsidian](https://obsidian.md/) notes that are easy to generate and export to [Anki](https://apps.ankiweb.net/) as flashcards. It's a great way to create formulaic Anki Flashcards that double as notes in Obsidian.

The project contains simple vocab flashcards as well as Jeopardy-style flashcards and a Jeopardy board in Obsidian, which hides togglable answers with the [Creases](https://github.com/liamcain/obsidian-creases) plugin.

Follow the instructions below to [download and setup](#download-and-setup) this project as an Obsidian vault with Anki media files. Then, follow the remaining steps to [generate flashcard notes](#generate-and-export-flashcards) in Obsidian using the [Templater](https://github.com/SilentVoid13/Templater) plugin and export them as flashcards using the [Flashcards](https://github.com/reuseman/flashcards-obsidian) plugin.

## Download and Setup

1. Download and install [Obsidian](https://obsidian.md/) and [Anki](https://apps.ankiweb.net/).
2. [Download this project as a zip folder](https://github.com/mxskylar/obsidian-flashcard-templates/archive/refs/heads/main.zip), then unzip the folder.
3. [Import the unzipped folder into Obsidian as a vault](https://help.obsidian.md/Getting+started/Create+a+vault#Open+existing+folder).
4. When importing, select `Trust Author and Enable Plugins` from the prompt. This will ensure that all the [community plugins](https://help.obsidian.md/Advanced+topics/Community+plugins) required to generate and export flashcards from the Obsidian vault work as expected.
5. Link to this project's `_media` directory in your [Anki media folder](https://docs.ankiweb.net/files.html#file-locations). This can be done by creating an [alias](https://support.apple.com/guide/mac-help/create-and-remove-aliases-on-mac-mchlp1046/mac) to the folder on macOS, a [shortcut](https://support.microsoft.com/en-us/office/create-a-desktop-shortcut-for-an-office-program-or-file-9a8df64b-cd87-4700-95cc-4bc3e2a962da) to the folder on Windows, or a [symlink](https://linuxize.com/post/how-to-create-symbolic-links-in-linux-using-the-ln-command/) to the folder on Linux.
6. Download the [Sample Obsidian Flashcards](https://ankiweb.net/shared/info/1234883347) deck provided by this project into Anki. They are available as a [shared deck](https://docs.ankiweb.net/getting-started.html#shared-decks) for Anki and need to be downloaded to ensure that the Anki card type for the templated flashcards are available for your flashcard decks.
7. Setup [Anki Connect](https://ankiweb.net/shared/info/2055492159) to enable the [Flashcards](https://github.com/reuseman/flashcards-obsidian#how-to-install) plugin to export flashcards to Anki.

The project is now ready to use! See the instructions below for steps to [generate and export](#generate-and-export-flashcards) flashcards.

## Generate and Export Flashcards

Every folder that does **not** begin with `_` can represent a deck. Every sub-folder can represent sub-decks. Each note in these folders may represent a flashcard.

1. [Create a new note](https://help.obsidian.md/How+to/Create+notes) in the folder that represents the cards deck.
2. On macOS, select `⌘ ⌥ e`. On Windows or Linux, select `ctrl opt e`. This will open a prompt for templates available to make flashcards. Select `Vocab Flashcard` to make a simple vocab flashcard or `Jeopardy Flashcard` to make a trivia question flashcard.
3. Fill in the prompts for the template as they appear.
4. Make sure Anki is open. Then, on macOS, select `⌘ ⌥ f`. On Windows or Linux, select `ctrl opt f`. This will export the flashcard to Anki. When you make updates to the flashcard, select the same hotkey to export the card again.

If you create a new folder for a new deck, make sure that the [Anki card type](https://docs.ankiweb.net/getting-started.html?highlight=card%20type#card-types) is set to `Obsidian Flashcard`. You can do this on desktop by selecting `Edit` on the bottom left of any card in the deck. Then select `Cards...` in the top left, change the `Card Type` at the top, and hit `Save` in the bottom right.

If you ever delete the flashcard from Anki, delete the ID number from the bottom of the flashcard note. This is a footnote preceded by `^`. It represents the ID for the card. If the card no longer exists, removing the ID will ensure that a new card is exported to Anki when you run the hotkey again.

### Using the Jeopardy Board

A [Jeopardy Board](./Sample%20Obsidian%20Flashcards/Jeopardy%20Board.md) is available to view all Jeopardy flashcard notes from Obsidian.

To link to a new Jeopardy flashcard from the board, ensure that a note named `Jeopardy Board`  exists in the folder for your parent flashcard deck. There should be a subdirectory named `Jeopardy` in this folder which contains all the Jeopardy flashcards. Follow step 2 [above](#generate-and-export-flashcards) to open the templates prompt, then select `Jeopardy Board Entry` and fill in the prompts for the template as they appear.