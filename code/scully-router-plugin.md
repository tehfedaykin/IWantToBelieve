### Configuring Routes with Dynamic Params

```typescript
import { ScullyConfig } from '@scullyio/scully';

export const config: ScullyConfig = {
  projectRoot: "./src",
  projectName: "animal-crossing",
  outDir: './dist/static',
  routes: {
    //route config for villagers/:id route
  }
};

```