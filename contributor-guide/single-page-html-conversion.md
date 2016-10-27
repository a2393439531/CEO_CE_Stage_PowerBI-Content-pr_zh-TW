# Single web page conversion guide

1.  Visit the target website and `File -> Save As`
2.  Save the page using its `github-file-name`
3.  Open the command prompt and navigate to the web page's folder
4.  Run pandoc to convert the topic `pandoc -f html -t markdown_github <github-file-name>.html -o <github-file-name>.md`
5.  Rename the assets folder from <ph id="ph1">`&lt;github-file-name&gt;_files`</ph> to <ph id="ph2">`&lt;github-file-name&gt;`</ph>. There maybe a warning but click through it anyway.
6.  Open the markdown file using <bpt id="p1">[</bpt>notepad++<ept id="p1">](https://notepad-plus-plus.org/)</ept>.
7.  Remove any unwanted content like headers, footers, and sidebars.
8.  Fix the H1 headding by adding a hashtag and space before the H1 heading and removing the double underline below it.
9.  Remove the empty span tags using search and replace
    
    1.  Press <ph id="ph1">`Ctrl+H`</ph> or navigate from the menu `Search -> Replace`
    2.  Make sure these options are checked
        -  Wrap around
        -  Search Mode: Regular expression
        -  Search Mode: . matches newline
    3.  Find what: <ph id="ph1">`&lt;span&gt;(.*?)&lt;/span&gt;`</ph> Replace with: <ph id="ph2">`\1`</ph>
    4.  Replace all

10.  Fix the image links:

    1.  Search： `\!\[(.*?)\]\(./<github-file-name>_files/`
    2.  取代： `![\1]\(media/<github-file-name/`
    3.  In the file explorer move the image folder to a media directory, create one if one does not exisit.
    4.  In the image folder remove any non-image items such as .js, .css, .php, and any unused images from the removed sections of the page (logos and icons).

11.  Open the markdown file in the editor of your choice. 

12. Compare the markdown content from the original web page. You may have to fix a few other things such as making sure ordered lists are spaced out correctly. There may be a few <ph id="ph1">`&lt;span&gt;`</ph> tags that need to be removed or other formatting changes that need to be made. Any tables that did not get converted will need to be fixed as well.

13.  Add any relevant metadata to your topic.

14.  Add your topic to the github repo (don't for get your image folder), make the commit to a local branch.

15.  Push the branch to your private fork and submit a pull request to the master branch

16.  Wait for your topic to pass validation and make any fixes as necessary. Once you are satisfied sign off on the pull request using <ph id="ph1">`#sign-off`</ph>.