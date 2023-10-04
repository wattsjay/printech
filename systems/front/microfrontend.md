# `Microfrontend`

https://micro-frontends.org/

Think about a website or web app as a composition of features which are owned by independent teams. Each team has a distinct area of business or mission it cares about and specializes in. A team is cross-functional and develops its features end-to-end, from database to user-interface.

1. Use a dynamic script tag to load the `microfrontend` JS to the page.
2. The `mfe` provides a method to start the rendering process.
3. The `mfe` renders to a div exposed by the `container`.
4. Use the `React Portals API` to render components outside the DOM tree where the `mfe` is rendered.