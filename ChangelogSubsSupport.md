# v1.5.2 #
## main ##
  * added Subssupport DVB player - possibility to select and playback subtitles while watching DVB broadcast
    * added in plugins menu
    * added in extensions menu (blue button)
    * possible auto sync subtitles to current event time (yellow button)
    * possible to change subtitles fps (blue button)
    * possible to show help menu (help button)
    * possible to show subtitles/event status (ok button)
      * shows current subtitle, subtitles time, position, fps
      * shows current event, event name, event time and duration
    * possible to resume/pause subtitles playback (pause/resume button)
    * possible to jump between subtitles
      * jump to next/previous subtitle (right/left button)
      * jump to next/previous minute subtitle (next,fastforward/previous,fast backwards button)
      * relative jump to custom position (long press of next,fastforward/previous/fastbackwards button)
      * jump to start of current subtitle (up/down button)

  * added Subssupport settings - possibility to change global subssupport settings
    * added in plugins menu
    * general settings
    * external subtitles settings
    * embedded subtitles settings
    * dvb player settings

  * Subssupport downloader
    * added event now and event next title for suggestions

  * fixed timing when custom subtitles fps is provided

  * updated font selection routine
    * all fonts are now retrieved for selection from standard enigma2 fonts location - typically /usr/share/fonts directory
    * removed Subssupport local fonts directory for font selection
    * removed Ubuntu fonts from package
      * Openpli based images have nice alternative (Liberationsans fonts), which is selected as default if available

  * External Subtitles Settings
    * removed "Subtitles Parsing/Rendering" option
      * it defaults to "new block renderer", all other renderers are removed
    * every type of external subtitle [regular/italic/bold] can be now rendered with different font and different color
      * added "Font type (Regular)" option
      * added "Font color (Regular)" option
      * added "Font transparency (Regular)" option
      * added "Font type (Italic)" option
      * added "Font color (Italic)" option
      * added "Font transparency (Italic)" option
      * added "Font type (Bold)" option
      * added "Font color (Bold)" option
      * added "Font transparency (Bold)" option

  * Embedded Subtitles Settings (non-pli)
    * added Font type selection for every subtitle style (not tested)

## search ##
  * Subssearch screen
    * fixed GS on cancelling choice dialog which is open when there are multiple subtitles available
    * don't show save "Next to video" option, when there is no video available
      * Subssupport DVB player
    * fix download error in Subssupport downloader/player when "Save to" option is set to "Next to video"
    * keep the order of search langs

  * Subssearch settings
    * fixed some skin issues
    * added jumping between providers and search config (yellow/pageUp/pageDown) button
    * added "Save as (fallback)" option
      * in case we have no filepath set and "Save as" is set to "video", "Save as (fallback)" option is used to determine download location

  * Searchparams screen
    * cache suggestion dialogs

  * History screen
    * change "settings" button color from yellow to blue

  * added titlovi provider
  * fixed subscene provider
  * fixed podnapisi provider

# v1.5.1 #
## main ##
  * improved precision of delay functions
  * added subtitles status screen (TV button in MP2 0.59)
    * possibility to change subtitles delay by skipping to previous/next subtitle (right/left arrow)
      * It allows very easy adjustments for videos for which was subtitles not made (recordings)
    * possibility to change subtitles delay by 200ms step (up/down arrow)
      * It is ment for fine tuning in case you find right subtitle by right/left action
    * possibility to change subtitles fps in case they were timed for different video fps (blue button)

# v1.5.0 #
## main ##
  * added subssupport downloader plugin
    * now you can search and download subtitles without opening mediaplayer
    * added to Plugins and Extensions menu (blue button)
  * attempt to fix compatibility with DMM images
  * fixed GS when loading subtitles with diacritics in filename
  * updated slovak locales
  * main menu screen
    * added "Search Subtitles" option for more direct reach
  * choose subtitles screen
    * removed "Search Subtitles" option
    * added "Choose from download history" option (yellow button)

