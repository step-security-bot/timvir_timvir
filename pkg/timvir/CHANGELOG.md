# timvir

## 0.2.36

### Patch Changes

- 328ae54: Add explicit type annotations to timvir/builtins

  Previously we would leak the fact that Timvir internally is using Linaria for styling.
  To the user of this library, the components in timvir/builtins should appear just like any other React components.

- 4f54ace: Hide Linaria from the public facing API

  With this change, we no longer leak Linaria types through the public facing Timvir API.
  Linaria still remains in use internally.
  But this fact is no longer exposed to users of Timvir.

## 0.2.35

### Patch Changes

- 3289108: Relax Link type

  The `Link` prop on `timvir/core` `<Page>` used to heavily lean on the type used by Next.js.
  In particular, it claimed to support `passHref` and `legacyBehavior` props.
  This is no longer the case.
  The `Link` can now be a plain HTMLAnchorElement (ie. `<a>`), or any component which implements a compatible inteface.
