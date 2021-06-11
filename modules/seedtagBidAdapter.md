# Overview

```
Module Name: Seedtag Bidder Adapter
Module Type: Bidder Adapter
Maintainer: prebid@seedtag.com
```

# Description

Module that connects to Seedtag demand sources to fetch bids.

# Test Parameters

## Sample Banner Ad Unit

```js
const adUnits = [
  {
    code: '/21804003197/prebid_test_300x250',
    mediaTypes: {
      banner: {
        sizes: [[300, 250]]
      }
    },
    bids: [
      {
        bidder: 'seedtag',
        params: {
          publisherId: '0000-0000-01',      // required
          adUnitId: '0000',                 // required
          placement: 'banner',              // required
          adPosition: 0                     // optional
        }
      }
    ]
  }
]
```

## Sample inStream Video Ad Unit

```js
var adUnits = [{
  code: 'video',
  mediaTypes: {
    video: {
      context: 'instream',   // required
      playerSize: [600, 300], // required
      mimes: ['video/mp4'], // recommended
      minduration: 5,       // optional
      maxduration: 60,      // optional
      boxingallowed: 1,     // optional
      skip: 1,              // optional
      startdelay: 1,        // optional
      linearity: 1,         // optional
      battr: [1, 2],        // optional
      maxbitrate: 10,       // optional
      playbackmethod: [1],  // optional
      delivery: [1],        // optional
      placement: 1,         // optional
    }
  },
  bids: [
    {
      bidder: 'seedtag',
      params: {
        publisherId: '0000-0000-01',    // required
        adUnitId: '0000',               // required
        placement: 'video',             // required
        adPosition: 0,                  // optional
        video: { // optional
          context: 'instream',   // optional
          playerSize: [600, 300], // optional
          mimes: ['video/mp4'], // optional
          minduration: 5,       // optional
          maxduration: 60,      // optional
          boxingallowed: 1,     // optional
          skip: 1,              // optional
          startdelay: 1,        // optional
          linearity: 1,         // optional
          battr: [1, 2],        // optional
          maxbitrate: 10,       // optional
          playbackmethod: [1],  // optional
          delivery: [1],        // optional
          placement: 1,         // optional
        }
      }
    }
  ]
}];
```

## Force testing a creative
In order to see how formats look like, you can test them with adunit config, or with url directly.

### With adunit config
This is just for testing, remove it before go to production
```
[
  {
    code: '/21804003197/prebid_test_300x250',
    mediaTypes: {
      banner: {
        sizes: [[300, 250]]
      }
    },
    bids: [
      {
        bidder: 'seedtag',
        params: {
          ...,
          testCreative: "display-open-300x250"
        }
      }
    ]
  }
]
```

### With url params
Just add this parameter to the publisher page : 
http://publisherpage.com/article?pbjs_seedtag_creative=display-open-300x250

### Available creative for test
| value | size |
| ----- | ---- |
| display-open-120x600 | 120x600 |
| display-open-160x600 | 160x600 |
| display-open-250x250 | 250x250 |
| display-open-300x50 | 300x50 |
| display-open-300x250 | 300x250 |
| display-open-300x600 | 300x600 |
| display-open-320x50 | 320x50 |
| display-open-320x100 | 320x100 |
| display-open-320x480 | 320x480 |
| display-open-336x280 | 336x280 |
| display-open-468x60 | 468x60 |
| display-open-728x90 | 728x90 |
| display-open-970x90 | 970x90 |
| display-open-970x250 | 970x250 |
| display-open-970x300 | 970x300 |
| display-open-980x90 | 980x90 |
| display-open-980x250 | 980x250 |
| display-direct-fid | 600x600 |
| video-direct-fiv | 600x600 |
| video-direct-piv | 600x600 |
| video-open-piv | 600x600 |
| adtag:[id] | - |
