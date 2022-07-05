---
id: fast-components.fastbreadcrumb
title: fastBreadcrumb variable
hide_title: true
---
<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[@microsoft/fast-components](./fast-components.md) &gt; [fastBreadcrumb](./fast-components.fastbreadcrumb.md)

## fastBreadcrumb variable

A function that returns a [Breadcrumb](./fast-foundation.breadcrumb.md) registration for configuring the component with a DesignSystem. Implements [breadcrumbTemplate](./fast-foundation.breadcrumbtemplate.md)

<b>Signature:</b>

```typescript
fastBreadcrumb: (overrideDefinition?: import("@microsoft/fast-foundation").OverrideFoundationElementDefinition<{
    baseName: string;
    template: import("@microsoft/fast-foundation").FoundationElementTemplate<import("@microsoft/fast-element").ViewTemplate<Breadcrumb, any>, import("@microsoft/fast-foundation").FoundationElementDefinition>;
    styles: import("@microsoft/fast-foundation").FoundationElementTemplate<import("@microsoft/fast-element").ElementStyles, import("@microsoft/fast-foundation").FoundationElementDefinition>;
}> | undefined) => import("@microsoft/fast-foundation").FoundationElementRegistry<{
    baseName: string;
    template: import("@microsoft/fast-foundation").FoundationElementTemplate<import("@microsoft/fast-element").ViewTemplate<Breadcrumb, any>, import("@microsoft/fast-foundation").FoundationElementDefinition>;
    styles: import("@microsoft/fast-foundation").FoundationElementTemplate<import("@microsoft/fast-element").ElementStyles, import("@microsoft/fast-foundation").FoundationElementDefinition>;
}, typeof Breadcrumb>
```

## Remarks

Generates HTML Element: `<fast-breadcrumb>`