### Use Meta & Title Services

```typescript
...
import { Meta, Title } from '@angular/platform-browser';

...
export class VillagerComponent implements OnInit {
  public villager$;
  constructor(
    private route: ActivatedRoute,
    private acnhService: AcnhService,
    private metaTagService: Meta,
    private titleTagService: Title
  ) { }

  ngOnInit(): void {
    this.villager$ = this.route.paramMap.pipe(
      switchMap((params: ParamMap) => {
        return this.acnhService.getVillager(params.get('id'))
      }),
      tap((villager: Villager) => {
        this.titleTagService.setTitle(villager.name['name-USen']);
        this.metaTagService.updateTag(
          { name: 'keywords', 
            content: `Animal Crossing New Horizons ${villager.name['name-USen']}` 
          },
          'name="keywords"');
        this.metaTagService.updateTag(
          { name: 'title', 
            content: `Animal Crossing New Horizons ${villager.name['name-USen']}` 
          },
          'name="title"');
        this.metaTagService.updateTag(
          { name: 'description', 
            content: `${villager.name['name-USen']} is ${villager.personality}` 
          },
          'name="description"');
        this.metaTagService.updateTag(
          { itemProp: 'image', 
          content: villager.imageUrl 
          }, 'itemProp="image"');
      })
    )
  }

}
```