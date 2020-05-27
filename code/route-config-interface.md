### RouteConfig Interface

```typescript
interface RouteConfig {
  '[route: string]': {
    type: 'json';
    postRenderers?: string[];
    [paramName: string]: {
      url: string;
      property: string;
      headers?: HeadersObject;
      resultsHandler?: (raw: any) => any[];
    };
  };
}
```