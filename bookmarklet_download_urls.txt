// How to use:

// 1. Open Your Browser
// 2. Access Bookmark Manager
// 3. Create a New Bookmark
// 4. Add name, for example: "Download Links"
// 5. Copy the following code and paste it into the URL field:

javascript:(function() {
    var links = document.querySelectorAll('a');
    var urls = Array.from(links).map(link => link.href).join('\n');

    var csvContent = 'data:text/csv;charset=utf-8,' + encodeURIComponent(urls);

    var a = document.createElement('a');
    a.href = csvContent;
    a.download = `links_${Date.now()}.csv`; 
    a.click();
})();

// 6. Save the bookmark
// 7. Open any web page and press on this new bookmark
