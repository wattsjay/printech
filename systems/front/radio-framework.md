# Radio Framework

System design interviews tend to be open-ended and vague. If the interviewer does not tel you which areas to focus on, you can make use of the Radio Framework to give an outline of what you are going to cover.

1. `Requirements`: spend time understanding the scope by asking clarifying questions.
2. `Architecture`: Identify the key components of the product and how they relate to each other.
3. `Data Model`: Describe the various data-entities, the fields they contain, and which components they belong to.

  > COMMENT: What about models?

4. `Interface Design` (API): Define the interface between components and features, the functionality of each API, and their parameters and responses.
5. `Optimization and Deep Dive`: Discuss possible optimization opportunities and specific areas of interest when building the product.

## Requirements

Start off with requirements gathering & clarification as things are usually left under specified on purpose. Spend a few minutes clarifying the requirements.

Some examples include:

  - What devices should the system support?
  - What's the primary device?
  - Which browsers?
  - Does the app need to work offline?
  - Do we need to support internationalization?
  - How much styling & customization should we allow?
  - Micro-frontend?
  - Organization? Domains etc.

## Architecture

For components, list down the various subcomponents that will exist within it and what data is being passed among each component. Stateful vs controlled components (features vs components?).

For example an Image Carousel:

  1. Main Image
  2. Thumbnail
  3. Image Store

It would be helpful to draw diagrams to illustrate the entities and their relationships. Which subcomponent communicates with which when a user interaction occurs.

For application design, common architectures include `Mode-View-Controller`, `Model-View-ViewModel`, `Flux`, `N-tier`.

  > TO-DO: Read up on the architecture patterns above.

## Data Model

  The `greatfrontend` resource is quite generic here. So flesh this out yourself and include Models.

  > TO-DO: Flesh this out.

## Interface Design (API)

- What are the configuration options you would allow for the component? What would be good defaults?

```ts
  function Component({
    foo = 1
  }:{
    foo?: number;
  }) {
    
  }
```

- Follow the `open-closed principle`. The component should be open for extension but closed for modification.
- If a component is meant to be `heavily styled or customized` by its user, extra care should go into the design of the props and to allow users to customize the look and feel of the components. Some techniques include `Composition`, `Render Props`, or `Style` and `className` props.

> TO-READ: Terms above.

  For applications, API design refers to the HTTP/network API parameters and the shape of the response.

## Optimization & Deep Dive

You probably won't have time to go into every area here, so during an interview you would probably choose the most relevant feature or component to go into deeper.

Showing traits of these areas and being able to dive deep into them are traits of senior front-end engineers.

### 1. UX

There are too many, but some low-hanging fruits include:

  - Reflect state: pending request, error etc.
  - Display empty state if no items in a list.
  - Destructive actions should have a confirmation step.
  - Disable interactive elements if they trigger an asynchronous step.
  - If there are search inputs involved, each keystroke should not fire
    a network request.
  - Handle extreme cases: Long strings should not break the UI.
  - Keyboard friendliness: Shortcuts & Focus (check tab order)

  > TO-DO: Make sure you understand focus & tab order.

### 2. PERFORMANCE

  - `Loading Speed`: The less JS the component contains, the less JS the browser has to download to load the component and the lower the network request time. It's also important to modularize components and allow users to download only the necessary JS modules needed for their use case.
  - Responsiveness:
    1. If a user interaction result in displaying of data that has to be loaded over the network, there will be a delay between the user interaction and updating the UI. Minimizing that delay or removing it entirely is the key to improving responsiveness.
    2. JS in a browser is single-threaded. The browser can only execute one line of code at any one time. The less work the component has to do when a user does something on the page, the faster the component can update the UI to respond to the changes.

    > TO-DO: Make sure you understand worker threads.

  - Memory Space: The more memory your component takes up on the page, the slower the browser performs and the experience will feel sluggish.
  - Optimization Tips:

    1. Render only what is displayed on the screen. If you have a large list, render only what is shown to the user. Make use of virtualization.
    2. Lazy load only necessary data.

    > TO-DO: Read up on lazy-loading.

    3. Preloading/prefetching data ahead of time: Load the next image or nth images if the user clicks `next` in rapid succession.
    
### 3. ACCESSIBILITY (a11y)

  - Color contrast
  - Keyboard friendliness
  - Visual impairment
  - Transcripts for audio

  - Foreground colors should have sufficient contrast with the BG colors.
  - Use the correct HTML tags for semantics. Or use `aria-role`.
  - Clickable items should have `tabindex` attribute, and also `cursor:pointer` styling to indicate that they can be clicked on.
  - Images should have `alt` text, which will be read out by screen readers and act as a fallback description if the image fails to load.
  - `Aria-label` helps provide context to elements which are non-obvious to non-visual users. E.g. an icon button without any text label within it should have a `aria-label` attribute so that the intention is clear.

  > TO-DO: Read up on a11y

### 4. INTERNATIONALIZATION (i18n)

Internationalization is the design and development of a product, application or document content that enables easy localization for target audiences that vary in culture, region, or language. Typically, components should not have to worry about i18n unless under a few specific circumstances:

  1. Component uses strings.
  2. Order of content matters: RTL languages.

  > TO-READ: React implementation of i18n.

### 5. MULTI DEVICE SUPPORT

Not much of value was given by `frontendinterviewhandbook`.

### 6. SECURITY

Most of the time, components aren't exposed to security vulnerabilities, but it can still happen. Here are the more common security vulnerabilities you should be aware of.

1. XSS
2. CSRF
3. Clickjacking
4. `rel=noopener`