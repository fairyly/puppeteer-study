# puppeteer-study
puppeteer-study


## 1.install

```
npm i puppeteer
# or "yarn add puppeteer"



puppeteer-core
Since version 1.7.0 we publish the puppeteer-core package, a version of Puppeteer that doesn't download any browser by default.

npm i puppeteer-core
# or "yarn add puppeteer-core"
```


## 2.使用 puppeteer 打开网页截图

```
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.screenshot({ path: 'example.png' });

  await browser.close();
})();
```

## 3.使用 puppeteer 生成pdf

```
const puppeteer = require('puppeteer');

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto('https://news.ycombinator.com', {
    waitUntil: 'networkidle2',
  });
  await page.pdf({ path: 'hn.pdf', format: 'a4' });

  await browser.close();
})();
```



## 参考
- [puppeteer/puppeteer](https://github.com/puppeteer/puppeteer)
