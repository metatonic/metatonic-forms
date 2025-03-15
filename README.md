# metatonic-forms

## Installation

## Usage

### App

```TypeScript
import {BaseApp} from '@metatonic/forms'
class FormsApp {
    constructor() {
        super('https://api.example.com/v1/openapi-file');
    } 
}
const formsApp = FormsApp();
```


### Control Overrides and Variants
By default Metatonic forms provides editors and selects for all models in your application but you can either override the defaults or add variants that can be used through out your app. 
```TypeScript
app.editors.default('MyModel', MyEditorComponent)
app.selects.default('MyModel', MySelectComponent)
app.selects.multi.default('MyModel', MyMultiSelectComponent) // Can also just have have select handle both single and multi select
app.editors.variant('MyModel', 'MyVariant', MyEditorComponent)
app.selects.variant('MyModel', 'MyVariant',MySelectComponent)
```

### Adding to an application

```tsx
<MtFormContext app={app}>
  <MTForm post='/v1/my-collection'/>
  <MTForm put={`/v1/my-collection/${id}`}/>
  <MTEdit for='MyModel' data={data} change={onEdit}/>
  <MTSelect for='MyModel' value={selectedId} change={onSelect}/>
</MTFormContext>
