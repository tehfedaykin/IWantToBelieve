### ACFG Application Routes

```typescript
const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'villagers', component: VillagersComponent },
  { path: 'villagers/:id', component: VillagerComponent },
  { path: 'fish', component: FishiesComponent },
  { path: 'fish/:id', component: FishComponent },
  { path: 'insects', component: InsectsComponent },
  { path: 'insects/:id', component: InsectComponent },
  { path: 'fossils', component: FossilsComponent }
];
```