# Lazy Loading

## Lazy Loading at Documents

## Lazy Loading at HomePage
The packages we used in Home Page is
```javascript
import {
    LazyLoadComponent,
    trackWindowScroll
} from "react-lazy-load-image-component";
import "react-lazy-load-image-component/src/effects/opacity.css";
```

The usage of home page lazy loading can be found at `src/HomeApp/ArchiveHome.js`, and the usage of `ArchiveHome.js` can be found at `src/HomeApp/HomePage.js`.

`ArchiveHome` takes an empty box as a placeholder. The purpose of making `ArchiveHome` is to check loading according to `scrollPosition`. The documentation can be found at [here](https://github.com/Aljullu/react-lazy-load-image-component)

```javascript
<LazyLoadComponent placeholder={<Box sx={{ width: 300, height: 300 }} />} scrollPosition={scrollPosition} threshold={1} >
```

In order to activate lazy loading at `HomePage`, `HomePage` renders `<NetworkComponent/>` first as a initial placeholder.

```javascript
<List>
    <NetworkComponent/>
    <Divider/>
    <ArchiveHome components={sample} scrollPosition={window.scrollY}/>
</List>
```