## search ##
  * added download history
    * shows list of all downloaded subtitles (if download history is enabled)
    * possibility to select and open downloaded subtitle (ok button)
    * possibility to remove downloaded subtitle from list/filesystem (red button)
    * downloaded subtitles in current search session are marked(green)
    * subtitles removed from filesystem are auto-removed also from the list
    * download history is limited (default=50 entries) when limit is reached then oldest entry is removed

  * search subtitles screen
    * fixed downloading subtitles with diacritics in filename
    * fixed serbian country code, serbian flag is now shown
    * search progress message now also shows count of found subtitles
    * while search is active only "exit" and "ok" buttons are enabled
      * exit - closes subtitle search
      * ok - stops search, and shows all found subtitles up to stop
      * other actions are disabled since it make no sense to change settings, or update search params while searching, performance is also decreased
    * menu actions in bottom menu are enabled/disabled also visually
    * added context menu (menu button)
      * first entry represents default action created by "search settings"
        * same action as pressing "ok" button on subtitle in subtitles list
      * possible options
        * Download (user defined) - downloads subtitle to predefined downloads directory
        * Download (next to video) - downloads subtitle next to video
        * Download (more ...) - shows more download options
          * customize download directory
          * customize filename
        * Download and Load ... - same as Download but also opens(loads) subtitles
    * added "History" option (yellow button)
      * opens download history
    * "Settings" option is moved from yellow to blue button
    * renamed "Update search params" to "Update"

  * search settings screen
    * fixed option "Always ask before overwriting existing subtitles"
      * was still asking for overwriting, when this option was turned off
    * added "Load subtitles after download" option
      * when turned off subtitles will be not loaded and you will remain in subtitle's search list, with possibility to download more subtitles
    * added "Save downloaded subtitles to history"
    * added "Load/Save download history directory"
      * select directory from where the download history will be stored and loaded
    * removed "Always ask where to download subtitles" option
      * this option is no longer neccessary, its fully replaced by "Download (more...)" option from context menu
    * fixed typos


