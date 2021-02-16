### Use Meta & Title Services

```typescript
...
import { Meta, Title } from '@angular/platform-browser';

...
import { Component, OnInit } from '@angular/core';

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
        this.metaTagService.updateTag({ name: 'keywords', content: `Animal Crossing New Horizons ${villager.name['name-USen']}` });
        this.metaTagService.updateTag({ name: 'title', content: `Animal Crossing New Horizons ${villager.name['name-USen']}` });
        this.metaTagService.updateTag({ name: 'description', content: `Information about Animal Crossing New Horizons villager ${villager.name['name-USen']}` });
        this.metaTagService.updateTag({ itemProp: 'image', content: villager.imageUri }, 'itemProp="image"');
      })
    )
  }

}

```