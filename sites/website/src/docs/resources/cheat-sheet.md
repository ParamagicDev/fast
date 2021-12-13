---
id: cheat-sheet
title: Cheat Sheet
sidebar_label: Cheat Sheet
custom_edit_url: https://github.com/microsoft/fast/edit/master/sites/website/src/docs/resources/cheat-sheet.md
---

# Cheat Sheet


## Packages:

### [@microsoft/fast-element](https://www.fast.design/docs/fast-element/getting-started)

**A library that is a lightweight means to easily build performant, memory-efficient, standards-compliant Web Components.**

* Provides a thin layer of opinions on top of [Web Components](https://www.fast.design/docs/resources/why-web-components), lifting the level of abstraction just enough to make it easier and FASTer to [build components]((#building-components)).   
* Use this library when you want to create completely new web components. 

To install the fast-element library, use either `npm` or `yarn`:

```shell
npm install --save @microsoft/fast-element
```

```shell
yarn add @microsoft/fast-element
```

Within your JavaScript or TypeScript code, you can then import library APIs like this:

```ts
import { FASTElement } from "@microsoft/fast-element";
```

---
### [@microsoft/fast-foundation](https://www.fast.design/docs/introduction)

**A library that provides foundational building blocks that can be assembled to create new design systems and component libraries.**

* Exports of this package can generally be thought of as un-styled base components that implement semantic and accessible markup and behavior.   
* Use this library when you want to implement something like Google's Material Design or Twitter Bootstrap.

```ts
import {
  Button as FoundationButton,
  buttonTemplate as template,
} from "@microsoft/fast-foundation";
import { css } from "@microsoft/fast-element";

export class MyButton extends FoundationButton {
  ...
}

export const buttonStyles = css`
  :host {
    background-color: azure;
  }
`;

export const myButton = MyButton.compose({
  baseName: "button",
  baseClass: FoundationButton,
  template,
  styles: buttonStyles,
  shadowOptions: {
    delegatesFocus: true,
  },
});
```
---

### [@microsoft/fast-components](https://www.fast.design/docs/components/getting-started)     

**A component library that implements Microsoft's [FAST Frame Design System](https://www.fast.design/docs/design-systems/fast-frame/).**

* Assembles the building blocks of `@microsoft/fast-foundation` to create its component set. 

* Use this library when you want to integrate [FAST Components](#using-components) into an existing site or app.

To install the components, use either `npm` or `yarn`:
```shell
npm install --save @microsoft/fast-components
``` 
```shell
yarn add @microsoft/fast-components
```

To use a Web Component as a custom element in HTML, the custom element must be registered:

```ts
import { 
    fastButton, 
    provideFASTDesignSystem 
} from "@microsoft/fast-components";

provideFASTDesignSystem()
    .register(
        fastButton() // custom element
    );
```

---
### [@fluentui/web-components](https://www.fast.design/docs/components/getting-started)

**A component library that implements Microsoft's [Fluent Design System](https://www.microsoft.com/design/fluent/#/).**

* Assembles the building blocks of `@microsoft/fast-foundation` to create its component set. 

* Use this library when you want components to look and feel like those found in Microsoft products.

To install the components, use either `npm` or `yarn`:
```shell
npm install --save @fluentui/web-components
``` 
```shell
yarn add @fluentui/web-components
```

To use a Web Component as a custom element in HTML, the custom element must be registered:

```ts
import { 
    fluentButton, 
    provideFluentDesignSystem 
} from "@fluentui/web-components";

provideFluentDesignSystem()
    .register(
        fluentButton() // custom element
    );
```

---
If you are attempting to configure the components for integration into a specific Microsoft product, the following table provides `AccentBaseColor` values you can use:

| Product     | AccentBaseColor | 
| :---        | :---            | 
| Office      | #D83B01         | 
| Word        | #185ABD         | 
| Excel       | #107C41         | 
| PowerPoint  | #C43E1C         | 
| Teams       | #6264A7         | 
| OneNote     | #7719AA         | 
| SharePoint  | #03787C         | 
| Stream      | #BC1948         | 

---


## [Using Components](https://www.fast.design/docs/components/getting-started)
### Setup

To register design system components:

```ts
import { 
    fastButton, 
    provideFASTDesignSystem 
} from "@microsoft/fast-components";

provideFASTDesignSystem()
    .register(
        fastButton() // desired custom component
    );
```

Or, register all system components:

```ts
import { 
    allComponents, 
    provideFASTDesignSystem 
} from "@microsoft/fast-components";

provideFASTDesignSystem().register(allComponents);
```

With the components registered, add any component to the HTML:

```html
<fast-button>Hello world</fast-button>
```

---

### [FAST Components](https://explore.fast.design/)

| Component | Name | Component Explorer | 
| :--- | :--- | :--- | 
| [fast-accordian](https://www.fast.design/docs/components/accordion) | `fastAccordion()` `fastAccordionItem()` | [Accordian](https://explore.fast.design/components/fast-accordion) | 
| [fast-anchor](https://www.fast.design/docs/components/anchor) | `fastAnchor()` | [Anchor](https://explore.fast.design/components/fast-anchor) | 
| [fast-anchored-region](https://www.fast.design/docs/components/anchored-region) | `fastAnchoredRegion()` | [Anchored region](https://explore.fast.design/components/fast-anchored-region) | 
| [fast-avatar](https://www.fast.design/docs/components/avatar) | `fastAvatar()` | [Avatar](https://explore.fast.design/components/fast-avatar) | 
| [fast-badge](https://www.fast.design/docs/components/badge) | `fastBadge()` | [Badge](https://explore.fast.design/components/fast-badge) | 
| [fast-breadcrumb](https://www.fast.design/docs/components/breadcrumb) | `fastBreadcrumb()` `fastBreadcrumbItem()` | [Breadcrumb](https://explore.fast.design/components/fast-breadcrumb) | 
| [fast-button](https://explore.fast.design/components/fast-button) | `fastButton()` | [Button](https://explore.fast.design/components/fast-button) | 
| [fast-card](https://www.fast.design/docs/components/card) | `fastCard()` | [Card](https://explore.fast.design/components/fast-card) | 
| [fast-checkbox](https://www.fast.design/docs/components/checkbox) | `fastCheckbox()` | [Checkbox](https://explore.fast.design/components/fast-checkbox) | 
| [fast-combobox](https://www.fast.design/docs/components/combobox) | `fastCheckbox()` `fastOption()` | [Combobox](https://explore.fast.design/components/fast-combobox) | 
| [fast-data-grid](https://www.fast.design/docs/components/data-grid) | `fastDataGridCell()` `fastDataGridRow()` `fastDataGrid()` | [Data grid](https://explore.fast.design/components/fast-data-grid) | 
| [fast-dialog](https://www.fast.design/docs/components/dialog) | `fastDialog()` | [Dialog](https://explore.fast.design/components/fast-dialog) | 
| [fast-disclosure](https://www.fast.design/docs/components/disclosure) | `fastDisclosure()` | [Disclosure](https://explore.fast.design/components/fast-disclosure) | 
| [fast-divider](https://www.fast.design/docs/components/divider) | `fastDivider()` | [Divider](https://explore.fast.design/components/fast-divider) | 
| [fast-flipper](https://www.fast.design/docs/components/flipper) | `fastFlipper()` | [Flipper](https://explore.fast.design/components/fast-flipper) | 
| [fast-horizontal-scroll](https://www.fast.design/docs/components/horizontal-scroll) | `fastHorizontalScroll()` | 
| [fast-listbox](https://www.fast.design/docs/components/listbox) | `fastListbox()` `fastOption()` | [Listbox](https://explore.fast.design/components/fast-listbox) | 
| [fast-menu](https://www.fast.design/docs/components/menu) | `fastMenu()` `fastMenuItem()` | [Menu](https://explore.fast.design/components/fast-menu) | 
| [fast-number-field](https://www.fast.design/docs/components/number-field) | `fastNumberField()` | [Number field](https://explore.fast.design/components/fast-number-field) | 
| [fast-progress](https://www.fast.design/docs/components/progress) | `fastProgress()` `fastProgressRing()` | [Progress ring](https://explore.fast.design/components/fast-progress-ring) / [Progress](https://explore.fast.design/components/fast-progress) |
| [fast-radio](https://www.fast.design/docs/components/radio) | `fastRadio()` | [Radio](https://explore.fast.design/components/fast-radio) | 
| [fast-radio-group](https://www.fast.design/docs/components/radio-group) | `fastRadio()` `fastRadioGroup()` | [Radio group](https://explore.fast.design/components/fast-radio-group) | 
| [fast-select](https://www.fast.design/docs/components/select) | `fastSelect()` `fastOption()` | [Select](https://explore.fast.design/components/fast-select) | 
| [fast-skeleton](https://www.fast.design/docs/components/skeleton) | `fastSkeleton()` | [Skeleton](https://explore.fast.design/components/fast-skeleton) | 
| [fast-slider](https://www.fast.design/docs/components/slider) | `fastSlider()` `fastSliderLabel()` | [Slider](https://explore.fast.design/components/fast-slider) | 
| [fast-switch](https://www.fast.design/docs/components/switch) | `fastSwitch()` | [Switch](https://explore.fast.design/components/fast-switch) | 
| [fast-tabs](https://www.fast.design/docs/components/tabs) | `fastTab()` `fastTabPanel()` `fastTabs()` | [Tabs](https://explore.fast.design/components/fast-tabs) | 
| [fast-text-area](https://www.fast.design/docs/components/text-area) | `fastTextArea()` | [Text area](https://explore.fast.design/components/fast-text-area) | 
| [fast-text-field](https://www.fast.design/docs/components/text-field) | `fastTextField()` | [Text field](https://explore.fast.design/components/fast-text-field) | 
| [fast-toolbar](https://www.fast.design/docs/components/toolbar) | `fastToolbar()` | [Toolbar](https://explore.fast.design/components/fast-toolbar) | 
| [fast-tooltip](https://www.fast.design/docs/components/tooltip) | `fastTooltip()` | [Tooltip](https://explore.fast.design/components/fast-tooltip) | 
| [fast-tree-view](https://www.fast.design/docs/components/tree-view) | `fastTreeItem()` `fastTreeView()` | [Tree view](https://explore.fast.design/components/fast-tree-view) | 

---
### [Integrations](https://www.fast.design/docs/integrations/introduction)

FAST libraries can also be used in combination with a wide variety of existing technologies.

- [Angular](https://www.fast.design/docs/integrations/angular)
- [ASP.NET](https://www.fast.design/docs/integrations/aspnet)
- [Aurelia](https://www.fast.design/docs/integrations/aurelia)
- [Blazor](https://www.fast.design/docs/integrations/blazor)
- [Ember](https://www.fast.design/docs/integrations/ember)
- [React](https://www.fast.design/docs/integrations/react)
- [Vue](https://www.fast.design/docs/integrations/vue)
- [Webpack](https://www.fast.design/docs/integrations/webpack)

Not seeing an integration for your preferred technology?  Open an issue on [GitHub](https://github.com/microsoft/fast/issues).

---
## [Building Components](https://www.fast.design/docs/components/getting-started)
### Setup

To define a custom element:

```ts
import { FASTElement, customElement } from "@microsoft/fast-element";

@customElement("name-tag") // custom element being created
export class NameTag extends FASTElement {

}
```

With this in place, you can now use your `<name-tag>` element anywhere in HTML with the following markup:

```html
<name-tag></name-tag>
```

---

### [Attributes](https://www.fast.design/docs/fast-element/defining-elements#customizing-attributes)

To add attributes to your HTML element, create properties decorated by the `@attr` decorator:

```ts
import { FASTElement, customElement, attr } from "@microsoft/fast-element";

@customElement("name-tag")
export class NameTag extends FASTElement {
  @attr greeting: string = "Hello";

  greetingChanged() {
    this.shadowRoot!.innerHTML = this.greeting;
  }
}
```

To use a Web Component with Attributes:

```html
<name-tag greeting="Hola"></name-tag>
```

---

#### [Customizing attributes](https://www.fast.design/docs/fast-element/defining-elements#customizing-attributes):

The three modes available through the `mode` property of the attribute configuration:

| Mode | Guidance |
| :-- | :-- | 
| reflect | The default mode that is used if none is specified. 
| boolean |  This mode causes your attribute to function using the HTML boolean attribute behavior.|
| fromView |  This mode skips reflecting the value of the property back to the HTML attribute.

---

Supply a custom `ValueConverter` by setting the converter property of the attribute configuration:

```ts
interface ValueConverter {
    toView(value: any): string;
    fromView(value: string): any;
}
```

Example:

```ts
const numberConverter: ValueConverter = {
  toView(value: number): string {
    return String(value);
  },

  fromView(value: string): number {
    return Number(value);
  }
};

@customElement("my-counter")
export class MyCounter extends FASTElement {
  @attr({
    mode: "reflect",
    converter: numberConverter
  })
  count: number = 0;
}
```

---
### [Templates](https://www.fast.design/docs/fast-element/declaring-templates)

To create an HTML template for an element, import and use the html tagged template helper and pass the template to the `@customElement` decorator:

```ts
import { FASTElement, customElement, attr, html } from "@microsoft/fast-element";

const template = html<NameTag>`
  <div class="header">
    <h3>${x => x.greeting.toUpperCase()}</h3>
    <h4>my name is</h4>
  </div>

  <div class="body">TODO: Name Here</div>

  <div class="footer"></div>
`;

@customElement({
  name: "name-tag",
  template
})
export class NameTag extends FASTElement {
  ...
}
```

---


### [Observables](https://www.fast.design/docs/fast-element/observables-and-state#observable-features)

To enable binding tracking and change notification, properties must be decorated with either `@attr` or `@observable`. 

Use `@attr` for primitive properties (string, bool, number) that are intended to be surfaced on your element as HTML [attributes](#attributes). Use `@observable` for all other property types on an HTMLElement and all observable properties on plain classes.


```ts
import { Observable } from "@microsoft/fast-element";

export class Person {
  @observable firstName = "";
  @observable lastName = "";

  get fullName() {
    return `${this.firstName} ${this.LastName}`;
  }
}
```

---
### [Bindings](https://www.fast.design/docs/fast-element/declaring-templates#understanding-bindings)

| Binding Type | Example | Notes |
| :--- | :--- | :--- |
| Content | `<a>${…}</a>` | Creates a binding to interpolate text or child templates into element content. |
| HTML Attribute | `<a href=${…}></a>` | Creates a binding that uses the setAttribute API. Attribute bindings also support interpolation with text and other bindings. |
| HTML Boolean Attribute | `<input ?disabled=${…}>` | Creates a binding that adds or removes the attribute based on truthy/falsey values. |
| JS Property | `<input :value=${…}>` | Creates a binding that sets a JavaScript property on the element. |
| Event Handler | `<button @click=${…}>...</button>` | Registers an event handler using addEventListener. The listener is automatically removed when the template is unbound. |
| HTML Element Reference | `<button ${ref("myButton")}>...</button>` | Captures a reference to the element and assigns it to the named property on the data source. |
| Slotted Node Capture | `<slot ${slotted("defaultSlotNodes")}></slot>` | Watches the slot for changes and synchronizes those to an array, assigned to the named property on the data source. |
| Child Node Capture | `<div ${children("divChildren")}></div>` | Watches the element's children or changes and synchronizes those to an array, assigned to the named property on the data source. |

---
### [Directives](https://www.fast.design/docs/fast-element/using-directives)

Use the [`when`](https://www.fast.design/docs/fast-element/using-directives#the-when-directive) directive to conditionally render blocks of HTML:

```ts
import { FASTElement, customElement, observable, html, when } from "@microsoft/fast-element";

const template = html<MyApp>`
 ...
  ${when(x => !x.ready, html<MyApp>`
    Loading...
  `)}
`;

@customElement({
  name: "my-app",
  template
})
export class MyApp extends FASTElement {
  @observable ready: boolean = false;
  ...
}
```

---

Use the [`repeat`](https://www.fast.design/docs/fast-element/using-directives#the-repeat-directive) directive to render a list of data:


```ts
import { FASTElement, customElement, observable, html, repeat } from "@microsoft/fast-element";

const template = html<FriendList>`
  ...
    ${repeat(x => x.friends, html<string>`
      <li>${x => x}</li>
    `)}
`;

@customElement({
  name: "friend-list",
  template
})
export class FriendList extends FASTElement {
  @observable friends: Person[] = [];
  ...
}
```

---

Properties available on the context object within a `repeat` block:

| Property | Definition |
| :-- | :-- |
| event | The event object when inside an event handler. |
| parent | The parent view-model when inside a repeat block. |
| parentContext | The parent ExecutionContext when inside a repeat block. This is useful when repeats are nested and the inner-most repeat needs access to the root view-model. |
| index | The index of the current item when inside a repeat block (opt-in). |
| length | The length of the array when inside a repeat block (opt-in). |
| isEven | True if the index of the current item is even when inside a repeat block (opt-in). |
| isOdd | True if the index of the current item is odd when inside a repeat block (opt-in). |
isFirst | True if the current item is first in the array inside a repeat block (opt-in). |
isInMiddle | True if the current item is somewhere in the middle of the array inside a repeat block (opt-in). |
isLast | True if the current item is last in the array inside a repeat block (opt-in). |

---

### [Styles](https://www.fast.design/docs/fast-element/leveraging-css#basic-styles)

`FASTElement` provides a css tagged template helper that allows for the creation of `ElementStyles`.

Adding CSS to a `FASTElement`:

```ts
import { FASTElement, customElement } from "@microsoft/fast-element";
import { css } from "@microsoft/fast-element";
import { disabledOpacity } from "../design-tokens";

const styles = css`
  :host([disabled])] {
    opacity: ${disabledOpacity};
  }
`;

@customElement({
  styles
})
export class MyElement extends FASTElement {}
```

---
#### [Composing styles](https://www.fast.design/docs/fast-element/leveraging-css#composing-styles)

`ElementStyles` can be composed with other styles:

```ts
import { normalize } from "./normalize";

const styles = css`
  ${normalize}
  :host {
    ...
  }
`;
```

---

#### [Partial CSS](https://www.fast.design/docs/fast-element/leveraging-css#partial-css)

Use the `cssPartial` tagged template literal to create reusable blocks of partial CSS:

```ts
import { css, cssPartial } from "@microsoft/fast-element";

const partial = cssPartial`color: red;`;
const styles = css`:host{ ${partial} }`;
```
---
### [CSSDirective](https://www.fast.design/docs/fast-element/leveraging-css#cssdirective)

To create a `CSSDirective`, import and extend `CSSDirective` from `@microsoft/fast-element`:

```ts
import { CSSDirective }  from "@microsoft/fast-element"

class RandomWidth extends CSSDirective {}
```

#### [createCSS method](https://www.fast.design/docs/fast-element/leveraging-css#createcss):

`CSSDirective` has a `createCSS()` method that returns a string to be interpolated into an `ElementStyles`:

```ts
class RandomWidth extends CSSDirective {
  createCSS() {
    return "width: var(--random-width);"
  }
}
```

#### [createBehavior method](https://www.fast.design/docs/fast-element/leveraging-css#createbehavior):

The `createBehavior()` method can be used to create a `Behavior` that is bound to the element using the `CSSDirective`:

```ts
class RandomWidth extends CSSDirective {
  private property = "--random-width";
  createCSS() {
    return `width: var(${this.property});`
  }

  createBehavior() {
    return {
      bind(el) {
        el.style.setProperty(this.property, Math.random() * 100)
      }
      unbind(el) {
        el.style.removeProperty(this.property);
      }
    }
  }
}
```

---
## Design System
### [Creating a Design System](https://www.fast.design/docs/design-systems/creating-a-component-library#defining-a-design-system)

1. Start with the base components defined in `@microsoft/fast-foundation` and compose them with your own styles:

```ts
import {
    Button,
    buttonTemplate as template,
} from "@microsoft/fast-foundation";
import { buttonStyles as styles } from "./special-button.styles";

export const specialButton = Button.compose({
    baseName: "button",
    template,
    styles,
    shadowOptions: {
        delegatesFocus: true,
    },
});

export const buttonStyles = styles;
```




2. Export a `provider function` for your community to use in setting everything up:

```ts
export function provideSpecialDesignSystem(element?: HTMLElement): DesignSystem {
    return DesignSystem.getOrCreate(element).withPrefix("special");
}
```

---

### [Design Tokens](https://www.fast.design/docs/design-systems/design-tokens)


[Creating a token](https://www.fast.design/docs/design-systems/design-tokens#create-a-token):

```ts
import { DesignToken } from "@microsoft/fast-foundation";

// create a design token
export const specialColor = DesignToken.create<string>("special-color");
```


[Using design tokens in CSS](https://www.fast.design/docs/design-systems/design-tokens#using-design-tokens-in-css):
```ts
// use the design token to build styles
const styles = css`
  :host {
    background: ${specialColor};
  }
`;

const ancestor = document.querySelector("my-ancestor") as FASTElement;
const descendent = ancestor.querySelector("my-descendent") as FASTElement;
```

[Setting values](https://www.fast.design/docs/design-systems/design-tokens#setting-values):
```ts
// change the value for a given element
specialColor.setValueFor(ancestor, "#FFF");
specialColor.setValueFor(descendent, "#000");
```

[Getting values](https://www.fast.design/docs/design-systems/design-tokens#getting-values):
```ts
// get the value
specialColor.getValueFor(ancestor); // "#FFF"
specialColor.getValueFor(descendent); // "#000"
```

[Deleting values](https://www.fast.design/docs/design-systems/design-tokens#deleting-values):
```ts
// unset the value (inherits from ancestor)
specialColor.deleteValueFor(descendent);
specialColor.getValueFor(descendent); // "#FFF"
```

---
#### Configuring a FAST Design Token:

```ts
// change the value for the typeRampBaseFontSize design token
const myElement = document.querySelector("my-element") as FASTElement;

typeRampBaseFontSize.setValueFor(myElement, "20px");
```

FAST exposes non-color related [Design Tokens](https://www.fast.design/docs/design-systems/fast-frame#fast-frame-design-tokens) that can be used to configure components stylistically. 

For Design Tokens related to color, see the [adaptive color system](https://www.fast.design/docs/design-systems/fast-frame/#adaptive-color-system).

---

## [Contributing to FAST](https://www.fast.design/docs/community/join)

**Connect with us**:

- Join our [Discord](https://discord.gg/FcSNfg4) server.
- Report bugs, request features through [Github](https://github.com/Microsoft/fast/issues/new/choose).


**Unsure of what to work on?**

- Here are [good first issues](https://github.com/Microsoft/fast/labels/community:good-first-issue).

---
### [Contributor Guide](https://www.fast.design/docs/community/contributor-guide/)
- [Machine setup](https://www.fast.design/docs/community/contributor-guide/#machine-setup)
- [Cloning the repository](https://www.fast.design/docs/community/contributor-guide/#cloning-the-repository)
- [Installing & building](https://www.fast.design/docs/community/contributor-guide/#installing-and-building)
- [Testing](https://www.fast.design/docs/community/contributor-guide/#testing)
- [Submitting a pull request](https://www.fast.design/docs/community/contributor-guide/#submitting-a-pull-request)
- [Merging a pull request](https://www.fast.design/docs/community/contributor-guide/#merging-a-pull-request)

---
### [Contributing to fast-component](https://www.fast.design/docs/community/contributor-guide)



```shell
cd packages/web-components/fast-components
yarn start
```


[Storybook](https://storybook.js.org/) will open in a browser window at `localhost:6006`.


---

### [Contributing to documentation](https://www.fast.design/docs/community/writing-documentation)

```shell
cd sites/website
yarn start
```

[Docusaurus](https://docusaurus.io/) will open in a browser window at `localhost:3000`.