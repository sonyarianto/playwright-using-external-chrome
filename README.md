# playwright-using-external-chrome
Quick sample of how to use Playwright to control external Chrome via CDP (Chrome DevTools Protocol).

## Overview
Mostly sample on the internet is about using Playwright with bundled Chromium. How about to use external or existing installed Chrome? That's this repository purpose, to give you example how to do it.

## Use "Chrome for Testing" as external Chrome
Instead of using your existing installed Chrome, now you can use Chrome for Testing to install Chrome for the purpose of automation or testing. This is very neat solution from Chrome team. It comes with versioned Chrome side-by-side with current stable version. Please read more at https://developer.chrome.com/blog/chrome-for-testing

I am using this command to download latest available Chrome for Testing binary corresponding to Stable channel.

```bash
npx @puppeteer/browsers install chrome@stable
```

After installation finished it will display the location of installed Chrome for Testing.

## Run the Chrome for Testing

To run the Chrome for Testing that will accept CDP connection please run with this command.

```
path/to/chrome-for-testing/chrome --remote-debugging-port=9222
```

I am using Windows 11 so here is my command to start the Chrome for Testing.

```
Start-Process -FilePath "C:\Users\Sony AK\chrome\win64-115.0.5790.102\chrome-win64\chrome.exe" -ArgumentList "--remote-debugging-port=9222"
```

I am using WSL2 in Windows 11, so here is my command to start Chrome for Testing.

```
~/chrome/linux-115.0.5790.102/chrome-linux64/chrome
```

the `115.0.5790.102` is just the version of Chrome for Testing on my local machine. Adjust that accordingly.

## The script

I already create the `index.js` script as quick sample. Just open that.

## Running the script

Just type below command. Make sure the Chrome for Testing already run before you run below command.

```
node ./index.js
```

That's it.

## Use cases

- Run web scraper script efficiently using existing browser instance.
- Just use your imagination.

## License

MIT

Maintained by Sony Arianto Kurniawan <<sony@sony-ak.com>> and contributors.
