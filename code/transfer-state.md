### TransferState

```typescript
// my-service.service.ts

import { TransferState, makeStateKey } from '@angular/platform-browser';
...
  constructor(private http: HttpClient, private ngState: TransferState) { }

  getVillagers(): Observable<Villager[]> {
    const villagersKey = makeStateKey('villagers');
    const cachedResponse = this.ngState.get(villagersKey, null);

    if (!cachedResponse) {
      return this.http.get<Villager[]>('http://acnhapi.com/villagers').pipe(
        tap((res) => this.ngState.set(villagersKey, res))
      )
    }

    return of(cachedResponse);
  }
...
```