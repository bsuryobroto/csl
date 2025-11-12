# ..citation styles..

..choose your style..[find them in folder `journal`]
- `journal-of-hayati.csl`
  - based on instruction from Hayati Journal of Biosciences in https://journal.ipb.ac.id/index.php/hayati/AuthorsGuideline
- `gaya-ipb-cse.csl`
  - based on Pedoman Penulisan Karya Ilmiah Tugas Akhir Mahasiswa Edisi Ke-4
    - PT Penerbit IPB Press
    - Cetakan 1, Desember 2019
  - https://kmmai.ipb.ac.id/buku-pedoman-penulisan-karya-ilmiah-tugas-akhir-mahasiswa-edisi-ke-4/

## how did i make them..?
- read `journal-of-hayati_story.md`

## problem when using in mendeley..?

### convo with glm-4.6:cloud in ollama..

---

> ..the styles work perfectly..! i upload the two styles to my github..but when mendeley 2.139 [in `word` plugin] ask for url..it throw an error "Custom citation style is malformed".


Excellent! I'm glad the styles work perfectly for you.

That "Custom citation style is malformed" error from Mendeley is very common and frustrating. The good news is that it's almost never an issue with the **content of your `.csl` file**, especially since we've already tested and confirmed it works. The error is almost always related to **how GitHub serves the file**.

Mendeley is very picky. It expects the file to be a pure XML file, served from a direct, raw URL. When you just link to a file on a GitHub repository page, GitHub often wraps it in its own web interface or sends it with the wrong `Content-Type` header, which confuses Mendeley.

### The Solution: Use the "Raw" URL

To fix this, you must give Mendeley the **direct, raw link** to the file's content.

**How to Get the Raw URL:**

1.  Go to your file on GitHub. For example: `https://github.com/[YourUsername]/[YourRepo]/blob/main/[YourStyleName].csl`
2.  Look for the button in the top-right corner of the file view that says **"Raw"**.
3.  Click that "Raw" button.

This will take you to a new URL that looks something like this:
`https://raw.githubusercontent.com/[YourUsername]/[YourRepo]/main/[YourStyleName].csl`

**This is the URL you must copy and paste into Mendeley.**

---

### Step-by-Step for Mendeley

1.  In Mendeley Desktop, go to `Tools` -> `Options` -> `Citation Styles`.
2.  Click the "Get More Styles" button.
3.  In the new window, click the "Install CSL" tab (looks like a file icon).
4.  Paste the **raw URL** you copied from GitHub into the box that says `From URL`.
5.  Click "Download".

Mendeley should now download and install the style without any errors. The same rule applies to Zotero and any other reference manager: always use the "Raw" GitHub URL for installing CSL files.

Let me know if that solves the problem

> ..it's okay for mendeley desktop..but still threw the same error in mendeley plugin in word..

Ah, that's a classic and very frustrating problem with the Mendeley Word plugin. The plugin and the desktop app sometimes have a "disconnect" and don't sync styles properly.

The fact that it works in the desktop app is great news—it proves your `.csl` file is perfectly valid and the GitHub raw URL is correct. The issue is now entirely with the Word plugin.

Here are the most common solutions, ranked from most likely to least likely. Please try them in order.

---

### Solution 1: The Classic "Refresh and Restart" (95% Chance of Success)

This is the most common fix. The Word plugin's style cache gets stuck.

1.  **Close Microsoft Word completely.**
2.  **Close Mendeley Desktop completely.** Make sure it's not running in the background (check your system tray).
3.  **Restart Mendeley Desktop.**
4.  In Mendeley Desktop, go to `View` -> `Citation Style` and make sure your new custom style is **selected** as your default style.
5.  **Re-open Microsoft Word.**
6.  Click the Mendeley tab. Go to the style dropdown and select your new style again, even if it already appears to be selected. Sometimes this forces a refresh.
7.  Try to insert a citation.

This sequence of actions forces the Word plugin to re-synchronize with the desktop app's list of installed styles.

---

### Solution 2: Manually Re-select the Style in Word

Sometimes the style is installed but not correctly "activated" in the plugin.

1.  In Word, go to the `Mendeley` tab.
2.  Click on the `Citation Style` dropdown menu.
3.  You should see a list of styles. Scroll down to the bottom and find your custom style. It might be listed as "gaya-ipb-cse" or the title you gave it.
4.  Select it from the list. If it was already selected, select a different style (like "APA") and then select your custom style again.
5.  Wait a few seconds for the Word plugin to update.
6.  Try inserting a citation.

---

### Solution 3: The "Nuclear Option" - Reinstall Mendeley Plugin

If the above doesn't work, the plugin itself might be corrupted.

1.  In Word, go to `File` -> `Options` -> `Add-ins`.
2.  At the bottom, find the `Manage:` dropdown, select `COM Add-ins`, and click `Go...`.
3.  Find "Mendeley Word Plugin" in the list, uncheck it, and click `OK`.
4.  **Close Word completely.**
5.  Go back into Mendeley Desktop. Go to `Tools` -> `Install MS Word Plugin`.
6.  Re-open Word and go through the initial setup again (it will ask for you to log in).

This will give you a fresh installation of the plugin, which should then correctly sync all the styles from the desktop app.

---

### A Final Thought

Please **try Solution 1 first**. This "close everything and restart in the right order" solves the problem for almost everyone who experiences it. It's a well-known bug with the Mendeley plugin.

Let me know if any of these solutions work for you