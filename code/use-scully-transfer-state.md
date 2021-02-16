### useScullyTransferState

```typescript
// my-service.service.ts
import { TransferStateService } from '@scullyio/ng-lib';
...

constructor(
   private http: HttpClient, 
   private transferState: TransferStateService
) { }

  getVillagers(): Observable<Villager[]> {
    return this.transferState.useScullyTransferState(
      'villagers',
      this.http.get<Villager[]>('https://acnhapi.com/v1/villagers')
    )
  }
```