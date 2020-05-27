### JSON Plugin

```typescript
import { ScullyConfig } from '@scullyio/scully';

export const config: ScullyConfig = {
  projectRoot: "./src",
  projectName: "animal-crossing",
  outDir: './dist/static',
  routes: {
    '/villagers/:id': {
      type: 'json',
      id: {
        url: 'https://acnhapi.com/v1/villagers',
        property: 'id',
        resultsHandler: (res) => {
          return Object.values(res);
        }
      }
    }
  }
};

```