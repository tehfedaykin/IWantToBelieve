### Villager Service

```typescript
// my-service.service.ts

  getVillagers(): Observable<Villager[]> {
    return this.http.get<Villager[]>('https://acnhapi.com/v1/villagers')
  }
```