# Rostelecom call records downloader

## Implementation details
- `dotenv` for credentials
- `cheerio` for `DOM` manipulation
- `node-fetch` or `axios` for url fetching

## Links:
- [Cheerio](https://www.npmjs.com/package/cheerio)
- [Axios](https://github.com/axios/axios)
- [Dev.to: Saving image from url](https://dev.to/masbagal/saving-image-from-url-using-node-js-5an6)
- [Node download image](https://flaviocopes.com/node-download-image/)

## Dev notes:
- Get all user links: `[ ...document.querySelectorAll(".record-table tbody a.dashed.black")].map(link => link.href)`
- Get all dates from page: 
```javascript
[ ...document.querySelectorAll("#datatables tbody tr")].map(row => {
    const datetime = row.cells[1].innerText;
    const time = datetime.slice(-5);
    const date = datetime.slice(0,8);
    return `${date} ${time}`
})
```