# Video

https://www.npmjs.com/package/@nstudio/nativescript-exoplayer

```
$ ns plugin add @nstudio/nativescript-exoplayer
```

```typescript
// somewhere at top of your component or bootstrap file
import { registerElement } from "@nativescript/angular";
import { Video } from '@nstudio/nativescript-exoplayer';
registerElement("Video", () => Video);
```

```
  <Video
      src="https://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4"
      autoplay="true"
      height="300"></Video>
```
