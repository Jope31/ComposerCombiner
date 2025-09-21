# **Composer.trade Symphony Combiner**

## **Overview**

This is a simple, client-side web tool designed to help users of [Composer.trade](https://www.composer.trade/) combine multiple trading symphonies. It allows you to upload up to three separate symphony text files, and it will intelligently merge their unique logic into a single, cohesive symphony.

The tool analyzes the top-level (group ...) blocks within each uploaded file, removes any exact duplicates, and then combines the unique strategies into a new symphony structure. This is particularly useful for traders who want to merge distinct strategies or components from different symphonies without manually editing complex, nested code.

## **Features**

* **Combine up to 3 Symphonies:** Easily upload and merge three different Composer.trade scripts.  
* **Duplicate Removal:** Automatically identifies and removes duplicate top-level (group ...) blocks to keep the final script clean and efficient.  
* **Preserves Formatting:** The output respects the syntax and line-break formatting required by Composer.trade.  
* **Client-Side Processing:** All processing happens directly in your browser. Your symphony files are not uploaded to any server.  
* **Simple UI:** A clean and straightforward interface for uploading files and getting the combined output.  
* **Copy to Clipboard:** Instantly copy the generated symphony to your clipboard for easy pasting into Composer.trade.

## **How to Use**

1. **Get Composer Code:** Open a symphony's page and click the "Get Composer Code" under the "...More" button on the top right. Paste and save this into a .txt file.
2. **Open symphony\_combiner.html:** Open the HTML file in any modern web browser (like Chrome, Firefox, or Safari).  
3. **Upload Files:** Click on the "Symphony 1", "Symphony 2", and "Symphony 3" upload areas to select the .txt files containing the symphonies you wish to combine. You can select from one to three files.  
4. **Combine:** Click the "Combine Symphonies" button.  
5. **Review Output:** The combined symphony will appear in the text area below the button. The tool will have created a new (defsymphony ...) wrapper with a new title and the current date.  
6. **Copy:** Click the "Copy to Clipboard" button to copy the entire combined script.  
7. **Paste into Composer:** Paste the copied script into a new symphony in your Composer.trade account.

## **Technical Details**

The script's logic is straightforward:

1. It reads the text content from each uploaded file.  
2. For each file, it identifies and extracts all top-level (group ...) blocks. A (group ...) is considered top-level if it is a direct child of the main (weight-equal \[...\] or (weight-specified \[...\] block that typically contains all strategies.  
3. It uses a JavaScript Set to store these blocks, which automatically handles the de-duplication of any identical groups across the different files.  
4. Finally, it constructs a new symphony string, inserting all the unique groups into a new (defsymphony ...) structure.

## **Disclaimer**

This tool is provided as-is, without any warranty. It is not affiliated with Composer.trade. Trading financial instruments involves risk. This tool is for educational and convenience purposes only and should not be considered financial advice. Always test your symphonies thoroughly in Composer's backtesting environment before deploying them with real capital.
