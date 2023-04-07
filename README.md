## Browser Storage Inspector

<p align="center">storage-inspector-js library helps to clear site data & provides storage usage & quota.</p>

<div align="center">

![npm version](https://img.shields.io/npm/v/storage-inspector-js.svg?style=flat-square)
[![install size](https://img.shields.io/badge/dynamic/json?url=https://packagephobia.com/v2/api.json?p=storage-inspector-js&query=$.install.pretty&label=install%20size&style=flat-square)](https://packagephobia.now.sh/result?p=storage-inspector-js)
[![npm bundle size](https://img.shields.io/bundlephobia/minzip/axios?style=flat-square)](https://bundlephobia.com/package/axios@latest)
[![npm downloads](https://img.shields.io/npm/dm/storage-inspector-js.svg?style=flat-square)](https://npm-stat.com/charts.html?package=storage-inspector-js) [![npm version](https://badge.fury.io/js/storage-inspector-js.svg)](https://badge.fury.io/js/storage-inspector-js)

</div>

# Browser Support

![Brave](https://img.shields.io/badge/Brave-FB542B?style=for-the-badge&logo=Brave&logoColor=white) ![Edge](https://img.shields.io/badge/Edge-0078D7?style=for-the-badge&logo=Microsoft-edge&logoColor=white) ![Firefox](https://img.shields.io/badge/Firefox-FF7139?style=for-the-badge&logo=Firefox-Browser&logoColor=white) ![Google Chrome](https://img.shields.io/badge/Google%20Chrome-4285F4?style=for-the-badge&logo=GoogleChrome&logoColor=white) ![IE](https://img.shields.io/badge/Internet%20Explorer-0076D6?style=for-the-badge&logo=Internet%20Explorer&logoColor=white) ![Opera](https://img.shields.io/badge/Opera-FF1B2D?style=for-the-badge&logo=Opera&logoColor=white) ![Safari](https://img.shields.io/badge/Safari-000000?style=for-the-badge&logo=Safari&logoColor=white)

# Installation

```js
 # If you use npm:
 npm i storage-inspector-js

 # If you use yarn:
 yarn add storage-inspector-js


 ES6 Usage
 import { BROWSER, getStorageUsageAndQuota, clearSiteData } from 'storage-inspector-js';

 Commonjs Usage
 var { BROWSER, getStorageUsageAndQuota, clearSiteData } = require('storage-inspector-js');

```

# Usage

<!-- ![Alt text](visual/react-collapsible-black.gif?raw=true "React Collapsible") -->

```js

import React from 'react';
import { BROWSER, getStorageUsageAndQuota, clearSiteData } from 'storage-inspector-js';

const App = () => {
  const storageInfo = (async () => await getStorageUsageAndQuota())();

  return (
   <div>
    <h3>BROWSER: {BROWSER}</h3>
    <p>Storage Info: {storageInfo.baked.usage/storageInfo.baked.quota}</p>
    <button onClick={clearSiteData}>Clear Site Data</button>
   </div>
  );
};

export default App;

```

# Props

| name                    | type       | params                                                | default | description                                                                                                                                                    |
| ----------------------- | ---------- | ----------------------------------------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BROWSER                 | `string`   |                                                       |         | it will provide the browser name i.e. `Brave`, `Chrome`, `Firefox`, `Safari`, `Internet Explorer` `Edge`, `Samsung Browser`, `UC Browser`, `Opera`, `Unknown`. |
| getStorageUsageAndQuota | `function` |                                                       |         | get storage usage & quota `{     raw: { usage: 180670, quota: 24090080 },     baked: { usage: "230KiB", quota: "980MiB" }    }`                                |
| clearSiteData           | `function` | `indexDBName` required for firefox, `reload` required |         | clears site data which includes all browser storage. Set `reload` params to `true`, to reload the site once storage is clear.                                  |
