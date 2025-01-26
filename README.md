## How to Save All Links on a Web Page as a CSV

This JavaScript bookmarklet allows you to download all the links (URLs) from a webpage as a CSV file. Follow the steps below to set it up and use it:

### Instructions

1. Open your browser.
2. Go to the **Bookmark Manager**.
3. Create a new bookmark.
4. Set the bookmark name, for example: `Download Links`.
5. Copy the following code and paste it into the **URL field** of the bookmark:

    ```javascript
    javascript:(function() {
        var links = document.querySelectorAll('a');
        var urls = Array.from(links).map(link => link.href).join('\n');

        var csvContent = 'data:text/csv;charset=utf-8,' + encodeURIComponent(urls);

        var a = document.createElement('a');
        a.href = csvContent;
        a.download = `links_${Date.now()}.csv`; 
        a.click();
    })();
    ```

6. Save the bookmark.
7. Open any webpage.
8. Click on the new bookmark to download all links on the page as a `.csv` file.

---

### Example

- If you save the bookmark as `Download Links` and open a webpage, clicking the bookmark will generate a file named something like `links_<timestamp>.csv` containing all the links on that page.

---

### Notes

- This script extracts all `<a>` tags on a page and their `href` attributes.
- The downloaded file will include one URL per line.