# v1.4.9 #
## main ##
  * updated polish translations by Mickey GMouse
  * fixed not working reset defaults in subtitles search settings [issue#63](https://code.google.com/p/mediaplayer2-for-sh4/issues/detail?id=#63)
  * install utf-16 encoding library when missing

# v1.4.8 #
## main ##
  * improved Subrip parser
    * better performance
    * more tolerant
  * fixed background calculation for text with preceding/trailing spaces

# v1.4.7 #
## main ##
  * improved MicroDVD parser
    * added font style tags support
    * added color tags support
  * subtitles delay change is now visible immediately
  * fixed update subtitles position routine after seeking back
  * fixed GS when invalid subtitles url is provided

## search ##
  * improved handling of broken subtitles providers
    * added info message when some providers are not working
    * all available providers are now shown in search settings
      * provider can have enabled, disabled and error state
      * providers text is colored according to its state
      * when OK button is pressed on provider with error state, message with more details is now shown
  * fixed behavior of subtitle's search list when country flag for subtitles in list is not available

# v1.4.6 #
## main ##
  * fix GS when rendering subtitles with color

# v1.4.5 #
## main ##
  * fix GS when "Block (new)" renderer is used on non-openpli based images

# v1.4.4 #
## main ##
  * renamed external subtitles block renderer to "Block (old)"
    * this renderer is not default anymore and will be deprecated it's still there for compatibility reasons
  * added new external subtitles block renderer "Block (new)"
    * added posibility to show background around subtitles
      * dynamic background - dynamically computed background that is as big as subtitles text(default)
        * background offsets - if background is too close or far from text then we can adjust it by providing offset values
      * static background - static background which is computed to fit 4 rows of subtitles with specified font(further improvements will follow)
      * transparency - we can set transparency of background
      * color - we can set color of background
    * this renderer is now default for external subtitles
  * add new feature to all external subtitles renderers
    * toggle on/off shadow
    * added subtitles transparency support
  * show units to all options in external/internal subtitles setup
  * updated slovak locales

## search ##
  * don't show duplicit languages in subtitles search window

# v1.4.3 #
## search ##
  * fixed GS on search start, when provider's libraries are missing

# v1.4.2 #

## main ##
  * added option to stop video on opening subtitles menu(default)
  * subtitles bigger then 400KB are not processed
    * This prevents from reading non-subtitles files and binary subtitles files(vobsub) which are not supported
  * updated slovak locales
  * updated czech locales by Vladimir Kuzba

## search ##
  * added Itasa provider (Italian subtitles)
  * added SubtitlesGR provider (Greek subtitles)
  * added missing default languages to Language-Selection screen
  * fixed GS when provider is temporary unavailable
  * fixed unpacking of nested subtitles in archives/subdirectories

# v1.4.0 #

## search ##
  * improved search engine
    * UI is more responsive during search, startup could take little longer though
    * search is now stoppable, so performance of enigma2 will be not affected after subtitles search exit
    * all search restrictions during search are removed

  * translations
    * slovak translation updated
    * czech translation needs update(feel free to contribute :))

  * improved "UPDATE SEARCH PARAMS" screen:
    * added simple history list of previously searched subtitles, while on title entry(red button)
    * added suggestions list(opensubtitles suggestions), while on title entry(green button)
    * added enable/disable use of video path
      * this option identifies if we want to provide, subtitle's search provider videopath, since some providers can use this path to detect subtitles in sync. This can be used if we want to download subtitles for entirely different video
    * added toggle source title(search expression)(blue button)

  * improved "SUBSSEARCH" screen:
    * no thread counter(top-right corner), since we don't use threads anymore
    * removed toggle search expression option(this is now in "UPDATE SEARCH PARAMS" screen
    * show video path search parameter
    * fixed subtitles list behaviour on repeated right/left/up/down action
    * optimized rendering of long subtitles list
    * search button(green)is not blocked anymore during subtitles search

  * improved "SUBSSEARCHSETTINGS" options:
    * added Preferred movie provider - movie provider which will be automatically selected for movie titles in SUBSEARCHPARAMS screen and on auto search
    * added Preferred tv show provider - tv show provider which will be automatically selected for tv show titles in SUBSEARCHPARAMS screen and on auto search
    * added Save as - we can define how do we want to name downloaded subtitles file
    * added Save to - we can define where do we want to download subtitles
    * added Append subtitle's language to filename - append/not language to subtitles filename
    * added Always ask for download location - alway ask/not for subtitles download location
    * added Check search params before search - alway open/not open SUBSSEARCHPARAMS screen before subtitles search
      * detecting search parameters from source title(filepath, streampath)is not always reliable, to avoid useless search with wrong parameters is this option enabled by default, so you can see how detection worked and you can correct it before actual search
    * removed search restriction options
    * renamed some options for better clarification

# v1.3.1 #

## main ##
  * fixed GS from 1.3.0 version when opening embedded subtitles menu on non-pli images - thx to Zdenek

# v1.3.0 #

## main ##
  * fixed GS on VTI image, when embedded subtitles are in use - thx to Zdenek for report and testing
  * fixed rare GS on close of subtitles search screen
  * improved quality of code(no global settings, safe to use multiple instances of classes in subtitles module at the same time), refactoring

## search ##
  * improved detection of compressed subtitles
  * disable search button(visually), when we try to seek with same params as previous search

# v1.2.5 #

## main ##
  * fixed font size option for embedded subtitles on VTI image
  * fixed warnings/removal of plugin in Openpli/OpenATV image
  * fixed GS on subtitles Loading error

## search ##
  * fixed sort providers option
  * fixed preferred languages option(no numerical input screen, not editable only on ok button)
  * fixed paging on right/left button in subtitles search list
  * added provider timeout option(no more waiting on unresponsive providers)
  * supressed provider's specific debug messages
  * cleanup debug messages

# v1.2.0 #

## main ##
  * added MicroDVD format support(.sub,.txt)
  * improved embedded subtitles support for non-pli images - (position, font, color, shadow), thx to Zdenek for testing, fontsize not working on VTI!
  * fixed czech translations by Vlad Kuzba
  * fixed bug when changing shadow type, encodings group or parsing/rendering
  * fixed cancelling modified entries in search settings
  * fixed language change detection

## search ##
  * improved efficiency and lookup for valid subtitles
    * specified search provider type (tv series search, movie search)
    * fixed hash function
    * search is possible only when search params are changed from previous search
    * added simultaneous option to allow/not allow simultaneous search
    * added manual search option - looks for subtitles only on user action(green)
    * added advanced search (show and edit detected search parameters(title,movie/series,episode,season, year,providers)
  * added toggle search expressions(blue button) - filename,dirname..
  * added provider header in subtitles settings
  * added progress info while searching
  * added subscene provider
  * added podnapisi provider (credentials necessary)
  * added serialzone provider
  * fixed detection of compressed subtitles
  * fixed saving provider's settings
  * fixed some encoding issues
  * provider passwords are now hidden
  * [OpenSubtitles](OpenSubtitles.md) try to fix ProtocolError 503