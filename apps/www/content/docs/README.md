# Đây là các tài liệu hướng dẫn của shadcn/ui được viết trong dạng mdx

Hãy dùng các hướng dẫn này cho việc thành chiếu đễ tạo ra các components sáng tạo hơn dựa vào các mẫu có sẵn

## Directory Structure

- 📄 about.mdx
- 📄 changelog.mdx
- 📄 cli.mdx
- 📁 components/
  - 📄 accordion.mdx
  - 📄 alert-dialog.mdx
  - 📄 alert.mdx
  - 📄 aspect-ratio.mdx
  - 📄 avatar.mdx
  - 📄 badge.mdx
  - 📄 breadcrumb.mdx
  - 📄 button.mdx
  - 📄 calendar.mdx
  - 📄 card.mdx
  - 📄 carousel.mdx
  - 📄 chart.mdx
  - 📄 checkbox.mdx
  - 📄 collapsible.mdx
  - 📄 combobox.mdx
  - 📄 command.mdx
  - 📄 context-menu.mdx
  - 📄 data-table.mdx
  - 📄 date-picker.mdx
  - 📄 dialog.mdx
  - 📄 drawer.mdx
  - 📄 dropdown-menu.mdx
  - 📄 form.mdx
  - 📄 hover-card.mdx
  - 📄 input-otp.mdx
  - 📄 input.mdx
  - 📄 label.mdx
  - 📄 menubar.mdx
  - 📄 navigation-menu.mdx
  - 📄 pagination.mdx
  - 📄 popover.mdx
  - 📄 progress.mdx
  - 📄 radio-group.mdx
  - 📄 resizable.mdx
  - 📄 scroll-area.mdx
  - 📄 select.mdx
  - 📄 separator.mdx
  - 📄 sheet.mdx
  - 📄 sidebar.mdx
  - 📄 skeleton.mdx
  - 📄 slider.mdx
  - 📄 sonner.mdx
  - 📄 switch.mdx
  - 📄 table.mdx
  - 📄 tabs.mdx
  - 📄 textarea.mdx
  - 📄 toast.mdx
  - 📄 toggle-group.mdx
  - 📄 toggle.mdx
  - 📄 tooltip.mdx
  - 📄 typography.mdx
- 📄 components-json.mdx
- 📁 dark-mode/
  - 📄 astro.mdx
  - 📄 index.mdx
  - 📄 next.mdx
  - 📄 remix.mdx
  - 📄 vite.mdx
- 📄 figma.mdx
- 📄 index.mdx
- 📁 installation/
  - 📄 astro.mdx
  - 📄 gatsby.mdx
  - 📄 index.mdx
  - 📄 laravel.mdx
  - 📄 manual.mdx
  - 📄 next.mdx
  - 📄 remix.mdx
  - 📄 vite.mdx
- 📄 monorepo.mdx
- 📄 react-19.mdx
- 📄 theming.mdx
- 📄 v0.mdx

## File Contents

### 📄 about.mdx

```
---
title: About
description: Powered by amazing open source projects.
---

## About

[ui.shadcn.com](https://ui.shadcn.com) is a project by [shadcn](https://shadcn.com).

## Credits

- [Radix UI](https://radix-ui.com) - For the primitives.
- [Vercel](https://vercel.com) - Where I host all my projects.
- [Shu Ding](https://shud.in) - The typography style is adapted from his work on Nextra.
- [Cal](https://cal.com) - Where I copied the styles for the first component: the `Button`.
- [cmdk](https://cmdk.paco.me) - For the `<Command />` component.

## License

MIT © [shadcn](https://shadcn.com)

```

### 📄 changelog.mdx

```
---
title: Changelog
description: Latest updates and announcements.
toc: false
---

## August 2024 - npx shadcn init

The new CLI is now available. It's a complete rewrite with a lot of new features and improvements. You can now install components, themes, hooks, utils and more using `npx shadcn add`.

This is a major step towards distributing code that you and your LLMs can access and use.

1. First up, the cli now has support for all major React framework out of the box. Next.js, Remix, Vite and Laravel. And when you init into a new app, we update your existing Tailwind files instead of overriding.
2. A component now ship its own dependencies. Take the accordion for example, it can define its Tailwind keyframes. When you add it to your project, we’ll update your tailwind.config.ts file accordingly.
3. You can also install remote components using url. `npx shadcn add https://acme.com/registry/navbar.json`.
4. We have also improve the init command. It does framework detection and can even init a brand new Next.js app in one command. `npx shadcn init`.
5. We have created a new schema that you can use to ship your own component registry. And since it has support for urls, you can even use it to distribute private components.
6. And a few more updates like better error handling and monorepo support.

You can try the new cli today.

```bash
npx shadcn init sidebar-01 login-01
```

### Update Your Project

To update an existing project to use the new CLI, update your `components.json` file to include import aliases for your **components**, **utils**, **ui**, **lib** and **hooks**.

```json showLineNumbers {7-13} title="components.json"
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "tailwind": {
    // ...
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  }
}
```

If you're using a different import alias prefix eg `~`, replace `@` with your prefix.

## April 2024 - Introducing Lift Mode

We're introducing a new mode for [Blocks](/blocks) called **Lift Mode**.

Enable Lift Mode to automatically "lift" smaller components from a block template for copy and paste.

<a href="/blocks">
  <Image
    src="/images/lift-mode-light.png"
    width="1432"
    height="1050"
    alt="Lift Mode"
    className="border dark:hidden shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <Image
    src="/images/lift-mode-dark.png"
    width="1432"
    height="1069"
    alt="Lift Mode"
    className="border hidden dark:block shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <span class="sr-only">View the blocks library</span>
</a>

With Lift Mode, you'll be able to copy the smaller components that make up a block template, like cards, buttons, and forms, and paste them directly into your project.

Visit the [Blocks](/blocks) page to try it out.

## March 2024 - Introducing Blocks

One of the most requested features since launch has been layouts: admin dashboards with sidebar, marketing page sections, cards and more.

**Today, we're launching [**Blocks**](/blocks)**.

<a href="/blocks">
  <Image
    src="/images/dashboard-1.jpg"
    width="716"
    height="430"
    alt="Admin dashboard"
    className="border dark:hidden shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <Image
    src="/images/dashboard-1-dark.jpg"
    width="716"
    height="430"
    alt="Admin dashboard"
    className="border hidden dark:block shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <span class="sr-only">View the blocks library</span>
</a>

Blocks are ready-made components that you can use to build your apps. They are fully responsive, accessible, and composable, meaning they are built using the same principles as the rest of the components in shadcn/ui.

We're starting with dashboard layouts and authentication pages, with plans to add more blocks in the coming weeks.

### Open Source

Blocks are open source. You can find the source on GitHub. Use them in your projects, customize them and contribute back.

<a href="/blocks">
  <Image
    src="/images/dashboard-2.jpg"
    width="716"
    height="420"
    alt="AI Playground"
    className="border dark:hidden shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <Image
    src="/images/dashboard-2-dark.jpg"
    width="716"
    height="420"
    alt="AI Playground"
    className="border hidden dark:block shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <span class="sr-only">View the blocks library</span>
</a>

### Request a Block

We're also introducing a "Request a Block" feature. If there's a specific block you'd like to see, simply create a request on GitHub and the community can upvote and build it.

<a href="/blocks">
  <Image
    src="/images/dashboard-3.jpg"
    width="716"
    height="420"
    alt="Settings Page"
    className="border dark:hidden shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <Image
    src="/images/dashboard-3-dark.jpg"
    width="716"
    height="420"
    alt="Settings Page"
    className="border hidden dark:block shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <span class="sr-only">View the blocks library</span>
</a>

### v0

If you have a [v0](https://v0.dev) account, you can use the **Edit in v0** feature to open the code on v0 for prompting and further generation.

<div class="w-full aspect-video bg-background flex items-center justify-center border shadow-sm rounded-lg overflow-hidden mt-6">
  <svg
    viewBox="0 0 40 20"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
    className="text-foreground w-40 h-40"
  >
    <path
      d="M23.3919 0H32.9188C36.7819 0 39.9136 3.13165 39.9136 6.99475V16.0805H36.0006V6.99475C36.0006 6.90167 35.9969 6.80925 35.9898 6.71766L26.4628 16.079C26.4949 16.08 26.5272 16.0805 26.5595 16.0805H36.0006V19.7762H26.5595C22.6964 19.7762 19.4788 16.6139 19.4788 12.7508V3.68923H23.3919V12.7508C23.3919 12.9253 23.4054 13.0977 23.4316 13.2668L33.1682 3.6995C33.0861 3.6927 33.003 3.68923 32.9188 3.68923H23.3919V0Z"
      fill="currentColor"
    ></path>
    <path
      d="M13.7688 19.0956L0 3.68759H5.53933L13.6231 12.7337V3.68759H17.7535V17.5746C17.7535 19.6705 15.1654 20.6584 13.7688 19.0956Z"
      fill="currentColor"
    ></path>
  </svg>
</div>

That's it. _Looking forward to seeing what you build with Blocks_.

## March 2024 - Breadcrumb and Input OTP

We've added a new Breadcrumb component and an Input OTP component.

### Breadcrumb

An accessible and flexible breadcrumb component. It has support for collapsed items, custom separators, bring-your-own routing `<Link />` and composable with other shadcn/ui components.

<ComponentPreview name="breadcrumb-demo" />

[See more examples](/docs/components/breadcrumb)

### Input OTP

A fully featured input OTP component. It has support for numeric and alphanumeric codes, custom length, copy-paste and accessible. Input OTP is built on top of [input-otp](https://github.com/guilhermerodz/input-otp) by [@guilherme_rodz](https://twitter.com/guilherme_rodz).

<ComponentPreview name="input-otp-demo" />

[Read the docs](/docs/components/input-otp)

If you have a [v0](https://v0.dev), the new components are available for generation.

## December 2023 - New components, CLI and more

We've added new components to shadcn/ui and made a lot of improvements to the CLI.

Here's a quick overview of what's new:

- [**Carousel**](#carousel) - A carousel component with motion, swipe gestures and keyboard support.
- [**Drawer**](#drawer) - A drawer component that looks amazing on mobile.
- [**Pagination**](#pagination) - A pagination component with page navigation, previous and next buttons.
- [**Resizable**](#resizable) - A resizable component for building resizable panel groups and layouts.
- [**Sonner**](#sonner) - The last toast component you'll ever need.
- [**CLI updates**](#cli-updates) - Support for custom **Tailwind prefix** and `tailwind.config.ts`.

### Carousel

We've added a fully featured carousel component with motion, swipe gestures and keyboard support. Built on top of [Embla Carousel](https://www.embla-carousel.com).

It has support for infinite looping, autoplay, vertical orientation, and more.

<ComponentPreview name="carousel-demo" />

### Drawer

Oh the drawer component 😍. Built on top of [Vaul](https://github.com/emilkowalski/vaul) by [emilkowalski\_](https://twitter.com/emilkowalski_).

Try opening the following drawer on mobile. It looks amazing!

<ComponentPreview name="drawer-demo" />

### Pagination

We've added a pagination component with page navigation, previous and next buttons. Simple, flexible and works with your framework's `<Link />` component.

<ComponentPreview name="pagination-demo" />

### Resizable

Build resizable panel groups and layouts with this `<Resizable />` component.

<ComponentPreview name="resizable-demo-with-handle" />

`<Resizable />` is built using [react-resizable-panels](https://github.com/bvaughn/react-resizable-panels) by [bvaughn](https://github.com/bvaughn). It has support for mouse, touch and keyboard.

### Sonner

Another one by [emilkowalski\_](https://twitter.com/emilkowalski_). The last toast component you'll ever need. Sonner is now availabe in shadcn/ui.

<ComponentPreview name="sonner-demo" />

### CLI updates

This has been one of the most requested features. You can now configure a custom Tailwind prefix and the cli will automatically prefix your utility classes when adding components.

This means you can now easily add shadcn/ui components to existing projects like Docusaurus, Nextra...etc. A drop-in for your existing design system with no conflict. 🔥

```tsx /tw-/
<AlertDialog className="tw-grid tw-gap-4 tw-border tw-bg-background tw-shadow-lg" />
```

It works with `cn`, `cva` and CSS variables.

The cli can now also detect `tailwind.config.ts` and add the TypeScript version of the config for you.

That's it. Happy Holidays.

## July 2023 - JavaScript

This project and the components are written in TypeScript. **We recommend using TypeScript for your project as well**.

However we provide a JavaScript version of the components, available via the [cli](/docs/cli).

```txt
Would you like to use TypeScript (recommended)? no
```

To opt-out of TypeScript, you can use the `tsx` flag in your `components.json` file.

```json {10} title="components.json"
{
  "style": "default",
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "src/app/globals.css",
    "baseColor": "zinc",
    "cssVariables": true
  },
  "rsc": false,
  "tsx": false,
  "aliases": {
    "utils": "~/lib/utils",
    "components": "~/components"
  }
}
```

To configure import aliases, you can use the following `jsconfig.json`:

```json {4} title="jsconfig.json"
{
  "compilerOptions": {
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```

## June 2023 - New CLI, Styles and more

I have a lot of updates to share with you today:

- [**New CLI**](#new-cli) - Rewrote the CLI from scratch. You can now add components, dependencies and configure import paths.
- [**Theming**](#theming-with-css-variables-or-tailwind-colors) - Choose between using CSS variables or Tailwind CSS utility classes for theming.
- [**Base color**](#base-color) - Configure the base color for your project. This will be used to generate the default color palette for your components.
- [**React Server Components**](#react-server-components) - Opt out of using React Server Components. The CLI will automatically append or remove the `use client` directive.
- [**Styles**](#styles) - Introducing a new concept called _Style_. A style comes with its own set of components, animations, icons and more.
- [**Exit animations**](#exit-animations) - Added exit animations to all components.
- [**Other updates**](#other-updates) - New `icon` button size, updated `sheet` component and more.
- [**Updating your project**](#updating-your-project) - How to update your project to get the latest changes.

---

### New CLI

I've been working on a new CLI for the past few weeks. It's a complete rewrite. It comes with a lot of new features and improvements.

### `init`

```bash
npx shadcn-ui@latest init
```

When you run the `init` command, you will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use? › Default
Which color would you like to use as base color? › Slate
Where is your global CSS file? › › app/globals.css
Do you want to use CSS variables for colors? › no / yes
Where is your tailwind.config.js located? › tailwind.config.js
Configure the import alias for components: › @/components
Configure the import alias for utils: › @/lib/utils
Are you using React Server Components? › no / yes
```

This file contains all the information about your components: where to install them, the import paths, how they are styled...etc.

You can use this file to change the import path of a component, set a baseColor or change the styling method.

```json title="components.json"
{
  "style": "default",
  "tailwind": {
    "config": "tailwind.config.ts",
    "css": "src/app/globals.css",
    "baseColor": "zinc",
    "cssVariables": true
  },
  "rsc": false,
  "aliases": {
    "utils": "~/lib/utils",
    "components": "~/components"
  }
}
```

This means you can now use the CLI with any directory structure including `src` and `app` directories.

### `add`

```bash
npx shadcn-ui@latest add
```

The `add` command is now much more capable. You can now add UI components but also import more complex components (coming soon).

The CLI will automatically resolve all components and dependencies, format them based on your custom config and add them to your project.

### `diff` (experimental)

```bash
npx shadcn-ui diff
```

We're also introducing a new `diff` command to help you keep track of upstream updates.

You can use this command to see what has changed in the upstream repository and update your project accordingly.

Run the `diff` command to get a list of components that have updates available:

```bash
npx shadcn-ui diff
```

```txt
The following components have updates available:
- button
  - /path/to/my-app/components/ui/button.tsx
- toast
  - /path/to/my-app/components/ui/use-toast.ts
  - /path/to/my-app/components/ui/toaster.tsx
```

Then run `diff [component]` to see the changes:

```bash
npx shadcn-ui diff alert
```

```diff /pl-12/
const alertVariants = cva(
- "relative w-full rounded-lg border",
+ "relative w-full pl-12 rounded-lg border"
)
```

---

### Theming with CSS Variables or Tailwind Colors

You can choose between using CSS variables or Tailwind CSS utility classes for theming.

When you add new components, the CLI will automatically use the correct theming methods based on your `components.json` configuration.

#### Utility classes

```tsx /bg-zinc-950/ /text-zinc-50/ /dark:bg-white/ /dark:text-zinc-950/
<div className="bg-zinc-950 dark:bg-white" />
```

To use utility classes for theming set `tailwind.cssVariables` to `false` in your `components.json` file.

```json {6} title="components.json"
{
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "slate",
    "cssVariables": false
  }
}
```

#### CSS Variables

```tsx /bg-background/ /text-foreground/
<div className="bg-background text-foreground" />
```

To use CSS variables classes for theming set `tailwind.cssVariables` to `true` in your `components.json` file.

```json {6} title="components.json"
{
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "slate",
    "cssVariables": true
  }
}
```

---

### Base color

You can now configure the base color for your project. This will be used to generate the default color palette for your components.

```json {5} title="components.json"
{
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "zinc",
    "cssVariables": false
  }
}
```

Choose between `gray`, `neutral`, `slate`, `stone` or `zinc`.

If you have `cssVariables` set to `true`, we will set the base colors as CSS variables in your `globals.css` file. If you have `cssVariables` set to `false`, we will inline the Tailwind CSS utility classes in your components.

---

### React Server Components

If you're using a framework that does not support React Server Components, you can now opt out by setting `rsc` to `false`. We will automatically append or remove the `use client` directive when adding components.

```json title="components.json"
{
  "rsc": false
}
```

---

### Styles

We are introducing a new concept called _Style_.

_You can think of style as the visual foundation: shapes, icons, animations & typography._ A style comes with its own set of components, animations, icons and more.

We are shipping two styles: `default` and `new-york` (with more coming soon).

<Image
  src="/images/style.jpg"
  width="716"
  height="402"
  alt="Default vs New York style"
  className="border rounded-lg overflow-hidden mt-6"
/>

The `default` style is the one you are used to. It's the one we've been using since the beginning of this project. It uses `lucide-react` for icons and `tailwindcss-animate` for animations.

The `new-york` style is a new style. It ships with smaller buttons, cards with shadows and a new set of icons from [Radix Icons](https://icons.radix-ui.com).

When you run the `init` command, you will be asked which style you would like to use. This is saved in your `components.json` file.

```json title="components.json"
{
  "style": "new-york"
}
```

### Theming

Start with a style as the base then theme using CSS variables or Tailwind CSS utility classes to completely change the look of your components.

<Image
  src="/images/style-with-theming.jpg"
  width="716"
  height="402"
  alt="Style with theming"
  className="border rounded-lg overflow-hidden mt-6"
/>

---

### Exit animations

I added exit animations to all components. Click on the combobox below to see the subtle exit animation.

<ComponentPreview name="combobox-demo" className="[&_.preview]:items-start" />

The animations can be customized using utility classes.

---

### Other updates

### Button

- Added a new button size `icon`:

<ComponentPreview name="button-icon" />

### Sheet

- Renamed `position` to `side` to match the other elements.

<ComponentPreview name="sheet-side" />

- Removed the `size` props. Use `className="w-[200px] md:w-[450px]"` for responsive sizing.

---

### Updating your project

Since we follow a copy and paste approach, you will need to manually update your project to get the latest changes.

<Callout className="mt-4">
  Note: we are working on a [`diff`](#diff-experimental) command to help you
  keep track of upstream updates.
</Callout>

<Steps>

### Add `components.json`

Creating a `components.json` file at the root:

```json title="components.json"
{
  "style": "default",
  "rsc": true,
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "slate",
    "cssVariables": true
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils"
  }
}
```

Update the values for `tailwind.css` and `aliases` to match your project structure.

### Button

Add the `icon` size to the `buttonVariants`:

```tsx {7} title="components/ui/button.tsx"
const buttonVariants = cva({
  variants: {
    size: {
      default: "h-10 px-4 py-2",
      sm: "h-9 rounded-md px-3",
      lg: "h-11 rounded-md px-8",
      icon: "h-10 w-10",
    },
  },
})
```

### Sheet

1. Replace the content of `sheet.tsx` with the following:

```tsx title="components/ui/sheet.tsx"
"use client"

import * as React from "react"
import * as SheetPrimitive from "@radix-ui/react-dialog"
import { cva, type VariantProps } from "class-variance-authority"
import { X } from "lucide-react"

import { cn } from "@/lib/utils"

const Sheet = SheetPrimitive.Root

const SheetTrigger = SheetPrimitive.Trigger

const SheetClose = SheetPrimitive.Close

const SheetPortal = ({
  className,
  ...props
}: SheetPrimitive.DialogPortalProps) => (
  <SheetPrimitive.Portal className={cn(className)} {...props} />
)
SheetPortal.displayName = SheetPrimitive.Portal.displayName

const SheetOverlay = React.forwardRef<
  React.ElementRef<typeof SheetPrimitive.Overlay>,
  React.ComponentPropsWithoutRef<typeof SheetPrimitive.Overlay>
>(({ className, ...props }, ref) => (
  <SheetPrimitive.Overlay
    className={cn(
      "fixed inset-0 z-50 bg-background/80 backdrop-blur-sm data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0",
      className
    )}
    {...props}
    ref={ref}
  />
))
SheetOverlay.displayName = SheetPrimitive.Overlay.displayName

const sheetVariants = cva(
  "fixed z-50 gap-4 bg-background p-6 shadow-lg transition ease-in-out data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:duration-300 data-[state=open]:duration-500",
  {
    variants: {
      side: {
        top: "inset-x-0 top-0 border-b data-[state=closed]:slide-out-to-top data-[state=open]:slide-in-from-top",
        bottom:
          "inset-x-0 bottom-0 border-t data-[state=closed]:slide-out-to-bottom data-[state=open]:slide-in-from-bottom",
        left: "inset-y-0 left-0 h-full w-3/4 border-r data-[state=closed]:slide-out-to-left data-[state=open]:slide-in-from-left sm:max-w-sm",
        right:
          "inset-y-0 right-0 h-full w-3/4  border-l data-[state=closed]:slide-out-to-right data-[state=open]:slide-in-from-right sm:max-w-sm",
      },
    },
    defaultVariants: {
      side: "right",
    },
  }
)

interface SheetContentProps
  extends React.ComponentPropsWithoutRef<typeof SheetPrimitive.Content>,
    VariantProps<typeof sheetVariants> {}

const SheetContent = React.forwardRef<
  React.ElementRef<typeof SheetPrimitive.Content>,
  SheetContentProps
>(({ side = "right", className, children, ...props }, ref) => (
  <SheetPortal>
    <SheetOverlay />
    <SheetPrimitive.Content
      ref={ref}
      className={cn(sheetVariants({ side }), className)}
      {...props}
    >
      {children}
      <SheetPrimitive.Close className="absolute right-4 top-4 rounded-sm opacity-70 ring-offset-background transition-opacity hover:opacity-100 focus:outline-none focus:ring-2 focus:ring-ring focus:ring-offset-2 disabled:pointer-events-none data-[state=open]:bg-secondary">
        <X className="h-4 w-4" />
        <span className="sr-only">Close</span>
      </SheetPrimitive.Close>
    </SheetPrimitive.Content>
  </SheetPortal>
))
SheetContent.displayName = SheetPrimitive.Content.displayName

const SheetHeader = ({
  className,
  ...props
}: React.HTMLAttributes<HTMLDivElement>) => (
  <div
    className={cn(
      "flex flex-col space-y-2 text-center sm:text-left",
      className
    )}
    {...props}
  />
)
SheetHeader.displayName = "SheetHeader"

const SheetFooter = ({
  className,
  ...props
}: React.HTMLAttributes<HTMLDivElement>) => (
  <div
    className={cn(
      "flex flex-col-reverse sm:flex-row sm:justify-end sm:space-x-2",
      className
    )}
    {...props}
  />
)
SheetFooter.displayName = "SheetFooter"

const SheetTitle = React.forwardRef<
  React.ElementRef<typeof SheetPrimitive.Title>,
  React.ComponentPropsWithoutRef<typeof SheetPrimitive.Title>
>(({ className, ...props }, ref) => (
  <SheetPrimitive.Title
    ref={ref}
    className={cn("text-lg font-semibold text-foreground", className)}
    {...props}
  />
))
SheetTitle.displayName = SheetPrimitive.Title.displayName

const SheetDescription = React.forwardRef<
  React.ElementRef<typeof SheetPrimitive.Description>,
  React.ComponentPropsWithoutRef<typeof SheetPrimitive.Description>
>(({ className, ...props }, ref) => (
  <SheetPrimitive.Description
    ref={ref}
    className={cn("text-sm text-muted-foreground", className)}
    {...props}
  />
))
SheetDescription.displayName = SheetPrimitive.Description.displayName

export {
  Sheet,
  SheetTrigger,
  SheetClose,
  SheetContent,
  SheetHeader,
  SheetFooter,
  SheetTitle,
  SheetDescription,
}
```

2. Rename `position` to `side`

```diff /position/ /side/
- <Sheet position="right" />
+ <Sheet side="right" />
```

</Steps>

### Thank you

I'd like to thank everyone who has been using this project, providing feedback and contributing to it. I really appreciate it. Thank you 🙏

```

### 📄 cli.mdx

```
---
title: CLI
description: Use the CLI to add components to your project.
---

<Callout>

**Note:** We just released a new `shadcn` CLI. See the [changelog](/docs/changelog) for more information.

</Callout>

## init

Use the `init` command to initialize configuration and dependencies for a new project.

The `init` command installs dependencies, adds the `cn` util, configures `tailwind.config.js`, and CSS variables for the project.

```bash
npx shadcn@latest init
```

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use? › New York
Which color would you like to use as base color? › Zinc
Do you want to use CSS variables for colors? › no / yes
```

### Options

```txt
Usage: shadcn init [options] [components...]

initialize your project and install dependencies

Arguments:
  components         the components to add or a url to the component.

Options:
  -d, --defaults    use default values i.e new-york, zinc and css variables. (default: false)
  -f, --force       force overwrite of existing components.json. (default: false)
  -y, --yes         skip confirmation prompt. (default: false)
  -c, --cwd <cwd>   the working directory. defaults to the current directory.
  -h, --help       display help for command
```

## add

Use the `add` command to add components and dependencies to your project.

```bash
npx shadcn@latest add [component]
```

You will be presented with a list of components to choose from:

```txt
Which components would you like to add? › Space to select. A to toggle all.
Enter to submit.

◯  accordion
◯  alert
◯  alert-dialog
◯  aspect-ratio
◯  avatar
◯  badge
◯  button
◯  calendar
◯  card
◯  checkbox
```

### Options

```txt
Usage: shadcn add [options] [components...]

add a component to your project

Arguments:
  components         the components to add or a url to the component.

Options:
  -y, --yes          skip confirmation prompt. (default: false)
  -o, --overwrite    overwrite existing files. (default: false)
  -c, --cwd <cwd>    the working directory. defaults to the current directory.
  -a, --all          add all available components. (default: false)
  -p, --path <path>  the path to add the component to.
  -h, --help         display help for command
```

## Monorepo

In a monorepo, you can specify the path to your workspace with the `-c` or `--cwd` option.

```bash
npx shadcn@latest init -c ./apps/www
```

or

```bash
npx shadcn@latest add alert-dialog -c ./apps/www
```

```

### 📄 components-json.mdx

```
---
title: components.json
description: Configuration for your project.
---

The `components.json` file holds configuration for your project.

We use it to understand how your project is set up and how to generate components customized for your project.

<Callout className="mt-6">
  Note: The `components.json` file is optional and **only required if you're
  using the CLI** to add components to your project. If you're using the copy
  and paste method, you don't need this file.
</Callout>

You can create a `components.json` file in your project by running the following command:

```bash
npx shadcn@latest init
```

See the <Link href="/docs/cli">CLI section</Link> for more information.

## $schema

You can see the JSON Schema for `components.json` [here](https://ui.shadcn.com/schema.json).

```json title="components.json"
{
  "$schema": "https://ui.shadcn.com/schema.json"
}
```

## style

The style for your components. **This cannot be changed after initialization.**

```json title="components.json"
{
  "style": "default" | "new-york"
}
```

<ComponentPreview name="card-with-form" />

## tailwind

Configuration to help the CLI understand how Tailwind CSS is set up in your project.

See the <Link href="/docs/installation">installation section</Link> for how to set up Tailwind CSS.

### tailwind.config

Path to where your `tailwind.config.js` file is located.

```json title="components.json"
{
  "tailwind": {
    "config": "tailwind.config.js" | "tailwind.config.ts"
  }
}
```

### tailwind.css

Path to the CSS file that imports Tailwind CSS into your project.

```json title="components.json"
{
  "tailwind": {
    "css": "styles/global.css"
  }
}
```

### tailwind.baseColor

This is used to generate the default color palette for your components. **This cannot be changed after initialization.**

```json title="components.json"
{
  "tailwind": {
    "baseColor": "gray" | "neutral" | "slate" | "stone" | "zinc"
  }
}
```

### tailwind.cssVariables

You can choose between using CSS variables or Tailwind CSS utility classes for theming.

To use utility classes for theming set `tailwind.cssVariables` to `false`. For CSS variables, set `tailwind.cssVariables` to `true`.

```json title="components.json"
{
  "tailwind": {
    "cssVariables": `true` | `false`
  }
}
```

For more information, see the <Link href="/docs/theming">theming docs</Link>.

**This cannot be changed after initialization.** To switch between CSS variables and utility classes, you'll have to delete and re-install your components.

### tailwind.prefix

The prefix to use for your Tailwind CSS utility classes. Components will be added with this prefix.

```json title="components.json"
{
  "tailwind": {
    "prefix": "tw-"
  }
}
```

## rsc

Whether or not to enable support for React Server Components.

The CLI automatically adds a `use client` directive to client components when set to `true`.

```json title="components.json"
{
  "rsc": `true` | `false`
}
```

## tsx

Choose between TypeScript or JavaScript components.

Setting this option to `false` allows components to be added as JavaScript with the `.jsx` file extension.

```json title="components.json"
{
  "tsx": `true` | `false`
}
```

## aliases

The CLI uses these values and the `paths` config from your `tsconfig.json` or `jsconfig.json` file to place generated components in the correct location.

Path aliases have to be set up in your `tsconfig.json` or `jsconfig.json` file.

<Callout className="mt-6">
  **Important:** If you're using the `src` directory, make sure it is included
  under `paths` in your `tsconfig.json` or `jsconfig.json` file.
</Callout>

### aliases.utils

Import alias for your utility functions.

```json title="components.json"
{
  "aliases": {
    "utils": "@/lib/utils"
  }
}
```

### aliases.components

Import alias for your components.

```json title="components.json"
{
  "aliases": {
    "components": "@/components"
  }
}
```

### aliases.ui

Import alias for `ui` components.

The CLI will use the `aliases.ui` value to determine where to place your `ui` components. Use this config if you want to customize the installation directory for your `ui` components.

```json title="components.json"
{
  "aliases": {
    "ui": "@/app/ui"
  }
}
```

### aliases.lib

Import alias for `lib` functions such as `format-date` or `generate-id`.

```json title="components.json"
{
  "aliases": {
    "lib": "@/lib"
  }
}
```

### aliases.hooks

Import alias for `hooks` such as `use-media-query` or `use-toast`.

```json title="components.json"
{
  "aliases": {
    "hooks": "@/hooks"
  }
}
```

```

### 📄 figma.mdx

```
---
title: Figma
description: Every component recreated in Figma. With customizable props, typography and icons.
---

## Paid

- [shadcn/ui kit](https://shadcndesign.com) by [ Matt Wierzbicki](https://x.com/matsugfx) - A premium, always up-to-date UI kit for Figma - shadcn/ui compatible and optimized for smooth design-to-dev handoff.

## Free

- [shadcn/ui design system](https://www.figma.com/community/file/1203061493325953101) by [Pietro Schirano](https://twitter.com/skirano) - A design companion for shadcn/ui. Each component was painstakingly crafted to perfectly match the code implementation.

```

### 📄 index.mdx

```
---
title: Introduction
description: Beautifully designed components that you can copy and paste into your apps. Accessible. Customizable. Open Source.
---

This is **NOT** a component library. It's a collection of re-usable components that you can copy and paste into your apps.

**What do you mean by not a component library?**

I mean you do not install it as a dependency. It is not available or distributed via npm.

Pick the components you need. Copy and paste the code into your project and customize to your needs. The code is yours.

_Use this as a reference to build your own component libraries._

## FAQ

<Accordion type="multiple">

<AccordionItem value="faq-1">
  <AccordionTrigger>
    Why copy/paste and not packaged as a dependency?
  </AccordionTrigger>
  <AccordionContent>
The idea behind this is to give you ownership and control over the code, allowing you to decide how the components are built and styled.

Start with some sensible defaults, then customize the components to your needs.

One of the drawbacks of packaging the components in an npm package is that the style is coupled with the implementation. _The design of your components should be separate from their implementation._

</AccordionContent>
</AccordionItem>

<AccordionItem value="faq-2">
  <AccordionTrigger>
    Do you plan to publish it as an npm package?
  </AccordionTrigger>
  <AccordionContent>
    No. I have no plans to publish it as an npm package.
  </AccordionContent>
</AccordionItem>

<AccordionItem value="faq-3">
<AccordionTrigger>
Which frameworks are supported?
</AccordionTrigger>
<AccordionContent>

You can use any framework that supports React. [Next.js](https://ui.shadcn.com/docs/installation/next), [Astro](https://ui.shadcn.com/docs/installation/astro), [Remix](https://ui.shadcn.com/docs/installation/remix), [Gatsby](https://ui.shadcn.com/docs/installation/gatsby) etc.

</AccordionContent>
</AccordionItem>

<AccordionItem value="faq-4">
  <AccordionTrigger>
  Can I use this in my project?
  </AccordionTrigger>
  <AccordionContent>
Yes. Free to use for personal and commercial projects. No attribution required.

But hey, let me know if you do. I'd love to see what you build.

    </AccordionContent>

</AccordionItem>

</Accordion>

```

### 📄 monorepo.mdx

```
---
title: Monorepo
description: Using shadcn/ui components and CLI in a monorepo.
---

<Callout>
  **Note:** We're releasing monorepo support in the CLI as __experimental__.
  Help us improve it by testing it out and sending feedback. If you have any
  questions, please [reach out to
  us](https://github.com/shadcn-ui/ui/discussions).
</Callout>

Until now, using shadcn/ui in a monorepo was a bit of a pain. You could add
components using the CLI, but you had to manage where the components
were installed and manually fix import paths.

With the new monorepo support in the CLI, we've made it a lot easier to use
shadcn/ui in a monorepo.

The CLI now understands the monorepo structure and will install the components,
dependencies and registry dependencies to the correct paths and handle imports
for you.

## Getting started

<Steps>

### Create a new monorepo project

To create a new monorepo project, run the `init` command. You will be prompted
to select the type of project you are creating.

```bash
npx shadcn@canary init
```

Select the `Next.js (Monorepo)` option.

```bash
? Would you like to start a new project?
    Next.js
❯   Next.js (Monorepo)
```

This will create a new monorepo project with two workspaces: `web` and `ui`,
and [Turborepo](https://turbo.build/repo/docs) as the build system.

Everything is set up for you, so you can start adding components to your project.

### Add components to your project

To add components to your project, run the `add` command **in the path of your app**.

```bash
cd apps/web
```

```bash
npx shadcn@canary add [COMPONENT]
```

The CLI will figure out what type of component you are adding and install the
correct files to the correct path.

For example, if you run `npx shadcn@canary add button`, the CLI will install the button component under `packages/ui` and update the import path for components in `apps/web`.

If you run `npx shadcn@canary add login-01`, the CLI will install the `button`, `label`, `input` and `card` components under `packages/ui` and the `login-form` component under `apps/web/components`.

### Importing components

You can import components from the `@workspace/ui` package as follows:

```tsx
import { Button } from "@workspace/ui/components/button"
```

You can also import hooks and utilities from the `@workspace/ui` package.

```tsx
import { useTheme } from "@workspace/ui/hooks/use-theme"
import { cn } from "@workspace/ui/lib/utils"
```

</Steps>

## File Structure

When you create a new monorepo project, the CLI will create the following file structure:

```txt
apps
└── web         # Your app goes here.
    ├── app
    │   └── page.tsx
    ├── components
    │   └── login-form.tsx
    ├── components.json
    └── package.json
packages
└── ui          # Your components and dependencies are installed here.
    ├── src
    │   ├── components
    │   │   └── button.tsx
    │   ├── hooks
    │   ├── lib
    │   │   └── utils.ts
    │   └── styles
    │       └── globals.css
    ├── components.json
    └── package.json
package.json
turbo.json
```

## Requirements

1. Every workspace must have a `components.json` file. A `package.json` file tells npm how to install the dependencies. A `components.json` file tells the CLI how and where to install components.

2. The `components.json` file must properly define aliases for the workspace. This tells the CLI how to import components, hooks, utilities, etc.

```json title="apps/web/components.json"
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": true,
  "tsx": true,
  "tailwind": {
    "config": "../../packages/ui/tailwind.config.ts",
    "css": "../../packages/ui/src/styles/globals.css",
    "baseColor": "zinc",
    "cssVariables": true
  },
  "iconLibrary": "lucide",
  "aliases": {
    "components": "@/components",
    "hooks": "@/hooks",
    "lib": "@/lib",
    "utils": "@workspace/ui/lib/utils",
    "ui": "@workspace/ui/components"
  }
}
```

```json title="packages/ui/components.json"
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": true,
  "tsx": true,
  "tailwind": {
    "config": "tailwind.config.ts",
    "css": "src/styles/globals.css",
    "baseColor": "zinc",
    "cssVariables": true
  },
  "iconLibrary": "lucide",
  "aliases": {
    "components": "@workspace/ui/components",
    "utils": "@workspace/ui/lib/utils",
    "hooks": "@workspace/ui/hooks",
    "lib": "@workspace/ui/lib",
    "ui": "@workspace/ui/components"
  }
}
```

3. Ensure you have the same `style`, `iconLibrary` and `baseColor` in both `components.json` files.

By following these requirements, the CLI will be able to install ui components, blocks, libs and hooks to the correct paths and handle imports for you.

## Help us improve monorepo support

We're releasing monorepo support in the CLI as **experimental**. Help us improve it by testing it out and sending feedback.

If you have any questions, please reach out to us on [GitHub Discussions](https://github.com/shadcn-ui/ui/discussions).

```

### 📄 react-19.mdx

```
---
title: Next.js 15 + React 19
description: Using shadcn/ui with Next.js 15 and React 19.
---

<Callout>
  **The following guide applies to any framework that supports React 19**. I
  titled this page "Next.js 15 + React 19" to help people upgrading to Next.js
  15 find it. We are working with package maintainers to help upgrade to React
  19.
</Callout>

## TL;DR

If you're using `npm`, you can install shadcn/ui dependencies with a flag. The `shadcn` CLI will prompt you to select a flag when you run it. No flags required for pnpm, bun, or yarn.

See [Upgrade Status](#upgrade-status) for the status of React 19 support for each package.

## What's happening?

React 19 is now [rc](https://www.npmjs.com/package/react?activeTab=versions) and is [tested and supported in the latest Next.js 15 release](https://nextjs.org/blog/next-15#react-19).

To support React 19, package maintainers will need to test and update their packages to include React 19 as a peer dependency. This is [already](https://github.com/radix-ui/primitives/pull/2952) [in](https://github.com/pacocoursey/cmdk/pull/318) [progress](https://github.com/emilkowalski/vaul/pull/498).

```diff /^19.0/
"peerDependencies": {
-  "react": "^16.8 || ^17.0 || ^18.0",
+  "react": "^16.8 || ^17.0 || ^18.0 || ^19.0",
-  "react-dom": "^16.8 || ^17.0 || ^18.0"
+  "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0"
},
```

<Callout>
  You can check if a package lists React 19 as a peer dependency by running
  `npm info <package> peerDependencies`.
</Callout>

In the meantime, if you are installing a package that **does not** list React 19 as a peer dependency, you will see an error message like this:

```bash
npm error code ERESOLVE
npm error ERESOLVE unable to resolve dependency tree
npm error
npm error While resolving: my-app@0.1.0
npm error Found: react@19.0.0-rc-69d4b800-20241021
npm error node_modules/react
npm error   react@"19.0.0-rc-69d4b800-20241021" from the root project
```

<Callout>
  **Note:** This is npm only. PNPM and Bun will only show a silent warning.
</Callout>

## How to fix this

### Solution 1: `--force` or `--legacy-peer-deps`

You can force install a package with the `--force` or the `--legacy-peer-deps` flag.

```bash
npm i <package> --force

npm i <package> --legacy-peer-deps
```

This will install the package and ignore the peer dependency warnings.

<Accordion type="multiple">
  <AccordionItem value="flags">
    <AccordionTrigger className="font-medium">
      What do the `--force` and `--legacy-peer-deps` flag do?
    </AccordionTrigger>
    <AccordionContent className="[&_ul]:mt-0">

      - `--force`: Ignores and overrides any dependency conflicts, forcing the
        installation of packages.
      - `--legacy-peer-deps`: Skips strict peer dependency checks, allowing
        installation of packages with unmet peer dependencies to avoid errors.

    </AccordionContent>

  </AccordionItem>
</Accordion>

### Solution 2: Use React 18

You can downgrade `react` and `react-dom` to version 18, which is compatible with the package you are installing and upgrade when the dependency is updated.

```bash
npm i react@18 react-dom@18
```

Whichever solution you choose, make sure you test your app thoroughly to ensure
there are no regressions.

## Using shadcn/ui on Next.js 15

### Using pnpm, bun, or yarn

Follow the instructions in the [installation guide](/docs/installation/next) to install shadcn/ui. No flags are needed.

### Using npm

When you run `npx shadcn@latest init -d`, you will be prompted to select an option to resolve the peer dependency issues.

```bash
It looks like you are using React 19.
Some packages may fail to install due to peer dependency issues (see https://ui.shadcn.com/react-19).

? How would you like to proceed? › - Use arrow-keys. Return to submit.
❯   Use --force
    Use --legacy-peer-deps
```

You can then run the command with the flag you choose.

## Adding components

The process for adding components is the same as above. Select a flag to resolve the peer dependency issues.

**Remember to always test your app after installing new dependencies.**

## Upgrade Status

To make it easy for you track the progress of the upgrade, I've created a table below with React 19 support status for the shadcn/ui dependencies.

- ✅ - Works with React 19 using npm, pnpm, and bun.
- 🚧 - Works with React 19 using pnpm and bun. Requires flag for npm. PR is in progress.

| Package                                                                            | Status | Note                                                        |
| ---------------------------------------------------------------------------------- | ------ | ----------------------------------------------------------- |
| [radix-ui](https://www.npmjs.com/package/@radix-ui/react-icons)                    | ✅     |                                                             |
| [lucide-react](https://www.npmjs.com/package/lucide-react)                         | ✅     |                                                             |
| [class-variance-authority](https://www.npmjs.com/package/class-variance-authority) | ✅     | Does not list React 19 as a peer dependency.                |
| [tailwindcss-animate](https://www.npmjs.com/package/tailwindcss-animate)           | ✅     | Does not list React 19 as a peer dependency.                |
| [embla-carousel-react](https://www.npmjs.com/package/embla-carousel-react)         | ✅     |                                                             |
| [recharts](https://www.npmjs.com/package/recharts)                                 | ✅     | See note [below](#recharts)                                 |
| [react-hook-form](https://www.npmjs.com/package/react-hook-form)                   | ✅     |                                                             |
| [react-resizable-panels](https://www.npmjs.com/package/react-resizable-panels)     | ✅     |                                                             |
| [sonner](https://www.npmjs.com/package/sonner)                                     | ✅     |                                                             |
| [react-day-picker](https://www.npmjs.com/package/react-day-picker)                 | ✅     | Works with flag for npm. Work to upgrade to v9 in progress. |
| [input-otp](https://www.npmjs.com/package/input-otp)                               | ✅     |                                                             |
| [vaul](https://www.npmjs.com/package/vaul)                                         | ✅     |                                                             |
| [@radix-ui/react-icons](https://www.npmjs.com/package/@radix-ui/react-icons)       | 🚧     | See [PR #194](https://github.com/radix-ui/icons/pull/194)   |
| [cmdk](https://www.npmjs.com/package/cmdk)                                         | ✅     |                                                             |

If you have any questions, please [open an issue](https://github.com/shadcn/ui/issues) on GitHub.

## Recharts

To use recharts with React 19, you will need to override the `react-is` dependency.

<Steps>

<Step>Add the following to your `package.json`</Step>

```json title="package.json"
"overrides": {
  "react-is": "^19.0.0-rc-69d4b800-20241021"
}
```

Note: the `react-is` version needs to match the version of React 19 you are using. The above is an example.

<Step>Run `npm install --legacy-peer-deps`</Step>

</Steps>

```

### 📄 theming.mdx

```
---
title: Theming
description: Using CSS Variables or Tailwind CSS for theming.
---

You can choose between using CSS variables or Tailwind CSS utility classes for theming.

## Utility classes

```tsx /bg-zinc-950/ /text-zinc-50/ /dark:bg-white/ /dark:text-zinc-950/
<div className="bg-zinc-950 dark:bg-white" />
```

To use utility classes for theming set `tailwind.cssVariables` to `false` in your `components.json` file.

```json {8} title="components.json"
{
  "style": "default",
  "rsc": true,
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "slate",
    "cssVariables": false
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils"
  }
}
```

## CSS Variables

```tsx /bg-background/ /text-foreground/
<div className="bg-background text-foreground" />
```

To use CSS variables for theming set `tailwind.cssVariables` to `true` in your `components.json` file.

```json {8} title="components.json"
{
  "style": "default",
  "rsc": true,
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "app/globals.css",
    "baseColor": "slate",
    "cssVariables": true
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils"
  }
}
```

### Convention

We use a simple `background` and `foreground` convention for colors. The `background` variable is used for the background color of the component and the `foreground` variable is used for the text color.

<Callout className="mt-4">

The `background` suffix is omitted when the variable is used for the background color of the component.

</Callout>

Given the following CSS variables:

```css
--primary: 222.2 47.4% 11.2%;
--primary-foreground: 210 40% 98%;
```

The `background` color of the following component will be `hsl(var(--primary))` and the `foreground` color will be `hsl(var(--primary-foreground))`.

```tsx
<div className="bg-primary text-primary-foreground">Hello</div>
```

<Callout>

**CSS variables must be defined without color space function**. See the [Tailwind CSS documentation](https://tailwindcss.com/docs/customizing-colors#using-css-variables) for more information.

</Callout>

### List of variables

Here's the list of variables available for customization:

<Steps>

```css title="Default background color of <body />...etc"
--background: 0 0% 100%;
--foreground: 222.2 47.4% 11.2%;
```

```css title="Muted backgrounds such as <TabsList />, <Skeleton /> and <Switch />"
--muted: 210 40% 96.1%;
--muted-foreground: 215.4 16.3% 46.9%;
```

```css title="Background color for <Card />"
--card: 0 0% 100%;
--card-foreground: 222.2 47.4% 11.2%;
```

```css title="Background color for popovers such as <DropdownMenu />, <HoverCard />, <Popover />"
--popover: 0 0% 100%;
--popover-foreground: 222.2 47.4% 11.2%;
```

```css title="Default border color"
--border: 214.3 31.8% 91.4%;
```

```css title="Border color for inputs such as <Input />, <Select />, <Textarea />"
--input: 214.3 31.8% 91.4%;
```

```css title="Primary colors for <Button />"
--primary: 222.2 47.4% 11.2%;
--primary-foreground: 210 40% 98%;
```

```css title="Secondary colors for <Button />"
--secondary: 210 40% 96.1%;
--secondary-foreground: 222.2 47.4% 11.2%;
```

```css title="Used for accents such as hover effects on <DropdownMenuItem>, <SelectItem>...etc"
--accent: 210 40% 96.1%;
--accent-foreground: 222.2 47.4% 11.2%;
```

```css title="Used for destructive actions such as <Button variant="destructive">"
--destructive: 0 100% 50%;
--destructive-foreground: 210 40% 98%;
```

```css title="Used for focus ring"
--ring: 215 20.2% 65.1%;
```

```css title="Border radius for card, input and buttons"
--radius: 0.5rem;
```

</Steps>

### Adding new colors

To add new colors, you need to add them to your CSS file and to your `tailwind.config.js` file.

```css title="app/globals.css"
:root {
  --warning: 38 92% 50%;
  --warning-foreground: 48 96% 89%;
}

.dark {
  --warning: 48 96% 89%;
  --warning-foreground: 38 92% 50%;
}
```

```js {5-6} title="tailwind.config.js"
module.exports = {
  theme: {
    extend: {
      colors: {
        warning: "hsl(var(--warning))",
        "warning-foreground": "hsl(var(--warning-foreground))",
      },
    },
  },
}
```

You can now use the `warning` utility class in your components.

```tsx /bg-warning/ /text-warning-foreground/
<div className="bg-warning text-warning-foreground" />
```

### Other color formats

I recommend using [HSL colors](https://www.smashingmagazine.com/2021/07/hsl-colors-css/) for theming but you can also use other color formats if you prefer.

See the [Tailwind CSS documentation](https://tailwindcss.com/docs/customizing-colors#using-css-variables) for more information on using `rgb`, `rgba` or `hsl` colors.

```

### 📄 v0.mdx

```
---
title: Open in v0
description: Open components in v0 for customization.
---

Every component on ui.shadcn.com is editable on [v0 by Vercel](https://v0.dev). This allows you to easily customize the components in natural language and paste into your app.

<a href="https://vercel.com/signup?utm_source=shad&utm_medium=web&utm_campaign=docs_cta_signup">
  <Image
    src="/images/open-in-v0.png"
    width="716"
    height="420"
    alt="Open in v0"
    className="border dark:hidden shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <Image
    src="/images/open-in-v0-dark.png"
    width="716"
    height="420"
    alt="Open in v0"
    className="border hidden dark:block shadow-sm rounded-lg overflow-hidden mt-6 w-full"
  />
  <span class="sr-only">Open in v0</span>
</a>

To use v0, sign-up for a free [Vercel account here](https://vercel.com/signup?utm_source=shad&utm_medium=web&utm_campaign=docs_cta_signup). In addition to v0, this gives you free access to Vercel's frontend cloud platform by the creators of Next.js, where you can deploy and host your project for free.

Learn more about getting started with [Vercel here](https://vercel.com/docs/getting-started-with-vercel?utm_source=shadcn_site&utm_medium=web&utm_campaign=docs_cta_about_vercel).

Learn more about getting started with [v0 here](https://v0.dev/faq).

```

### 📄 components/accordion.mdx

```
---
title: Accordion
description: A vertically stacked set of interactive headings that each reveal a section of content.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/accordion
  api: https://www.radix-ui.com/docs/primitives/components/accordion#api-reference
---

<ComponentPreview
  name="accordion-demo"
  className="[&_.preview>[data-orientation=vertical]]:sm:max-w-[70%]"
  description="An accordion with three items"
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>

<TabsContent value="cli">

```bash
npx shadcn@latest add accordion
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-accordion
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="accordion" />

<Step>Update the import paths to match your project setup.</Step>

<Step>Update `tailwind.config.js`</Step>

Add the following animations to your `tailwind.config.js` file:

```js title="tailwind.config.js" {5-18}
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      keyframes: {
        "accordion-down": {
          from: { height: "0" },
          to: { height: "var(--radix-accordion-content-height)" },
        },
        "accordion-up": {
          from: { height: "var(--radix-accordion-content-height)" },
          to: { height: "0" },
        },
      },
      animation: {
        "accordion-down": "accordion-down 0.2s ease-out",
        "accordion-up": "accordion-up 0.2s ease-out",
      },
    },
  },
}
```

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion"
```

```tsx
<Accordion type="single" collapsible>
  <AccordionItem value="item-1">
    <AccordionTrigger>Is it accessible?</AccordionTrigger>
    <AccordionContent>
      Yes. It adheres to the WAI-ARIA design pattern.
    </AccordionContent>
  </AccordionItem>
</Accordion>
```

```

### 📄 components/alert-dialog.mdx

```
---
title: Alert Dialog
description: A modal dialog that interrupts the user with important content and expects a response.
featured: true
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/alert-dialog
  api: https://www.radix-ui.com/docs/primitives/components/alert-dialog#api-reference
---

<ComponentPreview
  name="alert-dialog-demo"
  title="An alert dialog with cancel and continue buttons."
  description="An alert dialog with cancel and continue buttons."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add alert-dialog
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-alert-dialog
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="alert-dialog" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  AlertDialog,
  AlertDialogAction,
  AlertDialogCancel,
  AlertDialogContent,
  AlertDialogDescription,
  AlertDialogFooter,
  AlertDialogHeader,
  AlertDialogTitle,
  AlertDialogTrigger,
} from "@/components/ui/alert-dialog"
```

```tsx
<AlertDialog>
  <AlertDialogTrigger>Open</AlertDialogTrigger>
  <AlertDialogContent>
    <AlertDialogHeader>
      <AlertDialogTitle>Are you absolutely sure?</AlertDialogTitle>
      <AlertDialogDescription>
        This action cannot be undone. This will permanently delete your account
        and remove your data from our servers.
      </AlertDialogDescription>
    </AlertDialogHeader>
    <AlertDialogFooter>
      <AlertDialogCancel>Cancel</AlertDialogCancel>
      <AlertDialogAction>Continue</AlertDialogAction>
    </AlertDialogFooter>
  </AlertDialogContent>
</AlertDialog>
```

```

### 📄 components/alert.mdx

```
---
title: Alert
description: Displays a callout for user attention.
component: true
---

<ComponentPreview
  name="alert-demo"
  title="An alert with an icon, title and description."
  description="An alert with an icon, title and description. The title says 'Heads up!' and the description is 'You can add components to your app using the cli.'."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add alert
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="alert" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert"
```

```tsx
<Alert>
  <Terminal className="h-4 w-4" />
  <AlertTitle>Heads up!</AlertTitle>
  <AlertDescription>
    You can add components and dependencies to your app using the cli.
  </AlertDescription>
</Alert>
```

## Examples

### Default

<ComponentPreview
  name="alert-demo"
  title="An alert with an icon, title and description."
  description="An alert with an icon, title and description. The title says 'Heads up!' and the description is 'You can add components to your app using the cli.'."
/>

### Destructive

<ComponentPreview
  name="alert-destructive"
  title="An alert with a destructive variant."
  description="An alert with a destructive variant. The title says 'Delete this item?' and the description is 'This action cannot be undone.'."
/>

```

### 📄 components/aspect-ratio.mdx

```
---
title: Aspect Ratio
description: Displays content within a desired ratio.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/aspect-ratio
  api: https://www.radix-ui.com/docs/primitives/components/aspect-ratio#api-reference
---

<ComponentPreview
  name="aspect-ratio-demo"
  title="Aspect Ratio"
  description="A component that displays an image with a 16:9 aspect ratio."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add aspect-ratio
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-aspect-ratio
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="aspect-ratio" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import Image from "next/image"

import { AspectRatio } from "@/components/ui/aspect-ratio"
```

```tsx
<div className="w-[450px]">
  <AspectRatio ratio={16 / 9}>
    <Image src="..." alt="Image" className="rounded-md object-cover" />
  </AspectRatio>
</div>
```

```

### 📄 components/avatar.mdx

```
---
title: Avatar
description: An image element with a fallback for representing the user.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/avatar
  api: https://www.radix-ui.com/docs/primitives/components/avatar#api-reference
---

<ComponentPreview
  name="avatar-demo"
  title="Avatar"
  description="An avatar with a fallback."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add avatar
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-avatar
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="avatar" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar"
```

```tsx
<Avatar>
  <AvatarImage src="https://github.com/shadcn.png" />
  <AvatarFallback>CN</AvatarFallback>
</Avatar>
```

```

### 📄 components/badge.mdx

```
---
title: Badge
description: Displays a badge or a component that looks like a badge.
component: true
---

<ComponentPreview
  name="badge-demo"
  title="Badge"
  description="A default badge"
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add badge
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="badge" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Badge } from "@/components/ui/badge"
```

```tsx
<Badge variant="outline">Badge</Badge>
```

### Link

You can use the `badgeVariants` helper to create a link that looks like a badge.

```tsx
import { badgeVariants } from "@/components/ui/badge"
```

```tsx
<Link className={badgeVariants({ variant: "outline" })}>Badge</Link>
```

## Examples

### Default

<ComponentPreview
  name="badge-demo"
  title="Badge"
  description="A default badge"
/>

---

### Secondary

<ComponentPreview
  name="badge-secondary"
  title="Badge"
  description="A badge using secondary as variant."
/>

---

### Outline

<ComponentPreview
  name="badge-outline"
  title="Badge"
  description="A badge using outline as variant."
/>

---

### Destructive

<ComponentPreview name="badge-destructive" description="A destructive badge." />

```

### 📄 components/breadcrumb.mdx

```
---
title: Breadcrumb
description: Displays the path to the current resource using a hierarchy of links.
component: true
---

<ComponentPreview
  name="breadcrumb-demo"
  className="[&_.preview]:p-2"
  description="A breadcrumb with a collapsible dropdown."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add breadcrumb
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="breadcrumb" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Breadcrumb,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbList,
  BreadcrumbPage,
  BreadcrumbSeparator,
} from "@/components/ui/breadcrumb"
```

```tsx
<Breadcrumb>
  <BreadcrumbList>
    <BreadcrumbItem>
      <BreadcrumbLink href="/">Home</BreadcrumbLink>
    </BreadcrumbItem>
    <BreadcrumbSeparator />
    <BreadcrumbItem>
      <BreadcrumbLink href="/components">Components</BreadcrumbLink>
    </BreadcrumbItem>
    <BreadcrumbSeparator />
    <BreadcrumbItem>
      <BreadcrumbPage>Breadcrumb</BreadcrumbPage>
    </BreadcrumbItem>
  </BreadcrumbList>
</Breadcrumb>
```

## Examples

### Custom separator

Use a custom component as `children` for `<BreadcrumbSeparator />` to create a custom separator.

<ComponentPreview
  name="breadcrumb-separator"
  description="A breadcrumb with a custom separator"
/>

```tsx showLineNumbers {1,10-12}
import { Slash } from "lucide-react"

...

<Breadcrumb>
  <BreadcrumbList>
    <BreadcrumbItem>
      <BreadcrumbLink href="/">Home</BreadcrumbLink>
    </BreadcrumbItem>
    <BreadcrumbSeparator>
      <Slash />
    </BreadcrumbSeparator>
    <BreadcrumbItem>
      <BreadcrumbLink href="/components">Components</BreadcrumbLink>
    </BreadcrumbItem>
  </BreadcrumbList>
</Breadcrumb>
```

---

### Dropdown

You can compose `<BreadcrumbItem />` with a `<DropdownMenu />` to create a dropdown in the breadcrumb.

<ComponentPreview
  name="breadcrumb-dropdown"
  className="[&_.preview]:p-2"
  description="A breadcrumb with a dropdown."
/>

```tsx showLineNumbers {1-6,11-21}
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"

...

<BreadcrumbItem>
  <DropdownMenu>
    <DropdownMenuTrigger className="flex items-center gap-1">
      Components
      <ChevronDownIcon />
    </DropdownMenuTrigger>
    <DropdownMenuContent align="start">
      <DropdownMenuItem>Documentation</DropdownMenuItem>
      <DropdownMenuItem>Themes</DropdownMenuItem>
      <DropdownMenuItem>GitHub</DropdownMenuItem>
    </DropdownMenuContent>
  </DropdownMenu>
</BreadcrumbItem>
```

---

### Collapsed

We provide a `<BreadcrumbEllipsis />` component to show a collapsed state when the breadcrumb is too long.

<ComponentPreview
  name="breadcrumb-ellipsis"
  className="[&_.preview]:p-2"
  description="A breadcrumb showing a collapsed state."
/>

```tsx showLineNumbers {1,9}
import { BreadcrumbEllipsis } from "@/components/ui/breadcrumb"

...

<Breadcrumb>
  <BreadcrumbList>
    {/* ... */}
    <BreadcrumbItem>
      <BreadcrumbEllipsis />
    </BreadcrumbItem>
    {/* ... */}
  </BreadcrumbList>
</Breadcrumb>
```

---

### Link component

To use a custom link component from your routing library, you can use the `asChild` prop on `<BreadcrumbLink />`.

<ComponentPreview
  name="breadcrumb-link"
  description="A breadcrumb with a custom Link component"
/>

```tsx showLineNumbers {1,8-10}
import { Link } from "next/link"

...

<Breadcrumb>
  <BreadcrumbList>
    <BreadcrumbItem>
      <BreadcrumbLink asChild>
        <Link href="/">Home</Link>
      </BreadcrumbLink>
    </BreadcrumbItem>
    {/* ... */}
  </BreadcrumbList>
</Breadcrumb>
```

---

### Responsive

Here's an example of a responsive breadcrumb that composes `<BreadcrumbItem />` with `<BreadcrumbEllipsis />`, `<DropdownMenu />`, and `<Drawer />`.

It displays a dropdown on desktop and a drawer on mobile.

<ComponentPreview
  name="breadcrumb-responsive"
  className="[&_.preview]:p-2"
  description="A responsive breadcrumb. It displays a dropdown on desktop and a drawer on mobile."
/>

```

### 📄 components/button.mdx

```
---
title: Button
description: Displays a button or a component that looks like a button.
featured: true
component: true
---

<ComponentPreview name="button-demo" description="A button" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add button
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-slot
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="button" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Button } from "@/components/ui/button"
```

```tsx
<Button variant="outline">Button</Button>
```

## Link

You can use the `buttonVariants` helper to create a link that looks like a button.

```tsx
import { buttonVariants } from "@/components/ui/button"
```

```tsx
<Link className={buttonVariants({ variant: "outline" })}>Click here</Link>
```

Alternatively, you can set the `asChild` parameter and nest the link component.

```tsx
<Button asChild>
  <Link href="/login">Login</Link>
</Button>
```

## Examples

### Primary

<ComponentPreview name="button-demo" description="A primary button" />

### Secondary

<ComponentPreview name="button-secondary" description="A secondary button" />

### Destructive

<ComponentPreview
  name="button-destructive"
  description="A destructive button"
/>

### Outline

<ComponentPreview
  name="button-outline"
  description="A button using the outline variant."
/>

### Ghost

<ComponentPreview
  name="button-ghost"
  description="A button using the ghost variant"
/>

### Link

<ComponentPreview
  name="button-link"
  description="A button using the link variant."
/>

### Icon

<ComponentPreview name="button-icon" description="An icon button" />

### With Icon

<ComponentPreview name="button-with-icon" description="A button with an icon" />

### Loading

<ComponentPreview
  name="button-loading"
  description="A button with a loading state."
/>

### As Child

<ComponentPreview
  name="button-as-child"
  description="A button wrapping a custom Link component"
/>

## Changelog

### 2024-10-16 Classes for icons

Added `gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0` to the button to automatically style icon inside the button.

Add the following classes to the `cva` call in your `button.tsx` file.

```diff showLineNumbers title="button.tsx"
const buttonVariants = cva(
  "inline-flex ... gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0"
)
```

```

### 📄 components/calendar.mdx

```
---
title: Calendar
description: A date field component that allows users to enter and edit date.
component: true
links:
  doc: https://react-day-picker.js.org
---

<ComponentPreview
  name="calendar-demo"
  title="Calendar"
  description="A calendar showing the current date."
/>

## About

The `Calendar` component is built on top of [React DayPicker](https://react-day-picker.js.org).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add calendar
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install react-day-picker date-fns
```

<Step>Add the `Button` component to your project.</Step>

The `Calendar` component uses the `Button` component. Make sure you have it installed in your project.

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="calendar" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Calendar } from "@/components/ui/calendar"
```

```tsx
const [date, setDate] = React.useState<Date | undefined>(new Date())

return (
  <Calendar
    mode="single"
    selected={date}
    onSelect={setDate}
    className="rounded-md border"
  />
)
```

See the [React DayPicker](https://react-day-picker.js.org) documentation for more information.

## Date Picker

You can use the `<Calendar>` component to build a date picker. See the [Date Picker](/docs/components/date-picker) page for more information.

## Examples

### Form

<ComponentPreview name="calendar-form" />

## Changelog

### 11-03-2024 day_outside color

- Changed the color of the `day_outside` class to the following to improve contrast:

  ```tsx showLineNumbers title="calendar.tsx"
  "day_outside:
        "day-outside text-muted-foreground aria-selected:bg-accent/50 aria-selected:text-muted-foreground",
  ```

```

### 📄 components/card.mdx

```
---
title: Card
description: Displays a card with header, content, and footer.
component: true
---

<ComponentPreview name="card-with-form" description="A card with a form" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add card
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="card" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card"
```

```tsx
<Card>
  <CardHeader>
    <CardTitle>Card Title</CardTitle>
    <CardDescription>Card Description</CardDescription>
  </CardHeader>
  <CardContent>
    <p>Card Content</p>
  </CardContent>
  <CardFooter>
    <p>Card Footer</p>
  </CardFooter>
</Card>
```

## Examples

<ComponentPreview
  name="card-demo"
  description="A card showing notifications settings."
/>

## Changelog

### 11-03-2024 a11y for title and description

- Changed the `CardTitle` and `CardDescription` components to use `div` instead of `h3` and `p` to improve accessibility.

```tsx showLineNumbers title="card.tsx"
const CardTitle = React.forwardRef<
  HTMLDivElement,
  React.HTMLAttributes<HTMLDivElement>
>(({ className, ...props }, ref) => (
  <div
    ref={ref}
    className={cn("font-semibold leading-none tracking-tight", className)}
    {...props}
  />
))
CardTitle.displayName = "CardTitle"

const CardDescription = React.forwardRef<
  HTMLDivElement,
  React.HTMLAttributes<HTMLDivElement>
>(({ className, ...props }, ref) => (
  <div
    ref={ref}
    className={cn("text-sm text-muted-foreground", className)}
    {...props}
  />
))
CardDescription.displayName = "CardDescription"
```

```

### 📄 components/carousel.mdx

```
---
title: Carousel
description: A carousel with motion and swipe built using Embla.
component: true
links:
  doc: https://www.embla-carousel.com/get-started/react
  api: https://www.embla-carousel.com/api
---

<ComponentPreview
  name="carousel-demo"
  title="Carousel"
  description="A carousel with 5 items and a previous and next button."
/>

## About

The carousel component is built using the [Embla Carousel](https://www.embla-carousel.com/) library.

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>

<TabsContent value="cli">

```bash
npx shadcn@latest add carousel
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install embla-carousel-react
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="carousel" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/ui/carousel"
```

```tsx
<Carousel>
  <CarouselContent>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
  </CarouselContent>
  <CarouselPrevious />
  <CarouselNext />
</Carousel>
```

## Examples

### Sizes

To set the size of the items, you can use the `basis` utility class on the `<CarouselItem />`.

<ComponentPreview
  name="carousel-size"
  title="Carousel"
  description="A carousel with 3 active items of equal size."
/>

```tsx title="Example" showLineNumbers {4-6}
// 33% of the carousel width.
<Carousel>
  <CarouselContent>
    <CarouselItem className="basis-1/3">...</CarouselItem>
    <CarouselItem className="basis-1/3">...</CarouselItem>
    <CarouselItem className="basis-1/3">...</CarouselItem>
  </CarouselContent>
</Carousel>
```

```tsx title="Responsive" showLineNumbers {4-6}
// 50% on small screens and 33% on larger screens.
<Carousel>
  <CarouselContent>
    <CarouselItem className="md:basis-1/2 lg:basis-1/3">...</CarouselItem>
    <CarouselItem className="md:basis-1/2 lg:basis-1/3">...</CarouselItem>
    <CarouselItem className="md:basis-1/2 lg:basis-1/3">...</CarouselItem>
  </CarouselContent>
</Carousel>
```

### Spacing

To set the spacing between the items, we use a `pl-[VALUE]` utility on the `<CarouselItem />` and a negative `-ml-[VALUE]` on the `<CarouselContent />`.

<Callout className="mt-6">
  **Why:** I tried to use the `gap` property or a `grid` layout on the `
  <CarouselContent />` but it required a lot of math and mental effort to get the
  spacing right. I found `pl-[VALUE]` and `-ml-[VALUE]` utilities much easier to
  use.

You can always adjust this in your own project if you need to.

</Callout>

<ComponentPreview
  name="carousel-spacing"
  title="Carousel"
  description="A carousel with 3 items with a spacing of 1rem."
/>

```tsx title="Example" showLineNumbers /-ml-4/ /pl-4/
<Carousel>
  <CarouselContent className="-ml-4">
    <CarouselItem className="pl-4">...</CarouselItem>
    <CarouselItem className="pl-4">...</CarouselItem>
    <CarouselItem className="pl-4">...</CarouselItem>
  </CarouselContent>
</Carousel>
```

```tsx title="Responsive" showLineNumbers /-ml-2/ /pl-2/ /md:-ml-4/ /md:pl-4/
<Carousel>
  <CarouselContent className="-ml-2 md:-ml-4">
    <CarouselItem className="pl-2 md:pl-4">...</CarouselItem>
    <CarouselItem className="pl-2 md:pl-4">...</CarouselItem>
    <CarouselItem className="pl-2 md:pl-4">...</CarouselItem>
  </CarouselContent>
</Carousel>
```

### Orientation

Use the `orientation` prop to set the orientation of the carousel.

<ComponentPreview
  name="carousel-orientation"
  title="Carousel"
  description="A vertical carousel."
/>

```tsx showLineNumbers /vertical | horizontal/
<Carousel orientation="vertical | horizontal">
  <CarouselContent>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
  </CarouselContent>
</Carousel>
```

## Options

You can pass options to the carousel using the `opts` prop. See the [Embla Carousel docs](https://www.embla-carousel.com/api/options/) for more information.

```tsx showLineNumbers {2-5}
<Carousel
  opts={{
    align: "start",
    loop: true,
  }}
>
  <CarouselContent>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
    <CarouselItem>...</CarouselItem>
  </CarouselContent>
</Carousel>
```

## API

Use a state and the `setApi` props to get an instance of the carousel API.

<ComponentPreview
  name="carousel-api"
  title="Carousel"
  description="A carousel with a slide counter."
/>

```tsx showLineNumbers {1,4,22}
import { type CarouselApi } from "@/components/ui/carousel"

export function Example() {
  const [api, setApi] = React.useState<CarouselApi>()
  const [current, setCurrent] = React.useState(0)
  const [count, setCount] = React.useState(0)

  React.useEffect(() => {
    if (!api) {
      return
    }

    setCount(api.scrollSnapList().length)
    setCurrent(api.selectedScrollSnap() + 1)

    api.on("select", () => {
      setCurrent(api.selectedScrollSnap() + 1)
    })
  }, [api])

  return (
    <Carousel setApi={setApi}>
      <CarouselContent>
        <CarouselItem>...</CarouselItem>
        <CarouselItem>...</CarouselItem>
        <CarouselItem>...</CarouselItem>
      </CarouselContent>
    </Carousel>
  )
}
```

## Events

You can listen to events using the api instance from `setApi`.

```tsx showLineNumbers {1,4-14,16}
import { type CarouselApi } from "@/components/ui/carousel"

export function Example() {
  const [api, setApi] = React.useState<CarouselApi>()

  React.useEffect(() => {
    if (!api) {
      return
    }

    api.on("select", () => {
      // Do something on select.
    })
  }, [api])

  return (
    <Carousel setApi={setApi}>
      <CarouselContent>
        <CarouselItem>...</CarouselItem>
        <CarouselItem>...</CarouselItem>
        <CarouselItem>...</CarouselItem>
      </CarouselContent>
    </Carousel>
  )
}
```

See the [Embla Carousel docs](https://www.embla-carousel.com/api/events/) for more information on using events.

## Plugins

You can use the `plugins` prop to add plugins to the carousel.

```ts showLineNumbers {1,6-10}
import Autoplay from "embla-carousel-autoplay"

export function Example() {
  return (
    <Carousel
      plugins={[
        Autoplay({
          delay: 2000,
        }),
      ]}
    >
      // ...
    </Carousel>
  )
}
```

<ComponentPreview
  name="carousel-plugin"
  title="Carousel"
  description="A carousel with the autoplay plugin."
/>

See the [Embla Carousel docs](https://www.embla-carousel.com/api/plugins/) for more information on using plugins.

```

### 📄 components/chart.mdx

```
---
title: Chart
description: Beautiful charts. Built using Recharts. Copy and paste into your apps.
component: true
---

<Callout className="mb-6">

**Note:** If you are using charts with **React 19** or the **Next.js 15**, see the note [here](/docs/react-19#recharts).

</Callout>

<ComponentPreview
  name="chart-bar-interactive"
  className="-mt-4 [&_.preview]:p-0 [&_.preview]:border-t [&_.preview>div]:shadow-none [&_.preview>div]:border-none [&_.preview>div]:w-full [&_.preview]:lg:min-h-[404px]"
  hideCode
/>

Introducing **Charts**. A collection of chart components that you can copy and paste into your apps.

Charts are designed to look great out of the box. They work well with the other components and are fully customizable to fit your project.

[Browse the Charts Library](/charts).

## Component

We use [Recharts](https://recharts.org/) under the hood.

We designed the `chart` component with composition in mind. **You build your charts using Recharts components and only bring in custom components, such as `ChartTooltip`, when and where you need it**.

```tsx showLineNumbers /ChartContainer/ /ChartTooltipContent/
import { Bar, BarChart } from "recharts"

import { ChartContainer, ChartTooltipContent } from "@/components/ui/charts"

export function MyChart() {
  return (
    <ChartContainer>
      <BarChart data={data}>
        <Bar dataKey="value" />
        <ChartTooltip content={<ChartTooltipContent />} />
      </BarChart>
    </ChartContainer>
  )
}
```

We do not wrap Recharts. This means you're not locked into an abstraction. When a new Recharts version is released, you can follow the official upgrade path to upgrade your charts.

**The components are yours**.

## Installation

<Callout className="mt-4">

**Note:** If you are using charts with **React 19** or the **Next.js 15**, see the note [here](/docs/react-19#recharts).

</Callout>

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

<Step>Run the following command to install `chart.tsx`</Step>

```bash
npx shadcn@latest add chart
```

<Step>Add the following colors to your CSS file</Step>

```css
@layer base {
  :root {
    --chart-1: 12 76% 61%;
    --chart-2: 173 58% 39%;
    --chart-3: 197 37% 24%;
    --chart-4: 43 74% 66%;
    --chart-5: 27 87% 67%;
  }

  .dark {
    --chart-1: 220 70% 50%;
    --chart-2: 160 60% 45%;
    --chart-3: 30 80% 55%;
    --chart-4: 280 65% 60%;
    --chart-5: 340 75% 55%;
  }
}
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install recharts
```

<Step>Copy and paste the following code into `components/ui/chart.tsx`.</Step>

<ComponentSource name="chart" />

<Step>Add the following colors to your CSS file</Step>

```css
@layer base {
  :root {
    --chart-1: 12 76% 61%;
    --chart-2: 173 58% 39%;
    --chart-3: 197 37% 24%;
    --chart-4: 43 74% 66%;
    --chart-5: 27 87% 67%;
  }

  .dark {
    --chart-1: 220 70% 50%;
    --chart-2: 160 60% 45%;
    --chart-3: 30 80% 55%;
    --chart-4: 280 65% 60%;
    --chart-5: 340 75% 55%;
  }
}
```

</Steps>

</TabsContent>

</Tabs>

## Your First Chart

Let's build your first chart. We'll build a bar chart, add a grid, axis, tooltip and legend.

<Steps>

<Step>Start by defining your data</Step>

The following data represents the number of desktop and mobile users for each month.

<Callout className="mt-4">

**Note:** Your data can be in any shape. You are not limited to the shape of the data below. Use the `dataKey` prop to map your data to the chart.

</Callout>

```tsx
const chartData = [
  { month: "January", desktop: 186, mobile: 80 },
  { month: "February", desktop: 305, mobile: 200 },
  { month: "March", desktop: 237, mobile: 120 },
  { month: "April", desktop: 73, mobile: 190 },
  { month: "May", desktop: 209, mobile: 130 },
  { month: "June", desktop: 214, mobile: 140 },
]
```

<Step>Define your chart config</Step>

The chart config holds configuration for the chart. This is where you place human-readable strings, such as labels, icons and color tokens for theming.

```tsx
import { type ChartConfig } from "@/components/ui/chart"

const chartConfig = {
  desktop: {
    label: "Desktop",
    color: "#2563eb",
  },
  mobile: {
    label: "Mobile",
    color: "#60a5fa",
  },
} satisfies ChartConfig
```

<Step>Build your chart</Step>

You can now build your chart using Recharts components.

<Callout className="mt-4 bg-amber-50 border-amber-200 dark:bg-amber-950/50 dark:border-amber-950">

**Important:** Remember to set a `min-h-[VALUE]` on the `ChartContainer` component. This is required for the chart be responsive.

</Callout>

<ComponentSource name="chart-bar-demo" />

<ComponentPreview
  name="chart-bar-demo"
  className="[&_.preview]:p-4 [&_.preview]:min-h-[250px]"
/>

</Steps>

### Add a Grid

Let's add a grid to the chart.

<Steps>

<Step>Import the `CartesianGrid` component.</Step>

```tsx /CartesianGrid/
import { Bar, BarChart, CartesianGrid } from "recharts"
```

<Step>Add the `CartesianGrid` component to your chart.</Step>

```tsx showLineNumbers {3}
<ChartContainer config={chartConfig} className="min-h-[200px] w-full">
  <BarChart accessibilityLayer data={chartData}>
    <CartesianGrid vertical={false} />
    <Bar dataKey="desktop" fill="var(--color-desktop)" radius={4} />
    <Bar dataKey="mobile" fill="var(--color-mobile)" radius={4} />
  </BarChart>
</ChartContainer>
```

<ComponentPreview
  name="chart-bar-demo-grid"
  className="[&_.preview]:p-4 [&_.preview]:min-h-[250px]"
/>

</Steps>

### Add an Axis

To add an x-axis to the chart, we'll use the `XAxis` component.

<Steps>

<Step>Import the `XAxis` component.</Step>

```tsx /XAxis/
import { Bar, BarChart, CartesianGrid, XAxis } from "recharts"
```

<Step>Add the `XAxis` component to your chart.</Step>

```tsx showLineNumbers {4-10}
<ChartContainer config={chartConfig} className="h-[200px] w-full">
  <BarChart accessibilityLayer data={chartData}>
    <CartesianGrid vertical={false} />
    <XAxis
      dataKey="month"
      tickLine={false}
      tickMargin={10}
      axisLine={false}
      tickFormatter={(value) => value.slice(0, 3)}
    />
    <Bar dataKey="desktop" fill="var(--color-desktop)" radius={4} />
    <Bar dataKey="mobile" fill="var(--color-mobile)" radius={4} />
  </BarChart>
</ChartContainer>
```

<ComponentPreview
  name="chart-bar-demo-axis"
  className="[&_.preview]:p-4 [&_.preview]:min-h-[250px]"
/>

</Steps>

### Add Tooltip

So far we've only used components from Recharts. They look great out of the box thanks to some customization in the `chart` component.

To add a tooltip, we'll use the custom `ChartTooltip` and `ChartTooltipContent` components from `chart`.

<Steps>

<Step>Import the `ChartTooltip` and `ChartTooltipContent` components.</Step>

```tsx
import { ChartTooltip, ChartTooltipContent } from "@/components/ui/chart"
```

<Step>Add the components to your chart.</Step>

```tsx showLineNumbers {11}
<ChartContainer config={chartConfig} className="h-[200px] w-full">
  <BarChart accessibilityLayer data={chartData}>
    <CartesianGrid vertical={false} />
    <XAxis
      dataKey="month"
      tickLine={false}
      tickMargin={10}
      axisLine={false}
      tickFormatter={(value) => value.slice(0, 3)}
    />
    <ChartTooltip content={<ChartTooltipContent />} />
    <Bar dataKey="desktop" fill="var(--color-desktop)" radius={4} />
    <Bar dataKey="mobile" fill="var(--color-mobile)" radius={4} />
  </BarChart>
</ChartContainer>
```

<ComponentPreview
  name="chart-bar-demo-tooltip"
  className="[&_.preview]:p-4 [&_.preview]:min-h-[250px]"
/>

Hover to see the tooltips. Easy, right? Two components, and we've got a beautiful tooltip.

</Steps>

### Add Legend

We'll do the same for the legend. We'll use the `ChartLegend` and `ChartLegendContent` components from `chart`.

<Steps>

<Step>Import the `ChartLegend` and `ChartLegendContent` components.</Step>

```tsx
import { ChartLegend, ChartLegendContent } from "@/components/ui/chart"
```

<Step>Add the components to your chart.</Step>

```tsx showLineNumbers {12}
<ChartContainer config={chartConfig} className="h-[200px] w-full">
  <BarChart accessibilityLayer data={chartData}>
    <CartesianGrid vertical={false} />
    <XAxis
      dataKey="month"
      tickLine={false}
      tickMargin={10}
      axisLine={false}
      tickFormatter={(value) => value.slice(0, 3)}
    />
    <ChartTooltip content={<ChartTooltipContent />} />
    <ChartLegend content={<ChartLegendContent />} />
    <Bar dataKey="desktop" fill="var(--color-desktop)" radius={4} />
    <Bar dataKey="mobile" fill="var(--color-mobile)" radius={4} />
  </BarChart>
</ChartContainer>
```

<ComponentPreview
  name="chart-bar-demo-legend"
  className="[&_.preview]:p-4 [&_.preview]:min-h-[250px]"
/>

</Steps>

Done. You've built your first chart! What's next?

- [Themes and Colors](/docs/components/chart#theming)
- [Tooltip](/docs/components/chart#tooltip)
- [Legend](/docs/components/chart#legend)

## Chart Config

The chart config is where you define the labels, icons and colors for a chart.

It is intentionally decoupled from chart data.

This allows you to share config and color tokens between charts. It can also works independently for cases where your data or color tokens live remotely or in a different format.

```tsx /ChartConfig/
import { Monitor } from "lucide-react"

import { type ChartConfig } from "@/components/ui/chart"

const chartConfig = {
  desktop: {
    label: "Desktop",
    icon: Monitor,
    // A color like 'hsl(220, 98%, 61%)' or 'var(--color-name)'
    color: "#2563eb",
    // OR a theme object with 'light' and 'dark' keys
    theme: {
      light: "#2563eb",
      dark: "#dc2626",
    },
  },
} satisfies ChartConfig
```

## Theming

Charts has built-in support for theming. You can use css variables (recommended) or color values in any color format, such as hex, hsl or oklch.

### CSS Variables

<Steps>

<Step>Define your colors in your css file</Step>

```css {6-7,14-15} title="globals.css"
@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 240 10% 3.9%;
    // ...
    --chart-1: 12 76% 61%;
    --chart-2: 173 58% 39%;
  }

  .dark: {
    --background: 240 10% 3.9%;
    --foreground: 0 0% 100%;
    // ...
    --chart-1: 220 70% 50%;
    --chart-2: 160 60% 45%;
  }
}
```

<Step>Add the color to your `chartConfig`</Step>

```tsx {4,8}
const chartConfig = {
  desktop: {
    label: "Desktop",
    color: "hsl(var(--chart-1))",
  },
  mobile: {
    label: "Mobile",
    color: "hsl(var(--chart-2))",
  },
} satisfies ChartConfig
```

<Callout className="mt-4">

We're wrapping the value in `hsl()` here because we define the colors without color space function.

This is not required. You can use full color values, such as hex, hsl or oklch.

```css
--chart-1: oklch(70% 0.227 154.59);
```

```tsx
color: "var(--chart-1)",
```

</Callout>

</Steps>

### hex, hsl or oklch

You can also define your colors directly in the chart config. Use the color format you prefer.

```tsx
const chartConfig = {
  desktop: {
    label: "Desktop",
    color: "#2563eb",
  },
} satisfies ChartConfig
```

### Using Colors

To use the theme colors in your chart, reference the colors using the format `var(--color-KEY)`.

#### Components

```tsx
<Bar dataKey="desktop" fill="var(--color-desktop)" />
```

#### Chart Data

```tsx
const chartData = [
  { browser: "chrome", visitors: 275, fill: "var(--color-chrome)" },
  { browser: "safari", visitors: 200, fill: "var(--color-safari)" },
]
```

#### Tailwind

```tsx
<LabelList className="fill-[--color-desktop]" />
```

## Tooltip

A chart tooltip contains a label, name, indicator and value. You can use a combination of these to customize your tooltip.

<ComponentPreview
  name="chart-tooltip-demo"
  className="[&_.preview]:py-0"
  hideCode
/>

You can turn on/off any of these using the `hideLabel`, `hideIndicator` props and customize the indicator style using the `indicator` prop.

Use `labelKey` and `nameKey` to use a custom key for the tooltip label and name.

Chart comes with the `<ChartTooltip>` and `<ChartTooltipContent>` components. You can use these two components to add custom tooltips to your chart.

```tsx
import { ChartTooltip, ChartTooltipContent } from "@/components/ui/chart"
```

```tsx
<ChartTooltip content={<ChartTooltipContent />} />
```

### Props

Use the following props to customize the tooltip.

| Prop            | Type                     | Description                                  |
| :-------------- | :----------------------- | :------------------------------------------- |
| `labelKey`      | string                   | The config or data key to use for the label. |
| `nameKey`       | string                   | The config or data key to use for the name.  |
| `indicator`     | `dot` `line` or `dashed` | The indicator style for the tooltip.         |
| `hideLabel`     | boolean                  | Whether to hide the label.                   |
| `hideIndicator` | boolean                  | Whether to hide the indicator.               |

### Colors

Colors are automatically referenced from the chart config.

### Custom

To use a custom key for tooltip label and names, use the `labelKey` and `nameKey` props.

```tsx /browser/
const chartData = [
  { browser: "chrome", visitors: 187, fill: "var(--color-chrome)" },
  { browser: "safari", visitors: 200, fill: "var(--color-safari)" },
]

const chartConfig = {
  visitors: {
    label: "Total Visitors",
  },
  chrome: {
    label: "Chrome",
    color: "hsl(var(--chart-1))",
  },
  safari: {
    label: "Safari",
    color: "hsl(var(--chart-2))",
  },
} satisfies ChartConfig
```

```tsx
<ChartTooltip
  content={<ChartTooltipContent labelKey="visitors" nameKey="browser" />}
/>
```

This will use `Total Visitors` for label and `Chrome` and `Safari` for the tooltip names.

## Legend

You can use the custom `<ChartLegend>` and `<ChartLegendContent>` components to add a legend to your chart.

```tsx
import { ChartLegend, ChartLegendContent } from "@/components/ui/chart"
```

```tsx
<ChartLegend content={<ChartLegendContent />} />
```

### Colors

Colors are automatically referenced from the chart config.

### Custom

To use a custom key for legend names, use the `nameKey` prop.

```tsx /browser/
const chartData = [
  { browser: "chrome", visitors: 187, fill: "var(--color-chrome)" },
  { browser: "safari", visitors: 200, fill: "var(--color-safari)" },
]

const chartConfig = {
  chrome: {
    label: "Chrome",
    color: "hsl(var(--chart-1))",
  },
  safari: {
    label: "Safari",
    color: "hsl(var(--chart-2))",
  },
} satisfies ChartConfig
```

```tsx
<ChartLegend content={<ChartLegendContent nameKey="browser" />} />
```

This will use `Chrome` and `Safari` for the legend names.

## Accessibility

You can turn on the `accessibilityLayer` prop to add an accessible layer to your chart.

This prop adds keyboard access and screen reader support to your charts.

```tsx
<LineChart accessibilityLayer />
```

```

### 📄 components/checkbox.mdx

```
---
title: Checkbox
description: A control that allows the user to toggle between checked and not checked.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/checkbox
  api: https://www.radix-ui.com/docs/primitives/components/checkbox#api-reference
---

<ComponentPreview name="checkbox-demo" description="A checkbox" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add checkbox
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-checkbox
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="checkbox" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Checkbox } from "@/components/ui/checkbox"
```

```tsx
<Checkbox />
```

## Examples

### With text

<ComponentPreview
  name="checkbox-with-text"
  description="A checkbox with label and description."
/>

### Disabled

<ComponentPreview name="checkbox-disabled" description="A disabled checkbox" />

### Form

<ComponentPreview name="checkbox-form-single" />

<ComponentPreview name="checkbox-form-multiple" />

```

### 📄 components/collapsible.mdx

```
---
title: Collapsible
description: An interactive component which expands/collapses a panel.
component: true
featured: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/collapsible
  api: https://www.radix-ui.com/docs/primitives/components/collapsible#api-reference
---

<ComponentPreview
  name="collapsible-demo"
  description="A collapsible component."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add collapsible
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-collapsible
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="collapsible" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Collapsible,
  CollapsibleContent,
  CollapsibleTrigger,
} from "@/components/ui/collapsible"
```

```tsx
<Collapsible>
  <CollapsibleTrigger>Can I use this in my project?</CollapsibleTrigger>
  <CollapsibleContent>
    Yes. Free to use for personal and commercial projects. No attribution
    required.
  </CollapsibleContent>
</Collapsible>
```

```

### 📄 components/combobox.mdx

```
---
title: Combobox
description: Autocomplete input and command palette with a list of suggestions.
component: true
---

<ComponentPreview
  name="combobox-demo"
  description="A combobox with a list of frameworks."
/>

## Installation

The Combobox is built using a composition of the `<Popover />` and the `<Command />` components.

See installation instructions for the [Popover](/docs/components/popover#installation) and the [Command](/docs/components/command#installation) components.

## Usage

```tsx
"use client"

import * as React from "react"
import { Check, ChevronsUpDown } from "lucide-react"

import { cn } from "@/lib/utils"
import { Button } from "@/components/ui/button"
import {
  Command,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
} from "@/components/ui/command"
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"

const frameworks = [
  {
    value: "next.js",
    label: "Next.js",
  },
  {
    value: "sveltekit",
    label: "SvelteKit",
  },
  {
    value: "nuxt.js",
    label: "Nuxt.js",
  },
  {
    value: "remix",
    label: "Remix",
  },
  {
    value: "astro",
    label: "Astro",
  },
]

export function ComboboxDemo() {
  const [open, setOpen] = React.useState(false)
  const [value, setValue] = React.useState("")

  return (
    <Popover open={open} onOpenChange={setOpen}>
      <PopoverTrigger asChild>
        <Button
          variant="outline"
          role="combobox"
          aria-expanded={open}
          className="w-[200px] justify-between"
        >
          {value
            ? frameworks.find((framework) => framework.value === value)?.label
            : "Select framework..."}
          <ChevronsUpDown className="ml-2 h-4 w-4 shrink-0 opacity-50" />
        </Button>
      </PopoverTrigger>
      <PopoverContent className="w-[200px] p-0">
        <Command>
          <CommandInput placeholder="Search framework..." />
          <CommandList>
            <CommandEmpty>No framework found.</CommandEmpty>
            <CommandGroup>
              {frameworks.map((framework) => (
                <CommandItem
                  key={framework.value}
                  value={framework.value}
                  onSelect={(currentValue) => {
                    setValue(currentValue === value ? "" : currentValue)
                    setOpen(false)
                  }}
                >
                  <Check
                    className={cn(
                      "mr-2 h-4 w-4",
                      value === framework.value ? "opacity-100" : "opacity-0"
                    )}
                  />
                  {framework.label}
                </CommandItem>
              ))}
            </CommandGroup>
          </CommandList>
        </Command>
      </PopoverContent>
    </Popover>
  )
}
```

## Examples

### Combobox

<ComponentPreview
  name="combobox-demo"
  description="A combobox with a list of frameworks."
/>

### Popover

<ComponentPreview name="combobox-popover" />

### Dropdown menu

<ComponentPreview
  name="combobox-dropdown-menu"
  description="A combobox in a dropdown menu"
/>

### Responsive

You can create a responsive combobox by using the `<Popover />` on desktop and the `<Drawer />` components on mobile.

<ComponentPreview name="combobox-responsive" />

### Form

<ComponentPreview name="combobox-form" />

```

### 📄 components/command.mdx

```
---
title: Command
description: Fast, composable, unstyled command menu for React.
component: true
links:
  doc: https://cmdk.paco.me
---

<ComponentPreview
  name="command-demo"
  align="start"
  className="[&_.preview>div]:max-w-[450px]"
  description="A command menu"
/>

## About

The `<Command />` component uses the [`cmdk`](https://cmdk.paco.me) component by [pacocoursey](https://twitter.com/pacocoursey).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add command
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install cmdk
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="command" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Command,
  CommandDialog,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
  CommandSeparator,
  CommandShortcut,
} from "@/components/ui/command"
```

```tsx
<Command>
  <CommandInput placeholder="Type a command or search..." />
  <CommandList>
    <CommandEmpty>No results found.</CommandEmpty>
    <CommandGroup heading="Suggestions">
      <CommandItem>Calendar</CommandItem>
      <CommandItem>Search Emoji</CommandItem>
      <CommandItem>Calculator</CommandItem>
    </CommandGroup>
    <CommandSeparator />
    <CommandGroup heading="Settings">
      <CommandItem>Profile</CommandItem>
      <CommandItem>Billing</CommandItem>
      <CommandItem>Settings</CommandItem>
    </CommandGroup>
  </CommandList>
</Command>
```

## Examples

### Dialog

<ComponentPreview
  name="command-dialog"
  description="A command menu in a dialog"
/>

To show the command menu in a dialog, use the `<CommandDialog />` component.

```tsx
export function CommandMenu() {
  const [open, setOpen] = React.useState(false)

  React.useEffect(() => {
    const down = (e: KeyboardEvent) => {
      if (e.key === "k" && (e.metaKey || e.ctrlKey)) {
        e.preventDefault()
        setOpen((open) => !open)
      }
    }
    document.addEventListener("keydown", down)
    return () => document.removeEventListener("keydown", down)
  }, [])

  return (
    <CommandDialog open={open} onOpenChange={setOpen}>
      <CommandInput placeholder="Type a command or search..." />
      <CommandList>
        <CommandEmpty>No results found.</CommandEmpty>
        <CommandGroup heading="Suggestions">
          <CommandItem>Calendar</CommandItem>
          <CommandItem>Search Emoji</CommandItem>
          <CommandItem>Calculator</CommandItem>
        </CommandGroup>
      </CommandList>
    </CommandDialog>
  )
}
```

### Combobox

You can use the `<Command />` component as a combobox. See the [Combobox](/docs/components/combobox) page for more information.

## Changelog

### 2024-10-25 Classes for icons

Added `gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0` to the `<CommandItem />` to automatically style icon inside.

Add the following classes to the `cva` call in your `command.tsx` file.

```tsx showLineNumbers title="command.tsx"
const CommandItem = React.forwardRef<
  React.ElementRef<typeof CommandPrimitive.Item>,
  React.ComponentPropsWithoutRef<typeof CommandPrimitive.Item>
>(({ className, ...props }, ref) => (
  <CommandPrimitive.Item
    ref={ref}
    className={cn(
      "... gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0",
      className
    )}
    {...props}
  />
))
```

```

### 📄 components/context-menu.mdx

```
---
title: Context Menu
description: Displays a menu to the user — such as a set of actions or functions — triggered by a button.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/context-menu
  api: https://www.radix-ui.com/docs/primitives/components/context-menu#api-reference
---

<ComponentPreview
  name="context-menu-demo"
  description="A context menu with sub menu items."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add context-menu
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-context-menu
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="context-menu" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  ContextMenu,
  ContextMenuContent,
  ContextMenuItem,
  ContextMenuTrigger,
} from "@/components/ui/context-menu"
```

```tsx
<ContextMenu>
  <ContextMenuTrigger>Right click</ContextMenuTrigger>
  <ContextMenuContent>
    <ContextMenuItem>Profile</ContextMenuItem>
    <ContextMenuItem>Billing</ContextMenuItem>
    <ContextMenuItem>Team</ContextMenuItem>
    <ContextMenuItem>Subscription</ContextMenuItem>
  </ContextMenuContent>
</ContextMenu>
```

```

### 📄 components/data-table.mdx

```
---
title: Data Table
description: Powerful table and datagrids built using TanStack Table.
component: true
links:
  doc: https://tanstack.com/table/v8/docs/introduction
---

<ComponentPreview name="data-table-demo" className="[&_.preview]:items-start" />

## Introduction

Every data table or datagrid I've created has been unique. They all behave differently, have specific sorting and filtering requirements, and work with different data sources.

It doesn't make sense to combine all of these variations into a single component. If we do that, we'll lose the flexibility that [headless UI](https://tanstack.com/table/v8/docs/introduction#what-is-headless-ui) provides.

So instead of a data-table component, I thought it would be more helpful to provide a guide on how to build your own.

We'll start with the basic `<Table />` component and build a complex data table from scratch.

<Callout className="mt-4">

**Tip:** If you find yourself using the same table in multiple places in your app, you can always extract it into a reusable component.

</Callout>

## Table of Contents

This guide will show you how to use [TanStack Table](https://tanstack.com/table) and the `<Table />` component to build your own custom data table. We'll cover the following topics:

- [Basic Table](#basic-table)
- [Row Actions](#row-actions)
- [Pagination](#pagination)
- [Sorting](#sorting)
- [Filtering](#filtering)
- [Visibility](#visibility)
- [Row Selection](#row-selection)
- [Reusable Components](#reusable-components)

## Installation

1. Add the `<Table />` component to your project:

```bash
npx shadcn@latest add table
```

2. Add `tanstack/react-table` dependency:

```bash
npm install @tanstack/react-table
```

## Prerequisites

We are going to build a table to show recent payments. Here's what our data looks like:

```tsx showLineNumbers
type Payment = {
  id: string
  amount: number
  status: "pending" | "processing" | "success" | "failed"
  email: string
}

export const payments: Payment[] = [
  {
    id: "728ed52f",
    amount: 100,
    status: "pending",
    email: "m@example.com",
  },
  {
    id: "489e1d42",
    amount: 125,
    status: "processing",
    email: "example@gmail.com",
  },
  // ...
]
```

## Project Structure

Start by creating the following file structure:

```txt
app
└── payments
    ├── columns.tsx
    ├── data-table.tsx
    └── page.tsx
```

I'm using a Next.js example here but this works for any other React framework.

- `columns.tsx` (client component) will contain our column definitions.
- `data-table.tsx` (client component) will contain our `<DataTable />` component.
- `page.tsx` (server component) is where we'll fetch data and render our table.

## Basic Table

Let's start by building a basic table.

<Steps>

### Column Definitions

First, we'll define our columns.

```tsx showLineNumbers title="app/payments/columns.tsx" {3,14-27}
"use client"

import { ColumnDef } from "@tanstack/react-table"

// This type is used to define the shape of our data.
// You can use a Zod schema here if you want.
export type Payment = {
  id: string
  amount: number
  status: "pending" | "processing" | "success" | "failed"
  email: string
}

export const columns: ColumnDef<Payment>[] = [
  {
    accessorKey: "status",
    header: "Status",
  },
  {
    accessorKey: "email",
    header: "Email",
  },
  {
    accessorKey: "amount",
    header: "Amount",
  },
]
```

<Callout className="mt-4">

**Note:** Columns are where you define the core of what your table
will look like. They define the data that will be displayed, how it will be
formatted, sorted and filtered.

</Callout>

### `<DataTable />` component

Next, we'll create a `<DataTable />` component to render our table.

```tsx showLineNumbers title="app/payments/data-table.tsx"
"use client"

import {
  ColumnDef,
  flexRender,
  getCoreRowModel,
  useReactTable,
} from "@tanstack/react-table"

import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table"

interface DataTableProps<TData, TValue> {
  columns: ColumnDef<TData, TValue>[]
  data: TData[]
}

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const table = useReactTable({
    data,
    columns,
    getCoreRowModel: getCoreRowModel(),
  })

  return (
    <div className="rounded-md border">
      <Table>
        <TableHeader>
          {table.getHeaderGroups().map((headerGroup) => (
            <TableRow key={headerGroup.id}>
              {headerGroup.headers.map((header) => {
                return (
                  <TableHead key={header.id}>
                    {header.isPlaceholder
                      ? null
                      : flexRender(
                          header.column.columnDef.header,
                          header.getContext()
                        )}
                  </TableHead>
                )
              })}
            </TableRow>
          ))}
        </TableHeader>
        <TableBody>
          {table.getRowModel().rows?.length ? (
            table.getRowModel().rows.map((row) => (
              <TableRow
                key={row.id}
                data-state={row.getIsSelected() && "selected"}
              >
                {row.getVisibleCells().map((cell) => (
                  <TableCell key={cell.id}>
                    {flexRender(cell.column.columnDef.cell, cell.getContext())}
                  </TableCell>
                ))}
              </TableRow>
            ))
          ) : (
            <TableRow>
              <TableCell colSpan={columns.length} className="h-24 text-center">
                No results.
              </TableCell>
            </TableRow>
          )}
        </TableBody>
      </Table>
    </div>
  )
}
```

<Callout>

**Tip**: If you find yourself using `<DataTable />` in multiple places, this is the component you could make reusable by extracting it to `components/ui/data-table.tsx`.

`<DataTable columns={columns} data={data} />`

</Callout>

### Render the table

Finally, we'll render our table in our page component.

```tsx showLineNumbers title="app/payments/page.tsx" {22}
import { Payment, columns } from "./columns"
import { DataTable } from "./data-table"

async function getData(): Promise<Payment[]> {
  // Fetch data from your API here.
  return [
    {
      id: "728ed52f",
      amount: 100,
      status: "pending",
      email: "m@example.com",
    },
    // ...
  ]
}

export default async function DemoPage() {
  const data = await getData()

  return (
    <div className="container mx-auto py-10">
      <DataTable columns={columns} data={data} />
    </div>
  )
}
```

</Steps>

## Cell Formatting

Let's format the amount cell to display the dollar amount. We'll also align the cell to the right.

<Steps>

### Update columns definition

Update the `header` and `cell` definitions for amount as follows:

```tsx showLineNumbers title="app/payments/columns.tsx" {4-15}
export const columns: ColumnDef<Payment>[] = [
  {
    accessorKey: "amount",
    header: () => <div className="text-right">Amount</div>,
    cell: ({ row }) => {
      const amount = parseFloat(row.getValue("amount"))
      const formatted = new Intl.NumberFormat("en-US", {
        style: "currency",
        currency: "USD",
      }).format(amount)

      return <div className="text-right font-medium">{formatted}</div>
    },
  },
]
```

You can use the same approach to format other cells and headers.

</Steps>

## Row Actions

Let's add row actions to our table. We'll use a `<Dropdown />` component for this.

<Steps>

### Update columns definition

Update our columns definition to add a new `actions` column. The `actions` cell returns a `<Dropdown />` component.

```tsx showLineNumbers title="app/payments/columns.tsx" {4,6-14,18-45}
"use client"

import { ColumnDef } from "@tanstack/react-table"
import { MoreHorizontal } from "lucide-react"

import { Button } from "@/components/ui/button"
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"

export const columns: ColumnDef<Payment>[] = [
  // ...
  {
    id: "actions",
    cell: ({ row }) => {
      const payment = row.original

      return (
        <DropdownMenu>
          <DropdownMenuTrigger asChild>
            <Button variant="ghost" className="h-8 w-8 p-0">
              <span className="sr-only">Open menu</span>
              <MoreHorizontal className="h-4 w-4" />
            </Button>
          </DropdownMenuTrigger>
          <DropdownMenuContent align="end">
            <DropdownMenuLabel>Actions</DropdownMenuLabel>
            <DropdownMenuItem
              onClick={() => navigator.clipboard.writeText(payment.id)}
            >
              Copy payment ID
            </DropdownMenuItem>
            <DropdownMenuSeparator />
            <DropdownMenuItem>View customer</DropdownMenuItem>
            <DropdownMenuItem>View payment details</DropdownMenuItem>
          </DropdownMenuContent>
        </DropdownMenu>
      )
    },
  },
  // ...
]
```

You can access the row data using `row.original` in the `cell` function. Use this to handle actions for your row eg. use the `id` to make a DELETE call to your API.

</Steps>

## Pagination

Next, we'll add pagination to our table.

<Steps>

### Update `<DataTable>`

```tsx showLineNumbers title="app/payments/data-table.tsx" {5,17}
import {
  ColumnDef,
  flexRender,
  getCoreRowModel,
  getPaginationRowModel,
  useReactTable,
} from "@tanstack/react-table"

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const table = useReactTable({
    data,
    columns,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
  })

  // ...
}
```

This will automatically paginate your rows into pages of 10. See the [pagination docs](https://tanstack.com/table/v8/docs/api/features/pagination) for more information on customizing page size and implementing manual pagination.

### Add pagination controls

We can add pagination controls to our table using the `<Button />` component and the `table.previousPage()`, `table.nextPage()` API methods.

```tsx showLineNumbers title="app/payments/data-table.tsx" {1,15,21-39}
import { Button } from "@/components/ui/button"

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const table = useReactTable({
    data,
    columns,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
  })

  return (
    <div>
      <div className="rounded-md border">
        <Table>
          { // .... }
        </Table>
      </div>
      <div className="flex items-center justify-end space-x-2 py-4">
        <Button
          variant="outline"
          size="sm"
          onClick={() => table.previousPage()}
          disabled={!table.getCanPreviousPage()}
        >
          Previous
        </Button>
        <Button
          variant="outline"
          size="sm"
          onClick={() => table.nextPage()}
          disabled={!table.getCanNextPage()}
        >
          Next
        </Button>
      </div>
    </div>
  )
}
```

See [Reusable Components](#reusable-components) section for a more advanced pagination component.

</Steps>

## Sorting

Let's make the email column sortable.

<Steps>

### Update `<DataTable>`

```tsx showLineNumbers title="app/payments/data-table.tsx" showLineNumbers {3,6,10,18,25-28}
"use client"

import * as React from "react"
import {
  ColumnDef,
  SortingState,
  flexRender,
  getCoreRowModel,
  getPaginationRowModel,
  getSortedRowModel,
  useReactTable,
} from "@tanstack/react-table"

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const [sorting, setSorting] = React.useState<SortingState>([])

  const table = useReactTable({
    data,
    columns,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
    onSortingChange: setSorting,
    getSortedRowModel: getSortedRowModel(),
    state: {
      sorting,
    },
  })

  return (
    <div>
      <div className="rounded-md border">
        <Table>{ ... }</Table>
      </div>
    </div>
  )
}
```

### Make header cell sortable

We can now update the `email` header cell to add sorting controls.

```tsx showLineNumbers title="app/payments/columns.tsx" {4,9-19}
"use client"

import { ColumnDef } from "@tanstack/react-table"
import { ArrowUpDown } from "lucide-react"

export const columns: ColumnDef<Payment>[] = [
  {
    accessorKey: "email",
    header: ({ column }) => {
      return (
        <Button
          variant="ghost"
          onClick={() => column.toggleSorting(column.getIsSorted() === "asc")}
        >
          Email
          <ArrowUpDown className="ml-2 h-4 w-4" />
        </Button>
      )
    },
  },
]
```

This will automatically sort the table (asc and desc) when the user toggles on the header cell.

</Steps>

## Filtering

Let's add a search input to filter emails in our table.

<Steps>

### Update `<DataTable>`

```tsx showLineNumbers title="app/payments/data-table.tsx" {6,10,17,24-26,35-36,39,45-54}
"use client"

import * as React from "react"
import {
  ColumnDef,
  ColumnFiltersState,
  SortingState,
  flexRender,
  getCoreRowModel,
  getFilteredRowModel,
  getPaginationRowModel,
  getSortedRowModel,
  useReactTable,
} from "@tanstack/react-table"

import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const [sorting, setSorting] = React.useState<SortingState>([])
  const [columnFilters, setColumnFilters] = React.useState<ColumnFiltersState>(
    []
  )

  const table = useReactTable({
    data,
    columns,
    onSortingChange: setSorting,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
    getSortedRowModel: getSortedRowModel(),
    onColumnFiltersChange: setColumnFilters,
    getFilteredRowModel: getFilteredRowModel(),
    state: {
      sorting,
      columnFilters,
    },
  })

  return (
    <div>
      <div className="flex items-center py-4">
        <Input
          placeholder="Filter emails..."
          value={(table.getColumn("email")?.getFilterValue() as string) ?? ""}
          onChange={(event) =>
            table.getColumn("email")?.setFilterValue(event.target.value)
          }
          className="max-w-sm"
        />
      </div>
      <div className="rounded-md border">
        <Table>{ ... }</Table>
      </div>
    </div>
  )
}
```

Filtering is now enabled for the `email` column. You can add filters to other columns as well. See the [filtering docs](https://tanstack.com/table/v8/docs/guide/filters) for more information on customizing filters.

</Steps>

## Visibility

Adding column visibility is fairly simple using `@tanstack/react-table` visibility API.

<Steps>

### Update `<DataTable>`

```tsx showLineNumbers title="app/payments/data-table.tsx" {8,18-23,33-34,45,49,64-91}
"use client"

import * as React from "react"
import {
  ColumnDef,
  ColumnFiltersState,
  SortingState,
  VisibilityState,
  flexRender,
  getCoreRowModel,
  getFilteredRowModel,
  getPaginationRowModel,
  getSortedRowModel,
  useReactTable,
} from "@tanstack/react-table"

import { Button } from "@/components/ui/button"
import {
  DropdownMenu,
  DropdownMenuCheckboxItem,
  DropdownMenuContent,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"

export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const [sorting, setSorting] = React.useState<SortingState>([])
  const [columnFilters, setColumnFilters] = React.useState<ColumnFiltersState>(
    []
  )
  const [columnVisibility, setColumnVisibility] =
    React.useState<VisibilityState>({})

  const table = useReactTable({
    data,
    columns,
    onSortingChange: setSorting,
    onColumnFiltersChange: setColumnFilters,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
    getSortedRowModel: getSortedRowModel(),
    getFilteredRowModel: getFilteredRowModel(),
    onColumnVisibilityChange: setColumnVisibility,
    state: {
      sorting,
      columnFilters,
      columnVisibility,
    },
  })

  return (
    <div>
      <div className="flex items-center py-4">
        <Input
          placeholder="Filter emails..."
          value={table.getColumn("email")?.getFilterValue() as string}
          onChange={(event) =>
            table.getColumn("email")?.setFilterValue(event.target.value)
          }
          className="max-w-sm"
        />
        <DropdownMenu>
          <DropdownMenuTrigger asChild>
            <Button variant="outline" className="ml-auto">
              Columns
            </Button>
          </DropdownMenuTrigger>
          <DropdownMenuContent align="end">
            {table
              .getAllColumns()
              .filter(
                (column) => column.getCanHide()
              )
              .map((column) => {
                return (
                  <DropdownMenuCheckboxItem
                    key={column.id}
                    className="capitalize"
                    checked={column.getIsVisible()}
                    onCheckedChange={(value) =>
                      column.toggleVisibility(!!value)
                    }
                  >
                    {column.id}
                  </DropdownMenuCheckboxItem>
                )
              })}
          </DropdownMenuContent>
        </DropdownMenu>
      </div>
      <div className="rounded-md border">
        <Table>{ ... }</Table>
      </div>
    </div>
  )
}
```

This adds a dropdown menu that you can use to toggle column visibility.

</Steps>

## Row Selection

Next, we're going to add row selection to our table.

<Steps>

### Update column definitions

```tsx showLineNumbers title="app/payments/columns.tsx" {6,9-27}
"use client"

import { ColumnDef } from "@tanstack/react-table"

import { Badge } from "@/components/ui/badge"
import { Checkbox } from "@/components/ui/checkbox"

export const columns: ColumnDef<Payment>[] = [
  {
    id: "select",
    header: ({ table }) => (
      <Checkbox
        checked={
          table.getIsAllPageRowsSelected() ||
          (table.getIsSomePageRowsSelected() && "indeterminate")
        }
        onCheckedChange={(value) => table.toggleAllPageRowsSelected(!!value)}
        aria-label="Select all"
      />
    ),
    cell: ({ row }) => (
      <Checkbox
        checked={row.getIsSelected()}
        onCheckedChange={(value) => row.toggleSelected(!!value)}
        aria-label="Select row"
      />
    ),
    enableSorting: false,
    enableHiding: false,
  },
]
```

### Update `<DataTable>`

```tsx showLineNumbers title="app/payments/data-table.tsx" {11,23,28}
export function DataTable<TData, TValue>({
  columns,
  data,
}: DataTableProps<TData, TValue>) {
  const [sorting, setSorting] = React.useState<SortingState>([])
  const [columnFilters, setColumnFilters] = React.useState<ColumnFiltersState>(
    []
  )
  const [columnVisibility, setColumnVisibility] =
    React.useState<VisibilityState>({})
  const [rowSelection, setRowSelection] = React.useState({})

  const table = useReactTable({
    data,
    columns,
    onSortingChange: setSorting,
    onColumnFiltersChange: setColumnFilters,
    getCoreRowModel: getCoreRowModel(),
    getPaginationRowModel: getPaginationRowModel(),
    getSortedRowModel: getSortedRowModel(),
    getFilteredRowModel: getFilteredRowModel(),
    onColumnVisibilityChange: setColumnVisibility,
    onRowSelectionChange: setRowSelection,
    state: {
      sorting,
      columnFilters,
      columnVisibility,
      rowSelection,
    },
  })

  return (
    <div>
      <div className="rounded-md border">
        <Table />
      </div>
    </div>
  )
}
```

This adds a checkbox to each row and a checkbox in the header to select all rows.

### Show selected rows

You can show the number of selected rows using the `table.getFilteredSelectedRowModel()` API.

```tsx
<div className="flex-1 text-sm text-muted-foreground">
  {table.getFilteredSelectedRowModel().rows.length} of{" "}
  {table.getFilteredRowModel().rows.length} row(s) selected.
</div>
```

</Steps>

## Reusable Components

Here are some components you can use to build your data tables. This is from the [Tasks](/examples/tasks) demo.

### Column header

Make any column header sortable and hideable.

<ComponentSource src="/app/(app)/examples/tasks/components/data-table-column-header.tsx" />

```tsx {5}
export const columns = [
  {
    accessorKey: "email",
    header: ({ column }) => (
      <DataTableColumnHeader column={column} title="Email" />
    ),
  },
]
```

### Pagination

Add pagination controls to your table including page size and selection count.

<ComponentSource src="/app/(app)/examples/tasks/components/data-table-pagination.tsx" />

```tsx
<DataTablePagination table={table} />
```

### Column toggle

A component to toggle column visibility.

<ComponentSource src="/app/(app)/examples/tasks/components/data-table-view-options.tsx" />

```tsx
<DataTableViewOptions table={table} />
```

```

### 📄 components/date-picker.mdx

```
---
title: Date Picker
description: A date picker component with range and presets.
component: true
---

<ComponentPreview
  name="date-picker-demo"
  description="A date picker in a popover"
/>

## Installation

The Date Picker is built using a composition of the `<Popover />` and the `<Calendar />` components.

See installation instructions for the [Popover](/docs/components/popover#installation) and the [Calendar](/docs/components/calendar#installation) components.

## Usage

```tsx
"use client"

import * as React from "react"
import { format } from "date-fns"
import { Calendar as CalendarIcon } from "lucide-react"

import { cn } from "@/lib/utils"
import { Button } from "@/components/ui/button"
import { Calendar } from "@/components/ui/calendar"
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"

export function DatePickerDemo() {
  const [date, setDate] = React.useState<Date>()

  return (
    <Popover>
      <PopoverTrigger asChild>
        <Button
          variant={"outline"}
          className={cn(
            "w-[280px] justify-start text-left font-normal",
            !date && "text-muted-foreground"
          )}
        >
          <CalendarIcon className="mr-2 h-4 w-4" />
          {date ? format(date, "PPP") : <span>Pick a date</span>}
        </Button>
      </PopoverTrigger>
      <PopoverContent className="w-auto p-0">
        <Calendar
          mode="single"
          selected={date}
          onSelect={setDate}
          initialFocus
        />
      </PopoverContent>
    </Popover>
  )
}
```

See the [React DayPicker](https://react-day-picker.js.org) documentation for more information.

## Examples

### Date Picker

<ComponentPreview
  name="date-picker-demo"
  description="A date picker in a popover"
/>

### Date Range Picker

<ComponentPreview
  name="date-picker-with-range"
  description="A date range picker"
/>

### With Presets

<ComponentPreview
  name="date-picker-with-presets"
  description="A date picker with presets"
/>

### Form

<ComponentPreview name="date-picker-form" />

```

### 📄 components/dialog.mdx

```
---
title: Dialog
description: A window overlaid on either the primary window or another dialog window, rendering the content underneath inert.
featured: true
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/dialog
  api: https://www.radix-ui.com/docs/primitives/components/dialog#api-reference
---

<ComponentPreview
  name="dialog-demo"
  description="A dialog for editing profile details."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add dialog
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-dialog
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="dialog" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from "@/components/ui/dialog"
```

```tsx
<Dialog>
  <DialogTrigger>Open</DialogTrigger>
  <DialogContent>
    <DialogHeader>
      <DialogTitle>Are you absolutely sure?</DialogTitle>
      <DialogDescription>
        This action cannot be undone. This will permanently delete your account
        and remove your data from our servers.
      </DialogDescription>
    </DialogHeader>
  </DialogContent>
</Dialog>
```

## Examples

### Custom close button

<ComponentPreview name="dialog-close-button" />

## Notes

To activate the `Dialog` component from within a `Context Menu` or `Dropdown Menu`, you must encase the `Context Menu` or
`Dropdown Menu` component in the `Dialog` component. For more information, refer to the linked issue [here](https://github.com/radix-ui/primitives/issues/1836).

```tsx {14-25}
<Dialog>
  <ContextMenu>
    <ContextMenuTrigger>Right click</ContextMenuTrigger>
    <ContextMenuContent>
      <ContextMenuItem>Open</ContextMenuItem>
      <ContextMenuItem>Download</ContextMenuItem>
      <DialogTrigger asChild>
        <ContextMenuItem>
          <span>Delete</span>
        </ContextMenuItem>
      </DialogTrigger>
    </ContextMenuContent>
  </ContextMenu>
  <DialogContent>
    <DialogHeader>
      <DialogTitle>Are you absolutely sure?</DialogTitle>
      <DialogDescription>
        This action cannot be undone. Are you sure you want to permanently
        delete this file from our servers?
      </DialogDescription>
    </DialogHeader>
    <DialogFooter>
      <Button type="submit">Confirm</Button>
    </DialogFooter>
  </DialogContent>
</Dialog>
```

```

### 📄 components/drawer.mdx

```
---
title: Drawer
description: A drawer component for React.
component: true
links:
  doc: https://github.com/emilkowalski/vaul
---

<ComponentPreview name="drawer-demo" description="A drawer component." />

## About

Drawer is built on top of [Vaul](https://github.com/emilkowalski/vaul) by [emilkowalski\_](https://twitter.com/emilkowalski_).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add drawer
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install vaul
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="drawer" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx showLineNumbers
import {
  Drawer,
  DrawerClose,
  DrawerContent,
  DrawerDescription,
  DrawerFooter,
  DrawerHeader,
  DrawerTitle,
  DrawerTrigger,
} from "@/components/ui/drawer"
```

```tsx showLineNumbers
<Drawer>
  <DrawerTrigger>Open</DrawerTrigger>
  <DrawerContent>
    <DrawerHeader>
      <DrawerTitle>Are you absolutely sure?</DrawerTitle>
      <DrawerDescription>This action cannot be undone.</DrawerDescription>
    </DrawerHeader>
    <DrawerFooter>
      <Button>Submit</Button>
      <DrawerClose>
        <Button variant="outline">Cancel</Button>
      </DrawerClose>
    </DrawerFooter>
  </DrawerContent>
</Drawer>
```

## Examples

### Responsive Dialog

You can combine the `Dialog` and `Drawer` components to create a responsive dialog. This renders a `Dialog` component on desktop and a `Drawer` on mobile.

<ComponentPreview name="drawer-dialog" />

```

### 📄 components/dropdown-menu.mdx

```
---
title: Dropdown Menu
description: Displays a menu to the user — such as a set of actions or functions — triggered by a button.
featured: true
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/dropdown-menu
  api: https://www.radix-ui.com/docs/primitives/components/dropdown-menu#api-reference
---

<ComponentPreview
  name="dropdown-menu-demo"
  description="A dropdown menu with icons, shortcuts and sub menu items."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add dropdown-menu
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-dropdown-menu
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="dropdown-menu" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"
```

```tsx
<DropdownMenu>
  <DropdownMenuTrigger>Open</DropdownMenuTrigger>
  <DropdownMenuContent>
    <DropdownMenuLabel>My Account</DropdownMenuLabel>
    <DropdownMenuSeparator />
    <DropdownMenuItem>Profile</DropdownMenuItem>
    <DropdownMenuItem>Billing</DropdownMenuItem>
    <DropdownMenuItem>Team</DropdownMenuItem>
    <DropdownMenuItem>Subscription</DropdownMenuItem>
  </DropdownMenuContent>
</DropdownMenu>
```

## Examples

### Checkboxes

<ComponentPreview
  name="dropdown-menu-checkboxes"
  description="A dropdown menu with checkboxes."
/>

### Radio Group

<ComponentPreview
  name="dropdown-menu-radio-group"
  description="A dropdown menu with radio items."
/>

## Changelog

### 2024-10-16 Classes for icons

Added `gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0` to the `DropdownMenuItem` to automatically style icon inside the dropdown menu item.

Add the following classes to the `DropdownMenuItem` in your `dropdown-menu.tsx` file.

```diff showLineNumbers title="dropdown-menu.tsx"
const DropdownMenuItem = React.forwardRef<
  React.ElementRef<typeof DropdownMenuPrimitive.Item>,
  React.ComponentPropsWithoutRef<typeof DropdownMenuPrimitive.Item> & {
    inset?: boolean
  }
>(({ className, inset, ...props }, ref) => (
  <DropdownMenuPrimitive.Item
    ref={ref}
    className={cn(
      "relative ... gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0",
      inset && "pl-8",
      className
    )}
    {...props}
  />
))
```

### 2024-10-25 Classes for `<DropdownMenuSubTrigger />`

Added `gap-2 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0` to the `<DropdownMenuSubTrigger />` to automatically style icon inside.

Add the following classes to the `cva` call in your `dropdown-menu.tsx` file.

```tsx title="dropdown-menu.tsx"
<DropdownMenuPrimitive.SubTrigger
  ref={ref}
  className={cn(
    "flex cursor-default gap-2 select-none items-center rounded-sm px-2 py-1.5 text-sm outline-none focus:bg-accent data-[state=open]:bg-accent [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0",
    inset && "pl-8",
    className
  )}
  {...props}
>
  {/* ... */}
</DropdownMenuPrimitive.SubTrigger>
```

```

### 📄 components/form.mdx

```
---
title: React Hook Form
description: Building forms with React Hook Form and Zod.
links:
  doc: https://react-hook-form.com
---

Forms are tricky. They are one of the most common things you'll build in a web application, but also one of the most complex.

Well-designed HTML forms are:

- Well-structured and semantically correct.
- Easy to use and navigate (keyboard).
- Accessible with ARIA attributes and proper labels.
- Has support for client and server side validation.
- Well-styled and consistent with the rest of the application.

In this guide, we will take a look at building forms with [`react-hook-form`](https://react-hook-form.com/) and [`zod`](https://zod.dev). We're going to use a `<FormField>` component to compose accessible forms using Radix UI components.

## Features

The `<Form />` component is a wrapper around the `react-hook-form` library. It provides a few things:

- Composable components for building forms.
- A `<FormField />` component for building controlled form fields.
- Form validation using `zod`.
- Handles accessibility and error messages.
- Uses `React.useId()` for generating unique IDs.
- Applies the correct `aria` attributes to form fields based on states.
- Built to work with all Radix UI components.
- Bring your own schema library. We use `zod` but you can use anything you want.
- **You have full control over the markup and styling.**

## Anatomy

```tsx
<Form>
  <FormField
    control={...}
    name="..."
    render={() => (
      <FormItem>
        <FormLabel />
        <FormControl>
          { /* Your form field */}
        </FormControl>
        <FormDescription />
        <FormMessage />
      </FormItem>
    )}
  />
</Form>
```

## Example

```tsx
const form = useForm()

<FormField
  control={form.control}
  name="username"
  render={({ field }) => (
    <FormItem>
      <FormLabel>Username</FormLabel>
      <FormControl>
        <Input placeholder="shadcn" {...field} />
      </FormControl>
      <FormDescription>This is your public display name.</FormDescription>
      <FormMessage />
    </FormItem>
  )}
/>
```

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

### Command

```bash
npx shadcn@latest add form
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-label @radix-ui/react-slot react-hook-form @hookform/resolvers zod
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="form" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

<Steps>

### Create a form schema

Define the shape of your form using a Zod schema. You can read more about using Zod in the [Zod documentation](https://zod.dev).

```tsx showLineNumbers {3,5-7}
"use client"

import { z } from "zod"

const formSchema = z.object({
  username: z.string().min(2).max(50),
})
```

### Define a form

Use the `useForm` hook from `react-hook-form` to create a form.

```tsx showLineNumbers {3-4,14-20,22-27}
"use client"

import { zodResolver } from "@hookform/resolvers/zod"
import { useForm } from "react-hook-form"
import { z } from "zod"

const formSchema = z.object({
  username: z.string().min(2, {
    message: "Username must be at least 2 characters.",
  }),
})

export function ProfileForm() {
  // 1. Define your form.
  const form = useForm<z.infer<typeof formSchema>>({
    resolver: zodResolver(formSchema),
    defaultValues: {
      username: "",
    },
  })

  // 2. Define a submit handler.
  function onSubmit(values: z.infer<typeof formSchema>) {
    // Do something with the form values.
    // ✅ This will be type-safe and validated.
    console.log(values)
  }
}
```

Since `FormField` is using a controlled component, you need to provide a default value for the field. See the [React Hook Form docs](https://react-hook-form.com/docs/usecontroller) to learn more about controlled components.

### Build your form

We can now use the `<Form />` components to build our form.

```tsx showLineNumbers {7-17,28-50}
"use client"

import { zodResolver } from "@hookform/resolvers/zod"
import { useForm } from "react-hook-form"
import { z } from "zod"

import { Button } from "@/components/ui/button"
import {
  Form,
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form"
import { Input } from "@/components/ui/input"

const formSchema = z.object({
  username: z.string().min(2, {
    message: "Username must be at least 2 characters.",
  }),
})

export function ProfileForm() {
  // ...

  return (
    <Form {...form}>
      <form onSubmit={form.handleSubmit(onSubmit)} className="space-y-8">
        <FormField
          control={form.control}
          name="username"
          render={({ field }) => (
            <FormItem>
              <FormLabel>Username</FormLabel>
              <FormControl>
                <Input placeholder="shadcn" {...field} />
              </FormControl>
              <FormDescription>
                This is your public display name.
              </FormDescription>
              <FormMessage />
            </FormItem>
          )}
        />
        <Button type="submit">Submit</Button>
      </form>
    </Form>
  )
}
```

### Done

That's it. You now have a fully accessible form that is type-safe with client-side validation.

<ComponentPreview
  name="input-form"
  className="[&_[role=tablist]]:hidden [&>div>div:first-child]:hidden"
/>

</Steps>

## Examples

See the following links for more examples on how to use the `<Form />` component with other components:

- [Checkbox](/docs/components/checkbox#form)
- [Date Picker](/docs/components/date-picker#form)
- [Input](/docs/components/input#form)
- [Radio Group](/docs/components/radio-group#form)
- [Select](/docs/components/select#form)
- [Switch](/docs/components/switch#form)
- [Textarea](/docs/components/textarea#form)
- [Combobox](/docs/components/combobox#form)

```

### 📄 components/hover-card.mdx

```
---
title: Hover Card
description: For sighted users to preview content available behind a link.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/hover-card
  api: https://www.radix-ui.com/docs/primitives/components/hover-card#api-reference
---

<ComponentPreview name="hover-card-demo" description="A hover card component" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add hover-card
```

</TabsContent>

<TabsContent value="manual">

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-hover-card
```

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="hover-card" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  HoverCard,
  HoverCardContent,
  HoverCardTrigger,
} from "@/components/ui/hover-card"
```

```tsx
<HoverCard>
  <HoverCardTrigger>Hover</HoverCardTrigger>
  <HoverCardContent>
    The React Framework – created and maintained by @vercel.
  </HoverCardContent>
</HoverCard>
```

```

### 📄 components/input-otp.mdx

```
---
title: Input OTP
description: Accessible one-time password component with copy paste functionality.
component: true
links:
  doc: https://input-otp.rodz.dev
---

<ComponentPreview name="input-otp-demo" description="An 6 digits input OTP." />

## About

Input OTP is built on top of [input-otp](https://github.com/guilhermerodz/input-otp) by [@guilherme_rodz](https://twitter.com/guilherme_rodz).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

<Step>Run the following command:</Step>

```bash
npx shadcn@latest add input-otp
```

<Step>Update `tailwind.config.js`</Step>

Add the following animations to your `tailwind.config.js` file:

```js showLineNumbers title="tailwind.config.js" {6-9,12}
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      keyframes: {
        "caret-blink": {
          "0%,70%,100%": { opacity: "1" },
          "20%,50%": { opacity: "0" },
        },
      },
      animation: {
        "caret-blink": "caret-blink 1.25s ease-out infinite",
      },
    },
  },
}
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install input-otp
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="input-otp" />

<Step>Update the import paths to match your project setup.</Step>

<Step>Update `tailwind.config.js`</Step>

Add the following animations to your `tailwind.config.js` file:

```js showLineNumbers title="tailwind.config.js" {6-9,12}
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      keyframes: {
        "caret-blink": {
          "0%,70%,100%": { opacity: "1" },
          "20%,50%": { opacity: "0" },
        },
      },
      animation: {
        "caret-blink": "caret-blink 1.25s ease-out infinite",
      },
    },
  },
}
```

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  InputOTP,
  InputOTPGroup,
  InputOTPSeparator,
  InputOTPSlot,
} from "@/components/ui/input-otp"
```

```tsx
<InputOTP maxLength={6}>
  <InputOTPGroup>
    <InputOTPSlot index={0} />
    <InputOTPSlot index={1} />
    <InputOTPSlot index={2} />
  </InputOTPGroup>
  <InputOTPSeparator />
  <InputOTPGroup>
    <InputOTPSlot index={3} />
    <InputOTPSlot index={4} />
    <InputOTPSlot index={5} />
  </InputOTPGroup>
</InputOTP>
```

## Examples

### Pattern

Use the `pattern` prop to define a custom pattern for the OTP input.

<ComponentPreview
  name="input-otp-pattern"
  description="An input OTP with alphanumeric pattern."
/>

```tsx showLineNumbers {1,7}
import { REGEXP_ONLY_DIGITS_AND_CHARS } from "input-otp"

...

<InputOTP
  maxLength={6}
  pattern={REGEXP_ONLY_DIGITS_AND_CHARS}
>
  <InputOTPGroup>
    <InputOTPSlot index={0} />
    {/* ... */}
  </InputOTPGroup>
</InputOTP>
```

### Separator

You can use the `<InputOTPSeparator />` component to add a separator between the input groups.

<ComponentPreview
  name="input-otp-separator"
  description="An input OTP with custom separator."
/>

```tsx showLineNumbers {4,15}
import {
  InputOTP,
  InputOTPGroup,
  InputOTPSeparator,
  InputOTPSlot,
} from "@/components/ui/input-otp"

...

<InputOTP maxLength={4}>
  <InputOTPGroup>
    <InputOTPSlot index={0} />
    <InputOTPSlot index={1} />
  </InputOTPGroup>
  <InputOTPSeparator />
  <InputOTPGroup>
    <InputOTPSlot index={2} />
    <InputOTPSlot index={3} />
  </InputOTPGroup>
</InputOTP>
```

### Controlled

You can use the `value` and `onChange` props to control the input value.

<ComponentPreview name="input-otp-controlled" />

### Form

<ComponentPreview name="input-otp-form" />

## Changelog

### 2024-03-19 Composition

We've made some updates and replaced the render props pattern with composition. Here's how to update your code if you prefer the composition pattern.

<Callout className="mt-6">
  **Note:** You are not required to update your code if you are using the
  `render` prop. It is still supported.
</Callout>

<Steps>

<Step>Update to the latest version of `input-otp`.</Step>

```bash
npm install input-otp@latest
```

<Step>Update `input-otp.tsx`</Step>

```diff showLineNumbers title="input-otp.tsx" {2,8-11}
- import { OTPInput, SlotProps } from "input-otp"
+ import { OTPInput, OTPInputContext } from "input-otp"

 const InputOTPSlot = React.forwardRef<
   React.ElementRef<"div">,
-   SlotProps & React.ComponentPropsWithoutRef<"div">
-  >(({ char, hasFakeCaret, isActive, className, ...props }, ref) => {
+   React.ComponentPropsWithoutRef<"div"> & { index: number }
+  >(({ index, className, ...props }, ref) => {
+   const inputOTPContext = React.useContext(OTPInputContext)
+   const { char, hasFakeCaret, isActive } = inputOTPContext.slots[index]
```

<Step>Then replace the `render` prop in your code.</Step>

```diff showLineNumbers {2-12}
<InputOTP maxLength={6}>
  <InputOTPGroup>
    <InputOTPSlot index={0} />
    <InputOTPSlot index={1} />
    <InputOTPSlot index={2} />
  </InputOTPGroup>
  <InputOTPSeparator />
  <InputOTPGroup>
    <InputOTPSlot index={3} />
    <InputOTPSlot index={4} />
    <InputOTPSlot index={5} />
  </InputOTPGroup>
</InputOTP>
```

</Steps>

### 2024-03-19 Disabled

To add a disabled state to the input, update `<InputOTP />` as follows:

```tsx showLineNumbers title="input-otp.tsx" {4,7-11}
const InputOTP = React.forwardRef<
  React.ElementRef<typeof OTPInput>,
  React.ComponentPropsWithoutRef<typeof OTPInput>
>(({ className, containerClassName, ...props }, ref) => (
  <OTPInput
    ref={ref}
    containerClassName={cn(
      "flex items-center gap-2 has-[:disabled]:opacity-50",
      containerClassName
    )}
    className={cn("disabled:cursor-not-allowed", className)}
    {...props}
  />
))
InputOTP.displayName = "InputOTP"
```

```

### 📄 components/input.mdx

```
---
title: Input
description: Displays a form input field or a component that looks like an input field.
component: true
---

<ComponentPreview
  name="input-demo"
  className="[&_input]:max-w-xs"
  description="A form input component."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add input
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="input" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Input } from "@/components/ui/input"
```

```tsx
<Input />
```

## Examples

### Default

<ComponentPreview
  name="input-demo"
  className="[&_input]:max-w-xs"
  description="A form input component."
/>

### File

<ComponentPreview
  name="input-file"
  className="[&_input]:max-w-xs"
  description="A file input component."
/>

### Disabled

<ComponentPreview
  name="input-disabled"
  className="[&_input]:max-w-xs"
  description="A disabled input component."
/>

### With Label

<ComponentPreview
  name="input-with-label"
  className="[&_input]:max-w-xs"
  description="An input component with a label."
/>

### With Button

<ComponentPreview
  name="input-with-button"
  className="[&_input]:max-w-xs"
  description="An input component with a button."
/>

### Form

<ComponentPreview name="input-form" />

```

### 📄 components/label.mdx

```
---
title: Label
description: Renders an accessible label associated with controls.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/label
  api: https://www.radix-ui.com/docs/primitives/components/label#api-reference
---

<ComponentPreview name="label-demo" description="A label" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add label
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-label
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="label" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Label } from "@/components/ui/label"
```

```tsx
<Label htmlFor="email">Your email address</Label>
```

```

### 📄 components/menubar.mdx

```
---
title: Menubar
description: A visually persistent menu common in desktop applications that provides quick access to a consistent set of commands.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/menubar
  api: https://www.radix-ui.com/docs/primitives/components/menubar#api-reference
---

<ComponentPreview name="menubar-demo" description="A menubar component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add menubar
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-menubar
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="menubar" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Menubar,
  MenubarContent,
  MenubarItem,
  MenubarMenu,
  MenubarSeparator,
  MenubarShortcut,
  MenubarTrigger,
} from "@/components/ui/menubar"
```

```tsx
<Menubar>
  <MenubarMenu>
    <MenubarTrigger>File</MenubarTrigger>
    <MenubarContent>
      <MenubarItem>
        New Tab <MenubarShortcut>⌘T</MenubarShortcut>
      </MenubarItem>
      <MenubarItem>New Window</MenubarItem>
      <MenubarSeparator />
      <MenubarItem>Share</MenubarItem>
      <MenubarSeparator />
      <MenubarItem>Print</MenubarItem>
    </MenubarContent>
  </MenubarMenu>
</Menubar>
```

```

### 📄 components/navigation-menu.mdx

```
---
title: Navigation Menu
description: A collection of links for navigating websites.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/navigation-menu
  api: https://www.radix-ui.com/docs/primitives/components/navigation-menu#api-reference
---

<ComponentPreview name="navigation-menu-demo" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add navigation-menu
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-navigation-menu
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="navigation-menu" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuIndicator,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  NavigationMenuViewport,
} from "@/components/ui/navigation-menu"
```

```tsx
<NavigationMenu>
  <NavigationMenuList>
    <NavigationMenuItem>
      <NavigationMenuTrigger>Item One</NavigationMenuTrigger>
      <NavigationMenuContent>
        <NavigationMenuLink>Link</NavigationMenuLink>
      </NavigationMenuContent>
    </NavigationMenuItem>
  </NavigationMenuList>
</NavigationMenu>
```

## Examples

### Link Component

When using the Next.js `<Link />` component, you can use `navigationMenuTriggerStyle()` to apply the correct styles to the trigger.

```tsx
import { navigationMenuTriggerStyle } from "@/components/ui/navigation-menu"
```

```tsx {3-5}
<NavigationMenuItem>
  <Link href="/docs" legacyBehavior passHref>
    <NavigationMenuLink className={navigationMenuTriggerStyle()}>
      Documentation
    </NavigationMenuLink>
  </Link>
</NavigationMenuItem>
```

See also the [Radix UI documentation](https://www.radix-ui.com/docs/primitives/components/navigation-menu#with-client-side-routing) for handling client side routing.

```

### 📄 components/pagination.mdx

```
---
title: Pagination
description: Pagination with page navigation, next and previous links.
component: true
---

<ComponentPreview
  name="pagination-demo"
  description="A pagination with previous and next links."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add pagination
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="pagination" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Pagination,
  PaginationContent,
  PaginationEllipsis,
  PaginationItem,
  PaginationLink,
  PaginationNext,
  PaginationPrevious,
} from "@/components/ui/pagination"
```

```tsx
<Pagination>
  <PaginationContent>
    <PaginationItem>
      <PaginationPrevious href="#" />
    </PaginationItem>
    <PaginationItem>
      <PaginationLink href="#">1</PaginationLink>
    </PaginationItem>
    <PaginationItem>
      <PaginationEllipsis />
    </PaginationItem>
    <PaginationItem>
      <PaginationNext href="#" />
    </PaginationItem>
  </PaginationContent>
</Pagination>
```

### Next.js

By default the `<PaginationLink />` component will render an `<a />` tag.

To use the Next.js `<Link />` component, make the following updates to `pagination.tsx`.

```diff showLineNumbers /typeof Link/ {1}
+ import Link from "next/link"

- type PaginationLinkProps = ... & React.ComponentProps<"a">
+ type PaginationLinkProps = ... & React.ComponentProps<typeof Link>

const PaginationLink = ({...props }: ) => (
  <PaginationItem>
-   <a>
+   <Link>
      // ...
-   </a>
+   </Link>
  </PaginationItem>
)

```

<Callout className="mt-6">

**Note:** We are making updates to the cli to automatically do this for you.

</Callout>

```

### 📄 components/popover.mdx

```
---
title: Popover
description: Displays rich content in a portal, triggered by a button.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/popover
  api: https://www.radix-ui.com/docs/primitives/components/popover#api-reference
---

<ComponentPreview
  name="popover-demo"
  description="A popover component with a form."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add popover
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-popover
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="popover" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"
```

```tsx
<Popover>
  <PopoverTrigger>Open</PopoverTrigger>
  <PopoverContent>Place content for the popover here.</PopoverContent>
</Popover>
```

```

### 📄 components/progress.mdx

```
---
title: Progress
description: Displays an indicator showing the completion progress of a task, typically displayed as a progress bar.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/progress
  api: https://www.radix-ui.com/docs/primitives/components/progress#api-reference
---

<ComponentPreview
  name="progress-demo"
  description="A progress bar component."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add progress
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-progress
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="progress" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Progress } from "@/components/ui/progress"
```

```tsx
<Progress value={33} />
```

```

### 📄 components/radio-group.mdx

```
---
title: Radio Group
description: A set of checkable buttons—known as radio buttons—where no more than one of the buttons can be checked at a time.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/radio-group
  api: https://www.radix-ui.com/docs/primitives/components/radio-group#api-reference
---

<ComponentPreview
  name="radio-group-demo"
  description="A radio group with 3 items."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add radio-group
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-radio-group
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="radio-group" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Label } from "@/components/ui/label"
import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group"
```

```tsx
<RadioGroup defaultValue="option-one">
  <div className="flex items-center space-x-2">
    <RadioGroupItem value="option-one" id="option-one" />
    <Label htmlFor="option-one">Option One</Label>
  </div>
  <div className="flex items-center space-x-2">
    <RadioGroupItem value="option-two" id="option-two" />
    <Label htmlFor="option-two">Option Two</Label>
  </div>
</RadioGroup>
```

## Examples

### Form

<ComponentPreview name="radio-group-form" />

```

### 📄 components/resizable.mdx

```
---
title: Resizable
description: Accessible resizable panel groups and layouts with keyboard support.
component: true
links:
  doc: https://github.com/bvaughn/react-resizable-panels
  api: https://github.com/bvaughn/react-resizable-panels/tree/main/packages/react-resizable-panels
---

<ComponentPreview
  name="resizable-demo"
  description="A group of resizable horizontal and vertical panels."
/>

## About

The `Resizable` component is built on top of [react-resizable-panels](https://github.com/bvaughn/react-resizable-panels) by [bvaughn](https://github.com/bvaughn).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add resizable
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install react-resizable-panels
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="resizable" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  ResizableHandle,
  ResizablePanel,
  ResizablePanelGroup,
} from "@/components/ui/resizable"
```

```tsx
<ResizablePanelGroup direction="horizontal">
  <ResizablePanel>One</ResizablePanel>
  <ResizableHandle />
  <ResizablePanel>Two</ResizablePanel>
</ResizablePanelGroup>
```

## Examples

### Vertical

Use the `direction` prop to set the direction of the resizable panels.

<ComponentPreview
  name="resizable-vertical"
  description="A group of resizable vertical panels."
/>

```tsx showLineNumbers {9}
import {
  ResizableHandle,
  ResizablePanel,
  ResizablePanelGroup,
} from "@/components/ui/resizable"

export default function Example() {
  return (
    <ResizablePanelGroup direction="vertical">
      <ResizablePanel>One</ResizablePanel>
      <ResizableHandle />
      <ResizablePanel>Two</ResizablePanel>
    </ResizablePanelGroup>
  )
}
```

### Handle

You can set or hide the handle by using the `withHandle` prop on the `ResizableHandle` component.

<ComponentPreview
  name="resizable-handle"
  description="A group of resizable panels with a handle."
/>

```tsx showLineNumbers {11}
import {
  ResizableHandle,
  ResizablePanel,
  ResizablePanelGroup,
} from "@/components/ui/resizable"

export default function Example() {
  return (
    <ResizablePanelGroup direction="horizontal">
      <ResizablePanel>One</ResizablePanel>
      <ResizableHandle withHandle />
      <ResizablePanel>Two</ResizablePanel>
    </ResizablePanelGroup>
  )
}
```

```

### 📄 components/scroll-area.mdx

```
---
title: Scroll-area
description: Augments native scroll functionality for custom, cross-browser styling.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/scroll-area
  api: https://www.radix-ui.com/docs/primitives/components/scroll-area#api-reference
---

<ComponentPreview
  name="scroll-area-demo"
  description="A scroll area component."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add scroll-area
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-scroll-area
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="scroll-area" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { ScrollArea } from "@/components/ui/scroll-area"
```

```tsx
<ScrollArea className="h-[200px] w-[350px] rounded-md border p-4">
  Jokester began sneaking into the castle in the middle of the night and leaving
  jokes all over the place: under the king's pillow, in his soup, even in the
  royal toilet. The king was furious, but he couldn't seem to stop Jokester. And
  then, one day, the people of the kingdom discovered that the jokes left by
  Jokester were so funny that they couldn't help but laugh. And once they
  started laughing, they couldn't stop.
</ScrollArea>
```

## Examples

### Horizontal Scrolling

<ComponentPreview name="scroll-area-horizontal-demo" />

```

### 📄 components/select.mdx

```
---
title: Select
description: Displays a list of options for the user to pick from—triggered by a button.
component: true
featured: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/select
  api: https://www.radix-ui.com/docs/primitives/components/select#api-reference
---

<ComponentPreview
  name="select-demo"
  description="A select component with a list of options."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add select
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-select
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="select" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Select,
  SelectContent,
  SelectItem,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select"
```

```tsx
<Select>
  <SelectTrigger className="w-[180px]">
    <SelectValue placeholder="Theme" />
  </SelectTrigger>
  <SelectContent>
    <SelectItem value="light">Light</SelectItem>
    <SelectItem value="dark">Dark</SelectItem>
    <SelectItem value="system">System</SelectItem>
  </SelectContent>
</Select>
```

## Examples

### Scrollable

<ComponentPreview
  name="select-scrollable"
  description="A select component with a scrollable list of options."
/>

### Form

<ComponentPreview name="select-form" />

```

### 📄 components/separator.mdx

```
---
title: Separator
description: Visually or semantically separates content.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/separator
  api: https://www.radix-ui.com/docs/primitives/components/separator#api-reference
---

<ComponentPreview name="separator-demo" description="A separator component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add separator
```

</TabsContent>

<TabsContent value="manual">

<Steps>
<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-separator
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="separator" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Separator } from "@/components/ui/separator"
```

```tsx
<Separator />
```

```

### 📄 components/sheet.mdx

```
---
title: Sheet
description: Extends the Dialog component to display content that complements the main content of the screen.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/dialog
  api: https://www.radix-ui.com/docs/primitives/components/dialog#api-reference
---

<ComponentPreview name="sheet-demo" description="A sheet component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add sheet
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-dialog
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="sheet" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

### Usage

```tsx
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet"
```

```tsx
<Sheet>
  <SheetTrigger>Open</SheetTrigger>
  <SheetContent>
    <SheetHeader>
      <SheetTitle>Are you absolutely sure?</SheetTitle>
      <SheetDescription>
        This action cannot be undone. This will permanently delete your account
        and remove your data from our servers.
      </SheetDescription>
    </SheetHeader>
  </SheetContent>
</Sheet>
```

## Examples

### Side

Use the `side` property to `<SheetContent />` to indicate the edge of the screen where the component will appear. The values can be `top`, `right`, `bottom` or `left`.

<ComponentPreview name="sheet-side" />

### Size

You can adjust the size of the sheet using CSS classes:

```tsx {3}
<Sheet>
  <SheetTrigger>Open</SheetTrigger>
  <SheetContent className="w-[400px] sm:w-[540px]">
    <SheetHeader>
      <SheetTitle>Are you absolutely sure?</SheetTitle>
      <SheetDescription>
        This action cannot be undone. This will permanently delete your account
        and remove your data from our servers.
      </SheetDescription>
    </SheetHeader>
  </SheetContent>
</Sheet>
```

```

### 📄 components/sidebar.mdx

```
---
title: Sidebar
description: A composable, themeable and customizable sidebar component.
component: true
---

<figure className="flex flex-col gap-4">
  <ComponentPreview
    name="sidebar-07"
    title="Sidebar"
    type="block"
    description="A composable, themeable and customizable sidebar component built using shadcn/ui"
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar that collapses to icons.
  </figcaption>
</figure>

Sidebars are one of the most complex components to build. They are central
to any application and often contain a lot of moving parts.

I don't like building sidebars. So I built 30+ of them. All kinds of
configurations. Then I extracted the core components into `sidebar.tsx`.

We now have a solid foundation to build on top of. Composable. Themeable.
Customizable.

[Browse the Blocks Library](/blocks).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

<Step>Run the following command to install `sidebar.tsx`</Step>

```bash
npx shadcn@latest add sidebar
```

<Step>Add the following colors to your CSS file</Step>

The command above should install the colors for you. If not, copy and paste the following in your CSS file.

We'll go over the colors later in the [theming section](/docs/components/sidebar#theming).

```css title="app/globals.css"
@layer base {
  :root {
    --sidebar-background: 0 0% 98%;
    --sidebar-foreground: 240 5.3% 26.1%;
    --sidebar-primary: 240 5.9% 10%;
    --sidebar-primary-foreground: 0 0% 98%;
    --sidebar-accent: 240 4.8% 95.9%;
    --sidebar-accent-foreground: 240 5.9% 10%;
    --sidebar-border: 220 13% 91%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }

  .dark {
    --sidebar-background: 240 5.9% 10%;
    --sidebar-foreground: 240 4.8% 95.9%;
    --sidebar-primary: 224.3 76.3% 48%;
    --sidebar-primary-foreground: 0 0% 100%;
    --sidebar-accent: 240 3.7% 15.9%;
    --sidebar-accent-foreground: 240 4.8% 95.9%;
    --sidebar-border: 240 3.7% 15.9%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }
}
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="sidebar" />

<Step>Update the import paths to match your project setup.</Step>

<Step>Add the following colors to your CSS file</Step>

We'll go over the colors later in the [theming section](/docs/components/sidebar#theming).

```css title="app/globals.css"
@layer base {
  :root {
    --sidebar-background: 0 0% 98%;
    --sidebar-foreground: 240 5.3% 26.1%;
    --sidebar-primary: 240 5.9% 10%;
    --sidebar-primary-foreground: 0 0% 98%;
    --sidebar-accent: 240 4.8% 95.9%;
    --sidebar-accent-foreground: 240 5.9% 10%;
    --sidebar-border: 220 13% 91%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }

  .dark {
    --sidebar-background: 240 5.9% 10%;
    --sidebar-foreground: 240 4.8% 95.9%;
    --sidebar-primary: 224.3 76.3% 48%;
    --sidebar-primary-foreground: 0 0% 100%;
    --sidebar-accent: 240 3.7% 15.9%;
    --sidebar-accent-foreground: 240 4.8% 95.9%;
    --sidebar-border: 240 3.7% 15.9%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }
}
```

<Step>Add the Sidebar tailwind config into `tailwind.config.js`</Step>

Add the following object in the `theme.extend.colors` section of your `tailwind.config.js` file
this config enable sidebar related style utilities like bg-sidebar

```javascript title="tailwind.config.js"
// ...
sidebar: {
  DEFAULT: 'hsl(var(--sidebar-background))',
  foreground: 'hsl(var(--sidebar-foreground))',
  primary: 'hsl(var(--sidebar-primary))',
  'primary-foreground': 'hsl(var(--sidebar-primary-foreground))',
  accent: 'hsl(var(--sidebar-accent))',
  'accent-foreground': 'hsl(var(--sidebar-accent-foreground))',
  border: 'hsl(var(--sidebar-border))',
  ring: 'hsl(var(--sidebar-ring))',
},
// ...
```

</Steps>

</TabsContent>

</Tabs>

## Structure

A `Sidebar` component is composed of the following parts:

- `SidebarProvider` - Handles collapsible state.
- `Sidebar` - The sidebar container.
- `SidebarHeader` and `SidebarFooter` - Sticky at the top and bottom of the sidebar.
- `SidebarContent` - Scrollable content.
- `SidebarGroup` - Section within the `SidebarContent`.
- `SidebarTrigger` - Trigger for the `Sidebar`.

<Image
  src="/images/sidebar-structure.png"
  width="716"
  height="420"
  alt="Sidebar Structure"
  className="border dark:hidden rounded-lg overflow-hidden mt-6 w-full"
/>
<Image
  src="/images/sidebar-structure-dark.png"
  width="716"
  height="420"
  alt="Sidebar Structure"
  className="border hidden dark:block rounded-lg overflow-hidden mt-6 w-full"
/>

## Usage

```tsx showLineNumbers title="app/layout.tsx"
import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar"
import { AppSidebar } from "@/components/app-sidebar"

export default function Layout({ children }: { children: React.ReactNode }) {
  return (
    <SidebarProvider>
      <AppSidebar />
      <main>
        <SidebarTrigger />
        {children}
      </main>
    </SidebarProvider>
  )
}
```

```tsx showLineNumbers title="components/app-sidebar.tsx"
import {
  Sidebar,
  SidebarContent,
  SidebarFooter,
  SidebarGroup,
  SidebarHeader,
} from "@/components/ui/sidebar"

export function AppSidebar() {
  return (
    <Sidebar>
      <SidebarHeader />
      <SidebarContent>
        <SidebarGroup />
        <SidebarGroup />
      </SidebarContent>
      <SidebarFooter />
    </Sidebar>
  )
}
```

## Your First Sidebar

Let's start with the most basic sidebar. A collapsible sidebar with a menu.

<Steps>

<Step>
  Add a `SidebarProvider` and `SidebarTrigger` at the root of your application.
</Step>

```tsx showLineNumbers title="app/layout.tsx"
import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar"
import { AppSidebar } from "@/components/app-sidebar"

export default function Layout({ children }: { children: React.ReactNode }) {
  return (
    <SidebarProvider>
      <AppSidebar />
      <main>
        <SidebarTrigger />
        {children}
      </main>
    </SidebarProvider>
  )
}
```

<Step>Create a new sidebar component at `components/app-sidebar.tsx`.</Step>

```tsx showLineNumbers title="components/app-sidebar.tsx"
import { Sidebar, SidebarContent } from "@/components/ui/sidebar"

export function AppSidebar() {
  return (
    <Sidebar>
      <SidebarContent />
    </Sidebar>
  )
}
```

<Step>Now, let's add a `SidebarMenu` to the sidebar.</Step>

We'll use the `SidebarMenu` component in a `SidebarGroup`.

```tsx showLineNumbers title="components/app-sidebar.tsx"
import { Calendar, Home, Inbox, Search, Settings } from "lucide-react"

import {
  Sidebar,
  SidebarContent,
  SidebarGroup,
  SidebarGroupContent,
  SidebarGroupLabel,
  SidebarMenu,
  SidebarMenuButton,
  SidebarMenuItem,
} from "@/components/ui/sidebar"

// Menu items.
const items = [
  {
    title: "Home",
    url: "#",
    icon: Home,
  },
  {
    title: "Inbox",
    url: "#",
    icon: Inbox,
  },
  {
    title: "Calendar",
    url: "#",
    icon: Calendar,
  },
  {
    title: "Search",
    url: "#",
    icon: Search,
  },
  {
    title: "Settings",
    url: "#",
    icon: Settings,
  },
]

export function AppSidebar() {
  return (
    <Sidebar>
      <SidebarContent>
        <SidebarGroup>
          <SidebarGroupLabel>Application</SidebarGroupLabel>
          <SidebarGroupContent>
            <SidebarMenu>
              {items.map((item) => (
                <SidebarMenuItem key={item.title}>
                  <SidebarMenuButton asChild>
                    <a href={item.url}>
                      <item.icon />
                      <span>{item.title}</span>
                    </a>
                  </SidebarMenuButton>
                </SidebarMenuItem>
              ))}
            </SidebarMenu>
          </SidebarGroupContent>
        </SidebarGroup>
      </SidebarContent>
    </Sidebar>
  )
}
```

<Step>You've created your first sidebar.</Step>

<figure className="flex flex-col gap-4">
  <ComponentPreview
    name="sidebar-demo"
    title="Sidebar"
    type="block"
    description="Your first sidebar."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    Your first sidebar.
  </figcaption>
</figure>

</Steps>

## Components

The components in `sidebar.tsx` are built to be composable i.e you build your sidebar by putting the provided components together. They also compose well with other shadcn/ui components such as `DropdownMenu`, `Collapsible` or `Dialog` etc.

**If you need to change the code in `sidebar.tsx`, you are encouraged to do so. The code is yours. Use `sidebar.tsx` as a starting point and build your own.**

In the next sections, we'll go over each component and how to use them.

## SidebarProvider

The `SidebarProvider` component is used to provide the sidebar context to the `Sidebar` component. You should always wrap your application in a `SidebarProvider` component.

### Props

| Name           | Type                      | Description                                  |
| -------------- | ------------------------- | -------------------------------------------- |
| `defaultOpen`  | `boolean`                 | Default open state of the sidebar.           |
| `open`         | `boolean`                 | Open state of the sidebar (controlled).      |
| `onOpenChange` | `(open: boolean) => void` | Sets open state of the sidebar (controlled). |

### Width

If you have a single sidebar in your application, you can use the `SIDEBAR_WIDTH` and `SIDEBAR_WIDTH_MOBILE` variables in `sidebar.tsx` to set the width of the sidebar.

```tsx showLineNumbers title="components/ui/sidebar.tsx"
const SIDEBAR_WIDTH = "16rem"
const SIDEBAR_WIDTH_MOBILE = "18rem"
```

For multiple sidebars in your application, you can use the `style` prop to set the width of the sidebar.

To set the width of the sidebar, you can use the `--sidebar-width` and `--sidebar-width-mobile` CSS variables in the `style` prop.

```tsx showLineNumbers title="components/ui/sidebar.tsx"
<SidebarProvider
  style={{
    "--sidebar-width": "20rem",
    "--sidebar-width-mobile": "20rem",
  }}
>
  <Sidebar />
</SidebarProvider>
```

This will handle the width of the sidebar but also the layout spacing.

### Keyboard Shortcut

The `SIDEBAR_KEYBOARD_SHORTCUT` variable is used to set the keyboard shortcut used to open and close the sidebar.

To trigger the sidebar, you use the `cmd+b` keyboard shortcut on Mac and `ctrl+b` on Windows.

You can change the keyboard shortcut by updating the `SIDEBAR_KEYBOARD_SHORTCUT` variable.

```tsx showLineNumbers title="components/ui/sidebar.tsx"
const SIDEBAR_KEYBOARD_SHORTCUT = "b"
```

### Persisted State

The `SidebarProvider` supports persisting the sidebar state across page reloads and server-side rendering. It uses cookies to store the current state of the sidebar. When the sidebar state changes, a default cookie named `sidebar:state` is set with the current open/closed state. This cookie is then read on subsequent page loads to restore the sidebar state.

To persist sidebar state in Next.js, set up your `SidebarProvider` in `app/layout.tsx` like this:

```tsx showLineNumbers title="app/layout.tsx"
import { cookies } from "next/headers"

import { SidebarProvider, SidebarTrigger } from "@/components/ui/sidebar"
import { AppSidebar } from "@/components/app-sidebar"

export async function Layout({ children }: { children: React.ReactNode }) {
  const cookieStore = await cookies()
  const defaultOpen = cookieStore.get("sidebar:state")?.value === "true"

  return (
    <SidebarProvider defaultOpen={defaultOpen}>
      <AppSidebar />
      <main>
        <SidebarTrigger />
        {children}
      </main>
    </SidebarProvider>
  )
}
```

You can change the name of the cookie by updating the `SIDEBAR_COOKIE_NAME` variable in `sidebar.tsx`.

```tsx showLineNumbers title="components/ui/sidebar.tsx"
const SIDEBAR_COOKIE_NAME = "sidebar:state"
```

## Sidebar

The main `Sidebar` component used to render a collapsible sidebar.

```tsx showLineNumbers
import { Sidebar } from "@/components/ui/sidebar"

export function AppSidebar() {
  return <Sidebar />
}
```

### Props

| Property      | Type                              | Description                       |
| ------------- | --------------------------------- | --------------------------------- |
| `side`        | `left` or `right`                 | The side of the sidebar.          |
| `variant`     | `sidebar`, `floating`, or `inset` | The variant of the sidebar.       |
| `collapsible` | `offcanvas`, `icon`, or `none`    | Collapsible state of the sidebar. |

### side

Use the `side` prop to change the side of the sidebar.

Available options are `left` and `right`.

```tsx showLineNumbers
import { Sidebar } from "@/components/ui/sidebar"

export function AppSidebar() {
  return <Sidebar side="left | right" />
}
```

### variant

Use the `variant` prop to change the variant of the sidebar.

Available options are `sidebar`, `floating` and `inset`.

```tsx showLineNumbers
import { Sidebar } from "@/components/ui/sidebar"

export function AppSidebar() {
  return <Sidebar variant="sidebar | floating | inset" />
}
```

<Callout>
  **Note:** If you use the `inset` variant, remember to wrap your main content
  in a `SidebarInset` component.
</Callout>

```tsx showLineNumbers
<SidebarProvider>
  <Sidebar variant="inset" />
  <SidebarInset>
    <main>{children}</main>
  </SidebarInset>
</SidebarProvider>
```

### collapsible

Use the `collapsible` prop to make the sidebar collapsible.

Available options are `offcanvas`, `icon` and `none`.

```tsx showLineNumbers
import { Sidebar } from "@/components/ui/sidebar"

export function AppSidebar() {
  return <Sidebar collapsible="offcanvas | icon | none" />
}
```

| Prop        | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| `offcanvas` | A collapsible sidebar that slides in from the left or right. |
| `icon`      | A sidebar that collapses to icons.                           |
| `none`      | A non-collapsible sidebar.                                   |

## useSidebar

The `useSidebar` hook is used to control the sidebar.

```tsx showLineNumbers
import { useSidebar } from "@/components/ui/sidebar"

export function AppSidebar() {
  const {
    state,
    open,
    setOpen,
    openMobile,
    setOpenMobile,
    isMobile,
    toggleSidebar,
  } = useSidebar()
}
```

| Property        | Type                      | Description                                   |
| --------------- | ------------------------- | --------------------------------------------- |
| `state`         | `expanded` or `collapsed` | The current state of the sidebar.             |
| `open`          | `boolean`                 | Whether the sidebar is open.                  |
| `setOpen`       | `(open: boolean) => void` | Sets the open state of the sidebar.           |
| `openMobile`    | `boolean`                 | Whether the sidebar is open on mobile.        |
| `setOpenMobile` | `(open: boolean) => void` | Sets the open state of the sidebar on mobile. |
| `isMobile`      | `boolean`                 | Whether the sidebar is on mobile.             |
| `toggleSidebar` | `() => void`              | Toggles the sidebar. Desktop and mobile.      |

## SidebarHeader

Use the `SidebarHeader` component to add a sticky header to the sidebar.

The following example adds a `<DropdownMenu>` to the `SidebarHeader`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-header"
    title="Sidebar"
    type="block"
    description="A sidebar header with a dropdown menu."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar header with a dropdown menu.
  </figcaption>
</figure>

```tsx showLineNumbers title="components/app-sidebar.tsx"
<Sidebar>
  <SidebarHeader>
    <SidebarMenu>
      <SidebarMenuItem>
        <DropdownMenu>
          <DropdownMenuTrigger asChild>
            <SidebarMenuButton>
              Select Workspace
              <ChevronDown className="ml-auto" />
            </SidebarMenuButton>
          </DropdownMenuTrigger>
          <DropdownMenuContent className="w-[--radix-popper-anchor-width]">
            <DropdownMenuItem>
              <span>Acme Inc</span>
            </DropdownMenuItem>
            <DropdownMenuItem>
              <span>Acme Corp.</span>
            </DropdownMenuItem>
          </DropdownMenuContent>
        </DropdownMenu>
      </SidebarMenuItem>
    </SidebarMenu>
  </SidebarHeader>
</Sidebar>
```

## SidebarFooter

Use the `SidebarFooter` component to add a sticky footer to the sidebar.

The following example adds a `<DropdownMenu>` to the `SidebarFooter`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-footer"
    title="Sidebar"
    type="block"
    description="A sidebar footer with a dropdown menu."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar footer with a dropdown menu.
  </figcaption>
</figure>

```tsx showLineNumbers title="components/app-sidebar.tsx"
export function AppSidebar() {
  return (
    <SidebarProvider>
      <Sidebar>
        <SidebarHeader />
        <SidebarContent />
        <SidebarFooter>
          <SidebarMenu>
            <SidebarMenuItem>
              <DropdownMenu>
                <DropdownMenuTrigger asChild>
                  <SidebarMenuButton>
                    <User2 /> Username
                    <ChevronUp className="ml-auto" />
                  </SidebarMenuButton>
                </DropdownMenuTrigger>
                <DropdownMenuContent
                  side="top"
                  className="w-[--radix-popper-anchor-width]"
                >
                  <DropdownMenuItem>
                    <span>Account</span>
                  </DropdownMenuItem>
                  <DropdownMenuItem>
                    <span>Billing</span>
                  </DropdownMenuItem>
                  <DropdownMenuItem>
                    <span>Sign out</span>
                  </DropdownMenuItem>
                </DropdownMenuContent>
              </DropdownMenu>
            </SidebarMenuItem>
          </SidebarMenu>
        </SidebarFooter>
      </Sidebar>
    </SidebarProvider>
  )
}
```

## SidebarContent

The `SidebarContent` component is used to wrap the content of the sidebar. This is where you add your `SidebarGroup` components. It is scrollable.

```tsx showLineNumbers
import { Sidebar, SidebarContent } from "@/components/ui/sidebar"

export function AppSidebar() {
  return (
    <Sidebar>
      <SidebarContent>
        <SidebarGroup />
        <SidebarGroup />
      </SidebarContent>
    </Sidebar>
  )
}
```

## SidebarGroup

Use the `SidebarGroup` component to create a section within the sidebar.

A `SidebarGroup` has a `SidebarGroupLabel`, a `SidebarGroupContent` and an optional `SidebarGroupAction`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-group"
    title="Sidebar Group"
    type="block"
    description="A sidebar group."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar group.
  </figcaption>
</figure>

```tsx showLineNumbers
import { Sidebar, SidebarContent, SidebarGroup } from "@/components/ui/sidebar"

export function AppSidebar() {
  return (
    <Sidebar>
      <SidebarContent>
        <SidebarGroup>
          <SidebarGroupLabel>Application</SidebarGroupLabel>
          <SidebarGroupAction>
            <Plus /> <span className="sr-only">Add Project</span>
          </SidebarGroupAction>
          <SidebarGroupContent></SidebarGroupContent>
        </SidebarGroup>
      </SidebarContent>
    </Sidebar>
  )
}
```

## Collapsible SidebarGroup

To make a `SidebarGroup` collapsible, wrap it in a `Collapsible`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-group-collapsible"
    title="Sidebar Group"
    type="block"
    description="A collapsible sidebar group."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A collapsible sidebar group.
  </figcaption>
</figure>

```tsx showLineNumbers
export function AppSidebar() {
  return (
    <Collapsible defaultOpen className="group/collapsible">
      <SidebarGroup>
        <SidebarGroupLabel asChild>
          <CollapsibleTrigger>
            Help
            <ChevronDown className="ml-auto transition-transform group-data-[state=open]/collapsible:rotate-180" />
          </CollapsibleTrigger>
        </SidebarGroupLabel>
        <CollapsibleContent>
          <SidebarGroupContent />
        </CollapsibleContent>
      </SidebarGroup>
    </Collapsible>
  )
}
```

<Callout>
  **Note:** We wrap the `CollapsibleTrigger` in a `SidebarGroupLabel` to render
  a button.
</Callout>

## SidebarGroupAction

Use the `SidebarGroupAction` component to add an action button to the `SidebarGroup`.

```tsx showLineNumbers {5-7}
export function AppSidebar() {
  return (
    <SidebarGroup>
      <SidebarGroupLabel asChild>Projects</SidebarGroupLabel>
      <SidebarGroupAction title="Add Project">
        <Plus /> <span className="sr-only">Add Project</span>
      </SidebarGroupAction>
      <SidebarGroupContent />
    </SidebarGroup>
  )
}
```

<figure className="flex flex-col gap-4">
  <ComponentPreview
    name="sidebar-group-action"
    title="Sidebar Group"
    type="block"
    description="A sidebar group with an action button."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar group with an action button.
  </figcaption>
</figure>

## SidebarMenu

The `SidebarMenu` component is used for building a menu within a `SidebarGroup`.

A `SidebarMenu` component is composed of `SidebarMenuItem`, `SidebarMenuButton`, `<SidebarMenuAction />` and `<SidebarMenuSub />` components.

<Image
  src="/images/sidebar-menu.png"
  width="716"
  height="420"
  alt="Sidebar Menu"
  className="border dark:hidden rounded-lg overflow-hidden mt-6 w-full"
/>
<Image
  src="/images/sidebar-menu-dark.png"
  width="716"
  height="420"
  alt="Sidebar Menu"
  className="border hidden dark:block rounded-lg overflow-hidden mt-6 w-full"
/>

Here's an example of a `SidebarMenu` component rendering a list of projects.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-menu"
    title="Sidebar Menu"
    type="block"
    description="A sidebar menu with a list of projects."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar menu with a list of projects.
  </figcaption>
</figure>

```tsx showLineNumbers
<Sidebar>
  <SidebarContent>
    <SidebarGroup>
      <SidebarGroupLabel>Projects</SidebarGroupLabel>
      <SidebarGroupContent>
        <SidebarMenu>
          {projects.map((project) => (
            <SidebarMenuItem key={project.name}>
              <SidebarMenuButton asChild>
                <a href={project.url}>
                  <project.icon />
                  <span>{project.name}</span>
                </a>
              </SidebarMenuButton>
            </SidebarMenuItem>
          ))}
        </SidebarMenu>
      </SidebarGroupContent>
    </SidebarGroup>
  </SidebarContent>
</Sidebar>
```

## SidebarMenuButton

The `SidebarMenuButton` component is used to render a menu button within a `SidebarMenuItem`.

### Link or Anchor

By default, the `SidebarMenuButton` renders a button but you can use the `asChild` prop to render a different component such as a `Link` or an `a` tag.

```tsx showLineNumbers
<SidebarMenuButton asChild>
  <a href="#">Home</a>
</SidebarMenuButton>
```

### Icon and Label

You can render an icon and a truncated label inside the button. Remember to wrap the label in a `<span>`.

```tsx showLineNumbers
<SidebarMenuButton asChild>
  <a href="#">
    <Home />
    <span>Home</span>
  </a>
</SidebarMenuButton>
```

### isActive

Use the `isActive` prop to mark a menu item as active.

```tsx showLineNumbers
<SidebarMenuButton asChild isActive>
  <a href="#">Home</a>
</SidebarMenuButton>
```

## SidebarMenuAction

The `SidebarMenuAction` component is used to render a menu action within a `SidebarMenuItem`.

This button works independently of the `SidebarMenuButton` i.e you can have the `<SidebarMenuButton />` as a clickable link and the `<SidebarMenuAction />` as a button.

```tsx showLineNumbers
<SidebarMenuItem>
  <SidebarMenuButton asChild>
    <a href="#">
      <Home />
      <span>Home</span>
    </a>
  </SidebarMenuButton>
  <SidebarMenuAction>
    <Plus /> <span className="sr-only">Add Project</span>
  </SidebarMenuAction>
</SidebarMenuItem>
```

### DropdownMenu

Here's an example of a `SidebarMenuAction` component rendering a `DropdownMenu`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-menu-action"
    title="Sidebar Menu Action"
    type="block"
    description="A sidebar menu action with a dropdown menu."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar menu action with a dropdown menu.
  </figcaption>
</figure>

```tsx showLineNumbers
<SidebarMenuItem>
  <SidebarMenuButton asChild>
    <a href="#">
      <Home />
      <span>Home</span>
    </a>
  </SidebarMenuButton>
  <DropdownMenu>
    <DropdownMenuTrigger asChild>
      <SidebarMenuAction>
        <MoreHorizontal />
      </SidebarMenuAction>
    </DropdownMenuTrigger>
    <DropdownMenuContent side="right" align="start">
      <DropdownMenuItem>
        <span>Edit Project</span>
      </DropdownMenuItem>
      <DropdownMenuItem>
        <span>Delete Project</span>
      </DropdownMenuItem>
    </DropdownMenuContent>
  </DropdownMenu>
</SidebarMenuItem>
```

## SidebarMenuSub

The `SidebarMenuSub` component is used to render a submenu within a `SidebarMenu`.

Use `<SidebarMenuSubItem />` and `<SidebarMenuSubButton />` to render a submenu item.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-menu-sub"
    title="Sidebar Menu Sub"
    type="block"
    description="A sidebar menu sub."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar menu with a submenu.
  </figcaption>
</figure>

```tsx showLineNumbers
<SidebarMenuItem>
  <SidebarMenuButton />
  <SidebarMenuSub>
    <SidebarMenuSubItem>
      <SidebarMenuSubButton />
    </SidebarMenuSubItem>
    <SidebarMenuSubItem>
      <SidebarMenuSubButton />
    </SidebarMenuSubItem>
  </SidebarMenuSub>
</SidebarMenuItem>
```

## Collapsible SidebarMenu

To make a `SidebarMenu` component collapsible, wrap it and the `SidebarMenuSub` components in a `Collapsible`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-menu-collapsible"
    title="Sidebar Menu"
    type="block"
    description="A collapsible sidebar menu."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A collapsible sidebar menu.
  </figcaption>
</figure>

```tsx showLineNumbers
<SidebarMenu>
  <Collapsible defaultOpen className="group/collapsible">
    <SidebarMenuItem>
      <CollapsibleTrigger asChild>
        <SidebarMenuButton />
      </CollapsibleTrigger>
      <CollapsibleContent>
        <SidebarMenuSub>
          <SidebarMenuSubItem />
        </SidebarMenuSub>
      </CollapsibleContent>
    </SidebarMenuItem>
  </Collapsible>
</SidebarMenu>
```

## SidebarMenuBadge

The `SidebarMenuBadge` component is used to render a badge within a `SidebarMenuItem`.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-menu-badge"
    title="Sidebar Menu Badge"
    type="block"
    description="A sidebar menu badge."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar menu with a badge.
  </figcaption>
</figure>

```tsx showLineNumbers
<SidebarMenuItem>
  <SidebarMenuButton />
  <SidebarMenuBadge>24</SidebarMenuBadge>
</SidebarMenuItem>
```

## SidebarMenuSkeleton

The `SidebarMenuSkeleton` component is used to render a skeleton for a `SidebarMenu`. You can use this to show a loading state when using React Server Components, SWR or react-query.

```tsx showLineNumbers
function NavProjectsSkeleton() {
  return (
    <SidebarMenu>
      {Array.from({ length: 5 }).map((_, index) => (
        <SidebarMenuItem key={index}>
          <SidebarMenuSkeleton />
        </SidebarMenuItem>
      ))}
    </SidebarMenu>
  )
}
```

## SidebarSeparator

The `SidebarSeparator` component is used to render a separator within a `Sidebar`.

```tsx showLineNumbers
<Sidebar>
  <SidebarHeader />
  <SidebarSeparator />
  <SidebarContent>
    <SidebarGroup />
    <SidebarSeparator />
    <SidebarGroup />
  </SidebarContent>
</Sidebar>
```

## SidebarTrigger

Use the `SidebarTrigger` component to render a button that toggles the sidebar.

The `SidebarTrigger` component must be used within a `SidebarProvider`.

```tsx showLineNumbers
<SidebarProvider>
  <Sidebar />
  <main>
    <SidebarTrigger />
  </main>
</SidebarProvider>
```

### Custom Trigger

To create a custom trigger, you can use the `useSidebar` hook.

```tsx showLineNumbers
import { useSidebar } from "@/components/ui/sidebar"

export function CustomTrigger() {
  const { toggleSidebar } = useSidebar()

  return <button onClick={toggleSidebar}>Toggle Sidebar</button>
}
```

## SidebarRail

The `SidebarRail` component is used to render a rail within a `Sidebar`. This rail can be used to toggle the sidebar.

```tsx showLineNumbers
<Sidebar>
  <SidebarHeader />
  <SidebarContent>
    <SidebarGroup />
  </SidebarContent>
  <SidebarFooter />
  <SidebarRail />
</Sidebar>
```

## Data Fetching

### React Server Components

Here's an example of a `SidebarMenu` component rendering a list of projects using React Server Components.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-rsc"
    title="Sidebar Menu RSC"
    type="block"
    description="A sidebar menu using React Server Components."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A sidebar menu using React Server Components.
  </figcaption>
</figure>

```tsx showLineNumbers {6} title="Skeleton to show loading state."
function NavProjectsSkeleton() {
  return (
    <SidebarMenu>
      {Array.from({ length: 5 }).map((_, index) => (
        <SidebarMenuItem key={index}>
          <SidebarMenuSkeleton showIcon />
        </SidebarMenuItem>
      ))}
    </SidebarMenu>
  )
}
```

```tsx showLineNumbers {2} title="Server component fetching data."
async function NavProjects() {
  const projects = await fetchProjects()

  return (
    <SidebarMenu>
      {projects.map((project) => (
        <SidebarMenuItem key={project.name}>
          <SidebarMenuButton asChild>
            <a href={project.url}>
              <project.icon />
              <span>{project.name}</span>
            </a>
          </SidebarMenuButton>
        </SidebarMenuItem>
      ))}
    </SidebarMenu>
  )
}
```

```tsx showLineNumbers {8-10} title="Usage with React Suspense."
function AppSidebar() {
  return (
    <Sidebar>
      <SidebarContent>
        <SidebarGroup>
          <SidebarGroupLabel>Projects</SidebarGroupLabel>
          <SidebarGroupContent>
            <React.Suspense fallback={<NavProjectsSkeleton />}>
              <NavProjects />
            </React.Suspense>
          </SidebarGroupContent>
        </SidebarGroup>
      </SidebarContent>
    </Sidebar>
  )
}
```

### SWR and React Query

You can use the same approach with [SWR](https://swr.vercel.app/) or [react-query](https://tanstack.com/query/latest/docs/framework/react/overview).

```tsx showLineNumbers title="SWR"
function NavProjects() {
  const { data, isLoading } = useSWR("/api/projects", fetcher)

  if (isLoading) {
    return (
      <SidebarMenu>
        {Array.from({ length: 5 }).map((_, index) => (
          <SidebarMenuItem key={index}>
            <SidebarMenuSkeleton showIcon />
          </SidebarMenuItem>
        ))}
      </SidebarMenu>
    )
  }

  if (!data) {
    return ...
  }

  return (
    <SidebarMenu>
      {data.map((project) => (
        <SidebarMenuItem key={project.name}>
          <SidebarMenuButton asChild>
            <a href={project.url}>
              <project.icon />
              <span>{project.name}</span>
            </a>
          </SidebarMenuButton>
        </SidebarMenuItem>
      ))}
    </SidebarMenu>
  )
}
```

```tsx showLineNumbers title="React Query"
function NavProjects() {
  const { data, isLoading } = useQuery()

  if (isLoading) {
    return (
      <SidebarMenu>
        {Array.from({ length: 5 }).map((_, index) => (
          <SidebarMenuItem key={index}>
            <SidebarMenuSkeleton showIcon />
          </SidebarMenuItem>
        ))}
      </SidebarMenu>
    )
  }

  if (!data) {
    return ...
  }

  return (
    <SidebarMenu>
      {data.map((project) => (
        <SidebarMenuItem key={project.name}>
          <SidebarMenuButton asChild>
            <a href={project.url}>
              <project.icon />
              <span>{project.name}</span>
            </a>
          </SidebarMenuButton>
        </SidebarMenuItem>
      ))}
    </SidebarMenu>
  )
}
```

## Controlled Sidebar

Use the `open` and `onOpenChange` props to control the sidebar.

<figure className="flex flex-col gap-4 mt-6">
  <ComponentPreview
    name="sidebar-controlled"
    title="Sidebar Controlled"
    type="block"
    description="A controlled sidebar."
    className="w-full"
  />
  <figcaption className="text-center text-sm text-gray-500">
    A controlled sidebar.
  </figcaption>
</figure>

```tsx showLineNumbers
export function AppSidebar() {
  const [open, setOpen] = React.useState(false)

  return (
    <SidebarProvider open={open} onOpenChange={setOpen}>
      <Sidebar />
    </SidebarProvider>
  )
}
```

## Theming

We use the following CSS variables to theme the sidebar.

```css
@layer base {
  :root {
    --sidebar-background: 0 0% 98%;
    --sidebar-foreground: 240 5.3% 26.1%;
    --sidebar-primary: 240 5.9% 10%;
    --sidebar-primary-foreground: 0 0% 98%;
    --sidebar-accent: 240 4.8% 95.9%;
    --sidebar-accent-foreground: 240 5.9% 10%;
    --sidebar-border: 220 13% 91%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }

  .dark {
    --sidebar-background: 240 5.9% 10%;
    --sidebar-foreground: 240 4.8% 95.9%;
    --sidebar-primary: 0 0% 98%;
    --sidebar-primary-foreground: 240 5.9% 10%;
    --sidebar-accent: 240 3.7% 15.9%;
    --sidebar-accent-foreground: 240 4.8% 95.9%;
    --sidebar-border: 240 3.7% 15.9%;
    --sidebar-ring: 217.2 91.2% 59.8%;
  }
}
```

**We intentionally use different variables for the sidebar and the rest of the application** to make it easy to have a sidebar that is styled differently from the rest of the application. Think a sidebar with a darker shade from the main application.

## Styling

Here are some tips for styling the sidebar based on different states.

- **Styling an element based on the sidebar collapsible state.** The following will hide the `SidebarGroup` when the sidebar is in `icon` mode.

```tsx
<Sidebar collapsible="icon">
  <SidebarContent>
    <SidebarGroup className="group-data-[collapsible=icon]:hidden" />
  </SidebarContent>
</Sidebar>
```

- **Styling a menu action based on the menu button active state.** The following will force the menu action to be visible when the menu button is active.

```tsx
<SidebarMenuItem>
  <SidebarMenuButton />
  <SidebarMenuAction className="peer-data-[active=true]/menu-button:opacity-100" />
</SidebarMenuItem>
```

You can find more tips on using states for styling in this [Twitter thread](https://x.com/shadcn/status/1842329158879420864).

## Changelog

### 2024-10-30 Cookie handling in setOpen

- [#5593](https://github.com/shadcn-ui/ui/pull/5593) - Improved setOpen callback logic in `<SidebarProvider>`.

Update the `setOpen` callback in `<SidebarProvider>` as follows:

```tsx showLineNumbers
const setOpen = React.useCallback(
  (value: boolean | ((value: boolean) => boolean)) => {
    const openState = typeof value === "function" ? value(open) : value
    if (setOpenProp) {
      setOpenProp(openState)
    } else {
      _setOpen(openState)
    }

    // This sets the cookie to keep the sidebar state.
    document.cookie = `${SIDEBAR_COOKIE_NAME}=${openState}; path=/; max-age=${SIDEBAR_COOKIE_MAX_AGE}`
  },
  [setOpenProp, open]
)
```

### 2024-10-21 Fixed `text-sidebar-foreground`

- [#5491](https://github.com/shadcn-ui/ui/pull/5491) - Moved `text-sidebar-foreground` from `<SidebarProvider>` to `<Sidebar>` component.

### 2024-10-20 Typo in `useSidebar` hook.

Fixed typo in `useSidebar` hook.

```diff showLineNumbers title="sidebar.tsx"
-  throw new Error("useSidebar must be used within a Sidebar.")
+  throw new Error("useSidebar must be used within a SidebarProvider.")
```

```

### 📄 components/skeleton.mdx

```
---
title: Skeleton
description: Use to show a placeholder while content is loading.
component: true
---

<ComponentPreview name="skeleton-demo" description="A skeleton component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add skeleton
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="skeleton" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Skeleton } from "@/components/ui/skeleton"
```

```tsx
<Skeleton className="w-[100px] h-[20px] rounded-full" />
```

## Examples

### Card

<ComponentPreview
  name="skeleton-card"
  description="A card with skeleton showing a loading state."
/>

```

### 📄 components/slider.mdx

```
---
title: Slider
description: An input where the user selects a value from within a given range.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/slider
  api: https://www.radix-ui.com/docs/primitives/components/slider#api-reference
---

<ComponentPreview name="slider-demo" description="A slider component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add slider
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-slider
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="slider" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Slider } from "@/components/ui/slider"
```

```tsx
<Slider defaultValue={[33]} max={100} step={1} />
```

```

### 📄 components/sonner.mdx

```
---
title: Sonner
description: An opinionated toast component for React.
component: true
links:
  doc: https://sonner.emilkowal.ski
---

<ComponentPreview name="sonner-demo" />

## About

Sonner is built and maintained by [emilkowalski\_](https://twitter.com/emilkowalski_).

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

<Step>Run the following command:</Step>

```bash
npx shadcn@latest add sonner
```

<Step>Add the Toaster component</Step>

```tsx title="app/layout.tsx" {1,9}
import { Toaster } from "@/components/ui/sonner"

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head />
      <body>
        <main>{children}</main>
        <Toaster />
      </body>
    </html>
  )
}
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install sonner next-themes
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="sonner" />

<Step>Add the Toaster component</Step>

```tsx title="app/layout.tsx" {1,9}
import { Toaster } from "@/components/ui/sonner"

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head />
      <body>
        <main>{children}</main>
        <Toaster />
      </body>
    </html>
  )
}
```

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { toast } from "sonner"
```

```tsx
toast("Event has been created.")
```

```

### 📄 components/switch.mdx

```
---
title: Switch
description: A control that allows the user to toggle between checked and not checked.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/switch
  api: https://www.radix-ui.com/docs/primitives/components/switch#api-reference
---

<ComponentPreview name="switch-demo" description="A switch component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add switch
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-switch
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="switch" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Switch } from "@/components/ui/switch"
```

```tsx
<Switch />
```

## Examples

### Form

<ComponentPreview name="switch-form" />

```

### 📄 components/table.mdx

```
---
title: Table
description: A responsive table component.
component: true
---

<ComponentPreview name="table-demo" description="A table component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add table
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="table" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table"
```

```tsx
<Table>
  <TableCaption>A list of your recent invoices.</TableCaption>
  <TableHeader>
    <TableRow>
      <TableHead className="w-[100px]">Invoice</TableHead>
      <TableHead>Status</TableHead>
      <TableHead>Method</TableHead>
      <TableHead className="text-right">Amount</TableHead>
    </TableRow>
  </TableHeader>
  <TableBody>
    <TableRow>
      <TableCell className="font-medium">INV001</TableCell>
      <TableCell>Paid</TableCell>
      <TableCell>Credit Card</TableCell>
      <TableCell className="text-right">$250.00</TableCell>
    </TableRow>
  </TableBody>
</Table>
```

## Data Table

You can use the `<Table />` component to build more complex data tables. Combine it with [@tanstack/react-table](https://tanstack.com/table/v8) to create tables with sorting, filtering and pagination.

See the [Data Table](/docs/components/data-table) documentation for more information.

You can also see an example of a data table in the [Tasks](/examples/tasks) demo.

```

### 📄 components/tabs.mdx

```
---
title: Tabs
description: A set of layered sections of content—known as tab panels—that are displayed one at a time.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/tabs
  api: https://www.radix-ui.com/docs/primitives/components/tabs#api-reference
---

<ComponentPreview
  name="tabs-demo"
  description="A tabs component with two forms."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add tabs
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-tabs
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="tabs" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs"
```

```tsx
<Tabs defaultValue="account" className="w-[400px]">
  <TabsList>
    <TabsTrigger value="account">Account</TabsTrigger>
    <TabsTrigger value="password">Password</TabsTrigger>
  </TabsList>
  <TabsContent value="account">Make changes to your account here.</TabsContent>
  <TabsContent value="password">Change your password here.</TabsContent>
</Tabs>
```

```

### 📄 components/textarea.mdx

```
---
title: Textarea
description: Displays a form textarea or a component that looks like a textarea.
component: true
---

<ComponentPreview name="textarea-demo" description="A textarea" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add textarea
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="textarea" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Textarea } from "@/components/ui/textarea"
```

```tsx
<Textarea />
```

## Examples

### Default

<ComponentPreview name="textarea-demo" description="A textarea" />

### Disabled

<ComponentPreview name="textarea-disabled" description="A disabled textarea" />

### With Label

<ComponentPreview
  name="textarea-with-label"
  className="[&_div.grid]:w-full"
  description="A textarea with a label"
/>

### With Text

<ComponentPreview
  name="textarea-with-text"
  description="A textarea with text"
/>

### With Button

<ComponentPreview
  name="textarea-with-button"
  description="A textarea with a button"
/>

### Form

<ComponentPreview name="textarea-form" />

```

### 📄 components/toast.mdx

```
---
title: Toast
description: A succinct message that is displayed temporarily.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/toast
  api: https://www.radix-ui.com/docs/primitives/components/toast#api-reference
---

<ComponentPreview name="toast-demo" />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

<Steps>

<Step>Run the following command:</Step>

```bash
npx shadcn@latest add toast
```

<Step>Add the Toaster component</Step>

```tsx title="app/layout.tsx" {1,9}
import { Toaster } from "@/components/ui/toaster"

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head />
      <body>
        <main>{children}</main>
        <Toaster />
      </body>
    </html>
  )
}
```

</Steps>

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-toast
```

<Step>Copy and paste the following code into your project.</Step>

`toast.tsx`

<ComponentSource name="toast" />

`toaster.tsx`

<ComponentSource name="toast" fileName="toaster" />

`use-toast.tsx`

<ComponentSource name="toast" fileName="use-toast" />

<Step>Update the import paths to match your project setup.</Step>

<Step>Add the Toaster component</Step>

```tsx title="app/layout.tsx" {1,9}
import { Toaster } from "@/components/ui/toaster"

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head />
      <body>
        <main>{children}</main>
        <Toaster />
      </body>
    </html>
  )
}
```

</Steps>

</TabsContent>

</Tabs>

## Usage

The `useToast` hook returns a `toast` function that you can use to display a toast.

```tsx
import { useToast } from "@/hooks/use-toast"
```

```tsx {2,7-10}
export const ToastDemo = () => {
  const { toast } = useToast()

  return (
    <Button
      onClick={() => {
        toast({
          title: "Scheduled: Catch up",
          description: "Friday, February 10, 2023 at 5:57 PM",
        })
      }}
    >
      Show Toast
    </Button>
  )
}
```

<Callout>

To display multiple toasts at the same time, you can update the `TOAST_LIMIT` in `use-toast.tsx`.

</Callout>

## Examples

### Simple

<ComponentPreview name="toast-simple" />

### With title

<ComponentPreview name="toast-with-title" />

### With Action

<ComponentPreview name="toast-with-action" />

### Destructive

Use `toast({ variant: "destructive" })` to display a destructive toast.

<ComponentPreview name="toast-destructive" />

```

### 📄 components/toggle-group.mdx

```
---
title: Toggle Group
description: A set of two-state buttons that can be toggled on or off.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/toggle-group
  api: https://www.radix-ui.com/docs/primitives/components/toggle-group#api-reference
---

<ComponentPreview
  name="toggle-group-demo"
  description="A toggle group with three items."
/>

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add toggle-group
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-toggle-group
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="toggle-group" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { ToggleGroup, ToggleGroupItem } from "@/components/ui/toggle-group"
```

```tsx
<ToggleGroup type="single">
  <ToggleGroupItem value="a">A</ToggleGroupItem>
  <ToggleGroupItem value="b">B</ToggleGroupItem>
  <ToggleGroupItem value="c">C</ToggleGroupItem>
</ToggleGroup>
```

## Examples

### Default

<ComponentPreview
  name="toggle-group-demo"
  description="A toggle group with three items."
/>

### Outline

<ComponentPreview
  name="toggle-group-outline"
  description="A toggle group using the outline variant."
/>

### Single

<ComponentPreview
  name="toggle-group-single"
  description="A toggle group with single selection."
/>

### Small

<ComponentPreview
  name="toggle-group-sm"
  description="A toggle group using the small size."
/>

### Large

<ComponentPreview
  name="toggle-group-lg"
  description="A toggle group using the large size."
/>

### Disabled

<ComponentPreview
  name="toggle-group-disabled"
  description="A disabled toggle group."
/>

```

### 📄 components/toggle.mdx

```
---
title: Toggle
description: A two-state button that can be either on or off.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/toggle
  api: https://www.radix-ui.com/docs/primitives/components/toggle#api-reference
---

<ComponentPreview name="toggle-demo" description="A toggle component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add toggle
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-toggle
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="toggle" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import { Toggle } from "@/components/ui/toggle"
```

```tsx
<Toggle>Toggle</Toggle>
```

## Examples

### Default

<ComponentPreview name="toggle-demo" description="A toggle component." />

### Outline

<ComponentPreview
  name="toggle-outline"
  description="A toggle component using the outline variant."
/>

### With Text

<ComponentPreview
  name="toggle-with-text"
  description="A toggle component with text."
/>

### Small

<ComponentPreview name="toggle-sm" description="A small toggle component." />

### Large

<ComponentPreview name="toggle-lg" description="A large toggle component." />

### Disabled

<ComponentPreview
  name="toggle-disabled"
  description="A disabled toggle component."
/>

```

### 📄 components/tooltip.mdx

```
---
title: Tooltip
description: A popup that displays information related to an element when the element receives keyboard focus or the mouse hovers over it.
component: true
links:
  doc: https://www.radix-ui.com/docs/primitives/components/tooltip
  api: https://www.radix-ui.com/docs/primitives/components/tooltip#api-reference
---

<ComponentPreview name="tooltip-demo" description="A tooltip component." />

## Installation

<Tabs defaultValue="cli">

<TabsList>
  <TabsTrigger value="cli">CLI</TabsTrigger>
  <TabsTrigger value="manual">Manual</TabsTrigger>
</TabsList>
<TabsContent value="cli">

```bash
npx shadcn@latest add tooltip
```

</TabsContent>

<TabsContent value="manual">

<Steps>

<Step>Install the following dependencies:</Step>

```bash
npm install @radix-ui/react-tooltip
```

<Step>Copy and paste the following code into your project.</Step>

<ComponentSource name="tooltip" />

<Step>Update the import paths to match your project setup.</Step>

</Steps>

</TabsContent>

</Tabs>

## Usage

```tsx
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from "@/components/ui/tooltip"
```

```tsx
<TooltipProvider>
  <Tooltip>
    <TooltipTrigger>Hover</TooltipTrigger>
    <TooltipContent>
      <p>Add to library</p>
    </TooltipContent>
  </Tooltip>
</TooltipProvider>
```

```

### 📄 components/typography.mdx

```
---
title: Typography
description: Styles for headings, paragraphs, lists...etc
component: true
---

<ComponentPreview
  name="typography-demo"
  className="[&>div.min-h-[350px]]:p-6"
  description="A collection of typographic elements."
/>

## h1

<ComponentPreview name="typography-h1" />

## h2

<ComponentPreview name="typography-h2" />

## h3

<ComponentPreview name="typography-h3" />

## h4

<ComponentPreview name="typography-h4" />

## p

<ComponentPreview name="typography-p" />

## blockquote

<ComponentPreview name="typography-blockquote" />

## table

<ComponentPreview name="typography-table" />

## list

<ComponentPreview name="typography-list" />

## Inline code

<ComponentPreview name="typography-inline-code" />

## Lead

<ComponentPreview name="typography-lead" />

## Large

<ComponentPreview name="typography-large" />

## Small

<ComponentPreview name="typography-small" />

## Muted

<ComponentPreview name="typography-muted" />

```

### 📄 dark-mode/astro.mdx

```
---
title: Astro
description: Adding dark mode to your astro app.
---

## Dark mode

<Steps>

### Create an inline theme script

```astro title="src/pages/index.astro"
---
import '../styles/globals.css'
---

<script is:inline>
  const getThemePreference = () => {
    if (typeof localStorage !== 'undefined' && localStorage.getItem('theme')) {
      return localStorage.getItem('theme');
    }
    return window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light';
  };
  const isDark = getThemePreference() === 'dark';
  document.documentElement.classList[isDark ? 'add' : 'remove']('dark');

  if (typeof localStorage !== 'undefined') {
    const observer = new MutationObserver(() => {
      const isDark = document.documentElement.classList.contains('dark');
      localStorage.setItem('theme', isDark ? 'dark' : 'light');
    });
    observer.observe(document.documentElement, { attributes: true, attributeFilter: ['class'] });
  }
</script>

<html lang="en">
  <body>
      <h1>Astro</h1>
  </body>
</html>
```

### Add a mode toggle

```tsx title="src/components/ModeToggle.tsx"
import * as React from "react"
import { Moon, Sun } from "lucide-react"

import { Button } from "@/components/ui/button"
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"

export function ModeToggle() {
  const [theme, setThemeState] = React.useState<
    "theme-light" | "dark" | "system"
  >("theme-light")

  React.useEffect(() => {
    const isDarkMode = document.documentElement.classList.contains("dark")
    setThemeState(isDarkMode ? "dark" : "theme-light")
  }, [])

  React.useEffect(() => {
    const isDark =
      theme === "dark" ||
      (theme === "system" &&
        window.matchMedia("(prefers-color-scheme: dark)").matches)
    document.documentElement.classList[isDark ? "add" : "remove"]("dark")
  }, [theme])

  return (
    <DropdownMenu>
      <DropdownMenuTrigger asChild>
        <Button variant="outline" size="icon">
          <Sun className="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
          <Moon className="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
          <span className="sr-only">Toggle theme</span>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        <DropdownMenuItem onClick={() => setThemeState("theme-light")}>
          Light
        </DropdownMenuItem>
        <DropdownMenuItem onClick={() => setThemeState("dark")}>
          Dark
        </DropdownMenuItem>
        <DropdownMenuItem onClick={() => setThemeState("system")}>
          System
        </DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  )
}
```

### Display the mode toggle

Place a mode toggle on your site to toggle between light and dark mode.

```astro title="src/pages/index.astro"
---
import '../styles/globals.css'
import { ModeToggle } from '@/components/ModeToggle';
---

<!-- Inline script -->

<html lang="en">
  <body>
      <h1>Astro</h1>
      <ModeToggle client:load />
  </body>
</html>
```

</Steps>

```

### 📄 dark-mode/index.mdx

```
---
title: Dark Mode
description: Adding dark mode to your site.
---

<div className="grid sm:grid-cols-2 gap-4 sm:gap-6">
  <LinkedCard href="/docs/dark-mode/next">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Next.js</title>
      <path d="M11.5725 0c-.1763 0-.3098.0013-.3584.0067-.0516.0053-.2159.021-.3636.0328-3.4088.3073-6.6017 2.1463-8.624 4.9728C1.1004 6.584.3802 8.3666.1082 10.255c-.0962.659-.108.8537-.108 1.7474s.012 1.0884.108 1.7476c.652 4.506 3.8591 8.2919 8.2087 9.6945.7789.2511 1.6.4223 2.5337.5255.3636.04 1.9354.04 2.299 0 1.6117-.1783 2.9772-.577 4.3237-1.2643.2065-.1056.2464-.1337.2183-.1573-.0188-.0139-.8987-1.1938-1.9543-2.62l-1.919-2.592-2.4047-3.5583c-1.3231-1.9564-2.4117-3.556-2.4211-3.556-.0094-.0026-.0187 1.5787-.0235 3.509-.0067 3.3802-.0093 3.5162-.0516 3.596-.061.115-.108.1618-.2064.2134-.075.0374-.1408.0445-.495.0445h-.406l-.1078-.068a.4383.4383 0 01-.1572-.1712l-.0493-.1056.0053-4.703.0067-4.7054.0726-.0915c.0376-.0493.1174-.1125.1736-.143.0962-.047.1338-.0517.5396-.0517.4787 0 .5584.0187.6827.1547.0353.0377 1.3373 1.9987 2.895 4.3608a10760.433 10760.433 0 004.7344 7.1706l1.9002 2.8782.096-.0633c.8518-.5536 1.7525-1.3418 2.4657-2.1627 1.5179-1.7429 2.4963-3.868 2.8247-6.134.0961-.6591.1078-.854.1078-1.7475 0-.8937-.012-1.0884-.1078-1.7476-.6522-4.506-3.8592-8.2919-8.2087-9.6945-.7672-.2487-1.5836-.42-2.4985-.5232-.169-.0176-1.0835-.0366-1.6123-.037zm4.0685 7.217c.3473 0 .4082.0053.4857.047.1127.0562.204.1642.237.2767.0186.061.0234 1.3653.0186 4.3044l-.0067 4.2175-.7436-1.14-.7461-1.14v-3.066c0-1.982.0093-3.0963.0234-3.1502.0375-.1313.1196-.2346.2323-.2955.0961-.0494.1313-.054.4997-.054z" />
    </svg>
    <p className="font-medium mt-2">Next.js</p>
  </LinkedCard>
  <LinkedCard href="/docs/dark-mode/vite">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Vite</title>
      <path d="m8.286 10.578.512-8.657a.306.306 0 0 1 .247-.282L17.377.006a.306.306 0 0 1 .353.385l-1.558 5.403a.306.306 0 0 0 .352.385l2.388-.46a.306.306 0 0 1 .332.438l-6.79 13.55-.123.19a.294.294 0 0 1-.252.14c-.177 0-.35-.152-.305-.369l1.095-5.301a.306.306 0 0 0-.388-.355l-1.433.435a.306.306 0 0 1-.389-.354l.69-3.375a.306.306 0 0 0-.37-.36l-2.32.536a.306.306 0 0 1-.374-.316zm14.976-7.926L17.284 3.74l-.544 1.887 2.077-.4a.8.8 0 0 1 .84.369.8.8 0 0 1 .034.783L12.9 19.93l-.013.025-.015.023-.122.19a.801.801 0 0 1-.672.37.826.826 0 0 1-.634-.302.8.8 0 0 1-.16-.67l1.029-4.981-1.12.34a.81.81 0 0 1-.86-.262.802.802 0 0 1-.165-.67l.63-3.08-2.027.468a.808.808 0 0 1-.768-.233.81.81 0 0 1-.217-.6l.389-6.57-7.44-1.33a.612.612 0 0 0-.64.906L11.58 23.691a.612.612 0 0 0 1.066-.004l11.26-20.135a.612.612 0 0 0-.644-.9z" />
    </svg>
    <p className="font-medium mt-2">Vite</p>
  </LinkedCard>
  <LinkedCard href="/docs/dark-mode/astro">
    <svg
      role="img"
      viewBox="0 0 64 79"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <path d="M19.9924 65.9282C16.1165 62.432 14.9851 55.0859 16.5999 49.7638C19.3998 53.1193 23.2793 54.1822 27.2977 54.7822C33.5013 55.7081 39.5937 55.3618 45.3565 52.5637C46.0158 52.2434 46.625 51.8174 47.3454 51.386C47.8861 52.9341 48.0268 54.497 47.838 56.0877C47.3787 59.9617 45.4251 62.9542 42.3177 65.2227C41.0752 66.13 39.7604 66.9411 38.4771 67.7967C34.5346 70.4262 33.4679 73.5095 34.9494 77.9946C34.9846 78.1038 35.0161 78.2131 35.0957 78.4797C33.0828 77.5909 31.6124 76.2965 30.4921 74.5946C29.3088 72.7984 28.7458 70.8114 28.7162 68.6615C28.7014 67.6152 28.7014 66.5597 28.5588 65.5282C28.2107 63.0135 27.0144 61.8876 24.7608 61.8227C22.4479 61.7561 20.6183 63.1672 20.1331 65.3893C20.0961 65.5597 20.0424 65.7282 19.9887 65.9263L19.9924 65.9282Z" />
      <path d="M0.5 51.3932C0.5 51.3932 11.0979 46.2433 21.7254 46.2433L29.7382 21.5069C30.0381 20.3106 30.9141 19.4977 31.9029 19.4977C32.8918 19.4977 33.7677 20.3106 34.0677 21.5069L42.0804 46.2433C54.6672 46.2433 63.3058 51.3932 63.3058 51.3932C63.3058 51.3932 45.3044 2.47586 45.2692 2.37772C44.7526 0.931458 43.8804 0 42.7045 0H21.1032C19.9273 0 19.0903 0.931458 18.5384 2.37772C18.4995 2.47401 0.5 51.3932 0.5 51.3932Z" />
    </svg>
    <p className="font-medium mt-2">Astro</p>
  </LinkedCard>
  <LinkedCard href="/docs/dark-mode/remix">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Remix</title>
      <path d="M21.511 18.508c.216 2.773.216 4.073.216 5.492H15.31c0-.309.006-.592.011-.878.018-.892.036-1.821-.109-3.698-.19-2.747-1.374-3.358-3.55-3.358H1.574v-5h10.396c2.748 0 4.122-.835 4.122-3.049 0-1.946-1.374-3.125-4.122-3.125H1.573V0h11.541c6.221 0 9.313 2.938 9.313 7.632 0 3.511-2.176 5.8-5.114 6.182 2.48.497 3.93 1.909 4.198 4.694ZM1.573 24v-3.727h6.784c1.133 0 1.379.84 1.379 1.342V24Z" />
    </svg>
    <p className="font-medium mt-2">Remix</p>
  </LinkedCard>
</div>

```

### 📄 dark-mode/next.mdx

```
---
title: Next.js
description: Adding dark mode to your next app.
---

## Dark mode

<Steps>

### Install next-themes

Start by installing `next-themes`:

```bash
npm install next-themes
```

### Create a theme provider

```tsx title="components/theme-provider.tsx"
"use client"

import * as React from "react"
import { ThemeProvider as NextThemesProvider } from "next-themes"

export function ThemeProvider({
  children,
  ...props
}: React.ComponentProps<typeof NextThemesProvider>) {
  return <NextThemesProvider {...props}>{children}</NextThemesProvider>
}
```

### Wrap your root layout

Add the `ThemeProvider` to your root layout.

```tsx {1,9-11} title="app/layout.tsx"
import { ThemeProvider } from "@/components/theme-provider"

export default function RootLayout({ children }: RootLayoutProps) {
  return (
    <>
      <html lang="en" suppressHydrationWarning>
        <head />
        <body>
          <ThemeProvider
            attribute="class"
            defaultTheme="system"
            enableSystem
            disableTransitionOnChange
          >
            {children}
          </ThemeProvider>
        </body>
      </html>
    </>
  )
}
```

### Add a mode toggle

Place a mode toggle on your site to toggle between light and dark mode.

<ComponentPreview name="mode-toggle" className="[&_.preview]:items-start" />

</Steps>

```

### 📄 dark-mode/remix.mdx

```
---
title: Remix
description: Adding dark mode to your remix app.
---

## Dark mode

<Steps>

### Modify your tailwind.css file

Add `:root[class~="dark"]` to your tailwind.css file. This will allow you to use the `dark` class on your html element to apply dark mode styles.

```css {2} title="app/tailwind.css"
.dark,
:root[class~="dark"] {
  ...;
}
```

### Install remix-themes

Start by installing `remix-themes`:

```bash
npm install remix-themes
```

### Create a session storage and theme session resolver

```tsx title="app/sessions.server.tsx"
import { createThemeSessionResolver } from "remix-themes"

// You can default to 'development' if process.env.NODE_ENV is not set
const isProduction = process.env.NODE_ENV === "production"

const sessionStorage = createCookieSessionStorage({
  cookie: {
    name: "theme",
    path: "/",
    httpOnly: true,
    sameSite: "lax",
    secrets: ["s3cr3t"],
    // Set domain and secure only if in production
    ...(isProduction
      ? { domain: "your-production-domain.com", secure: true }
      : {}),
  },
})

export const themeSessionResolver = createThemeSessionResolver(sessionStorage)
```

### Set up Remix Themes

Add the `ThemeProvider` to your root layout.

```tsx {1-3,6-11,15-22,25-26,28,33} title="app/root.tsx"
import clsx from "clsx"
import { PreventFlashOnWrongTheme, ThemeProvider, useTheme } from "remix-themes"

import { themeSessionResolver } from "./sessions.server"

// Return the theme from the session storage using the loader
export async function loader({ request }: LoaderFunctionArgs) {
  const { getTheme } = await themeSessionResolver(request)
  return {
    theme: getTheme(),
  }
}
// Wrap your app with ThemeProvider.
// `specifiedTheme` is the stored theme in the session storage.
// `themeAction` is the action name that's used to change the theme in the session storage.
export default function AppWithProviders() {
  const data = useLoaderData<typeof loader>()
  return (
    <ThemeProvider specifiedTheme={data.theme} themeAction="/action/set-theme">
      <App />
    </ThemeProvider>
  )
}

export function App() {
  const data = useLoaderData<typeof loader>()
  const [theme] = useTheme()
  return (
    <html lang="en" className={clsx(theme)}>
      <head>
        <meta charSet="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <Meta />
        <PreventFlashOnWrongTheme ssrTheme={Boolean(data.theme)} />
        <Links />
      </head>
      <body>
        <Outlet />
        <ScrollRestoration />
        <Scripts />
        <LiveReload />
      </body>
    </html>
  )
}
```

### Add an action route

Create a file in `/routes/action.set-theme.ts`. Ensure that you pass the filename to the ThemeProvider component. This route it's used to store the preferred theme in the session storage when the user changes it.

```tsx title="app/routes/action.set-theme.ts"
import { createThemeAction } from "remix-themes"

import { themeSessionResolver } from "./sessions.server"

export const action = createThemeAction(themeSessionResolver)
```

### Add a mode toggle

Place a mode toggle on your site to toggle between light and dark mode.

```tsx title="components/mode-toggle.tsx"
import { Moon, Sun } from "lucide-react"
import { Theme, useTheme } from "remix-themes"

import { Button } from "./ui/button"
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "./ui/dropdown-menu"

export function ModeToggle() {
  const [, setTheme] = useTheme()

  return (
    <DropdownMenu>
      <DropdownMenuTrigger asChild>
        <Button variant="ghost" size="icon">
          <Sun className="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
          <Moon className="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
          <span className="sr-only">Toggle theme</span>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        <DropdownMenuItem onClick={() => setTheme(Theme.LIGHT)}>
          Light
        </DropdownMenuItem>
        <DropdownMenuItem onClick={() => setTheme(Theme.DARK)}>
          Dark
        </DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  )
}
```

</Steps>

```

### 📄 dark-mode/vite.mdx

```
---
title: Vite
description: Adding dark mode to your vite app.
---

## Dark mode

<Steps>

### Create a theme provider

```tsx title="components/theme-provider.tsx"
import { createContext, useContext, useEffect, useState } from "react"

type Theme = "dark" | "light" | "system"

type ThemeProviderProps = {
  children: React.ReactNode
  defaultTheme?: Theme
  storageKey?: string
}

type ThemeProviderState = {
  theme: Theme
  setTheme: (theme: Theme) => void
}

const initialState: ThemeProviderState = {
  theme: "system",
  setTheme: () => null,
}

const ThemeProviderContext = createContext<ThemeProviderState>(initialState)

export function ThemeProvider({
  children,
  defaultTheme = "system",
  storageKey = "vite-ui-theme",
  ...props
}: ThemeProviderProps) {
  const [theme, setTheme] = useState<Theme>(
    () => (localStorage.getItem(storageKey) as Theme) || defaultTheme
  )

  useEffect(() => {
    const root = window.document.documentElement

    root.classList.remove("light", "dark")

    if (theme === "system") {
      const systemTheme = window.matchMedia("(prefers-color-scheme: dark)")
        .matches
        ? "dark"
        : "light"

      root.classList.add(systemTheme)
      return
    }

    root.classList.add(theme)
  }, [theme])

  const value = {
    theme,
    setTheme: (theme: Theme) => {
      localStorage.setItem(storageKey, theme)
      setTheme(theme)
    },
  }

  return (
    <ThemeProviderContext.Provider {...props} value={value}>
      {children}
    </ThemeProviderContext.Provider>
  )
}

export const useTheme = () => {
  const context = useContext(ThemeProviderContext)

  if (context === undefined)
    throw new Error("useTheme must be used within a ThemeProvider")

  return context
}
```

### Wrap your root layout

Add the `ThemeProvider` to your root layout.

```tsx {1,5-7} title="App.tsx"
import { ThemeProvider } from "@/components/theme-provider"

function App() {
  return (
    <ThemeProvider defaultTheme="dark" storageKey="vite-ui-theme">
      {children}
    </ThemeProvider>
  )
}

export default App
```

### Add a mode toggle

Place a mode toggle on your site to toggle between light and dark mode.

```tsx title="components/mode-toggle.tsx"
import { Moon, Sun } from "lucide-react"

import { Button } from "@/components/ui/button"
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"
import { useTheme } from "@/components/theme-provider"

export function ModeToggle() {
  const { setTheme } = useTheme()

  return (
    <DropdownMenu>
      <DropdownMenuTrigger asChild>
        <Button variant="outline" size="icon">
          <Sun className="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
          <Moon className="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100" />
          <span className="sr-only">Toggle theme</span>
        </Button>
      </DropdownMenuTrigger>
      <DropdownMenuContent align="end">
        <DropdownMenuItem onClick={() => setTheme("light")}>
          Light
        </DropdownMenuItem>
        <DropdownMenuItem onClick={() => setTheme("dark")}>
          Dark
        </DropdownMenuItem>
        <DropdownMenuItem onClick={() => setTheme("system")}>
          System
        </DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  )
}
```

</Steps>

```

### 📄 installation/astro.mdx

```
---
title: Astro
description: Install and configure Astro.
---

<Steps>

### Create project

Start by creating a new Astro project:

```bash
npm create astro@latest
```

### Configure your Astro project

You will be asked a few questions to configure your project:

```txt showLineNumbers
- Where should we create your new project? ./your-app-name
- How would you like to start your new project? Choose a template
- Do you plan to write TypeScript? Yes
- How strict should TypeScript be? Strict
- Install dependencies? Yes
- Initialize a new git repository? (optional) Yes/No
```

### Add React to your project

Install React using the Astro CLI:

```bash
npx astro add react
```

<Callout className="mt-4">

Answer `Yes` to all the question prompted by the CLI when installing React.

</Callout>

### Add Tailwind CSS to your project

```bash
npx astro add tailwind
```

<Step>Create a `styles/globals.css` file in the `src` folder.</Step>

```css title="styles/globals.css" showLineNumbers
@tailwind base;
@tailwind components;
@tailwind utilities;
```

<Step>Import the `globals.css` file</Step>

Import the `styles/globals.css` file in the `src/pages/index.astro` file:

```ts title="src/pages/index.astro" showLineNumbers
---
import '@/styles/globals.css'
---
```

<Step>Update `astro.config.mjs` and set `applyBaseStyles` to `false`</Step>

To prevent serving the Tailwind base styles twice, we need to tell Astro not to apply the base styles, since we already include them in our own `globals.css` file. To do this, set the `applyBaseStyles` config option for the tailwind plugin in `astro.config.mjs` to `false`.

```js title="astro.config.mjs" {3-5} showLineNumbers
export default defineConfig({
  integrations: [
    tailwind({
      applyBaseStyles: false,
    }),
  ],
})
```

### Edit tsconfig.json file

Add the following code to the `tsconfig.json` file to resolve paths:

```ts title="tsconfig.json" {4-9} showLineNumbers
{
  "compilerOptions": {
    // ...
    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
    // ...
  }
}
```

### Run the CLI

Run the `shadcn` init command to setup your project:

```bash
npx shadcn@latest init
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```astro {2,10} showLineNumbers
---
import { Button } from "@/components/ui/button"
---

<html lang="en">
  <head>
    <title>Astro</title>
  </head>
  <body>
    <Button>Hello World</Button>
  </body>
</html>
```

</Steps>

```

### 📄 installation/gatsby.mdx

```
---
title: Gatsby
description: Install and configure Gatsby.
---

<Steps>

### Create project

Start by creating a new Gatsby project using `create-gatsby`:

```bash
npm init gatsby
```

### Configure your Gatsby project to use TypeScript and Tailwind CSS

You will be asked a few questions to configure your project:

```txt showLineNumbers
✔ What would you like to call your site?
· your-app-name
✔ What would you like to name the folder where your site will be created?
· your-app-name
✔ Will you be using JavaScript or TypeScript?
· TypeScript
✔ Will you be using a CMS?
· Choose whatever you want
✔ Would you like to install a styling system?
· Tailwind CSS
✔ Would you like to install additional features with other plugins?
· Choose whatever you want
✔ Shall we do this? (Y/n) · Yes
```

### Edit tsconfig.json file

Add the following code to the `tsconfig.json` file to resolve paths:

```ts {4-9} showLineNumbers
{
  "compilerOptions": {
    // ...
    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
    // ...
  }
}
```

### Create gatsby-node.ts file

Create a `gatsby-node.ts` file at the root of your project if it doesn’t already exist, and add the code below to the `gatsby-node` file so your app can resolve paths:

```ts
import * as path from "path"

export const onCreateWebpackConfig = ({ actions }) => {
  actions.setWebpackConfig({
    resolve: {
      alias: {
        "@/components": path.resolve(__dirname, "src/components"),
        "@/lib/utils": path.resolve(__dirname, "src/lib/utils"),
      },
    },
  })
}
```

### Run the CLI

Run the `shadcn-ui` init command to setup your project:

```bash
npx shadcn@latest init
```

### Configure components.json

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Would you like to use TypeScript (recommended)? no / yes
Which style would you like to use? › Default
Which color would you like to use as base color? › Slate
Where is your global CSS file? › › ./src/styles/globals.css
Do you want to use CSS variables for colors? › no / yes
Where is your tailwind.config.js located? › tailwind.config.js
Configure the import alias for components: › @/components
Configure the import alias for utils: › @/lib/utils
Are you using React Server Components? › no
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```tsx {1,6} showLineNumbers
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

</Steps>

```

### 📄 installation/index.mdx

```
---
title: Installation
description: How to install dependencies and structure your app.
---

## Frameworks

<div className="grid sm:grid-cols-2 gap-4 mt-8 sm:gap-6">
  <LinkedCard href="/docs/installation/next">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Next.js</title>
      <path d="M11.5725 0c-.1763 0-.3098.0013-.3584.0067-.0516.0053-.2159.021-.3636.0328-3.4088.3073-6.6017 2.1463-8.624 4.9728C1.1004 6.584.3802 8.3666.1082 10.255c-.0962.659-.108.8537-.108 1.7474s.012 1.0884.108 1.7476c.652 4.506 3.8591 8.2919 8.2087 9.6945.7789.2511 1.6.4223 2.5337.5255.3636.04 1.9354.04 2.299 0 1.6117-.1783 2.9772-.577 4.3237-1.2643.2065-.1056.2464-.1337.2183-.1573-.0188-.0139-.8987-1.1938-1.9543-2.62l-1.919-2.592-2.4047-3.5583c-1.3231-1.9564-2.4117-3.556-2.4211-3.556-.0094-.0026-.0187 1.5787-.0235 3.509-.0067 3.3802-.0093 3.5162-.0516 3.596-.061.115-.108.1618-.2064.2134-.075.0374-.1408.0445-.495.0445h-.406l-.1078-.068a.4383.4383 0 01-.1572-.1712l-.0493-.1056.0053-4.703.0067-4.7054.0726-.0915c.0376-.0493.1174-.1125.1736-.143.0962-.047.1338-.0517.5396-.0517.4787 0 .5584.0187.6827.1547.0353.0377 1.3373 1.9987 2.895 4.3608a10760.433 10760.433 0 004.7344 7.1706l1.9002 2.8782.096-.0633c.8518-.5536 1.7525-1.3418 2.4657-2.1627 1.5179-1.7429 2.4963-3.868 2.8247-6.134.0961-.6591.1078-.854.1078-1.7475 0-.8937-.012-1.0884-.1078-1.7476-.6522-4.506-3.8592-8.2919-8.2087-9.6945-.7672-.2487-1.5836-.42-2.4985-.5232-.169-.0176-1.0835-.0366-1.6123-.037zm4.0685 7.217c.3473 0 .4082.0053.4857.047.1127.0562.204.1642.237.2767.0186.061.0234 1.3653.0186 4.3044l-.0067 4.2175-.7436-1.14-.7461-1.14v-3.066c0-1.982.0093-3.0963.0234-3.1502.0375-.1313.1196-.2346.2323-.2955.0961-.0494.1313-.054.4997-.054z" />
    </svg>
    <p className="font-medium mt-2">Next.js</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/vite">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Vite</title>
      <path d="m8.286 10.578.512-8.657a.306.306 0 0 1 .247-.282L17.377.006a.306.306 0 0 1 .353.385l-1.558 5.403a.306.306 0 0 0 .352.385l2.388-.46a.306.306 0 0 1 .332.438l-6.79 13.55-.123.19a.294.294 0 0 1-.252.14c-.177 0-.35-.152-.305-.369l1.095-5.301a.306.306 0 0 0-.388-.355l-1.433.435a.306.306 0 0 1-.389-.354l.69-3.375a.306.306 0 0 0-.37-.36l-2.32.536a.306.306 0 0 1-.374-.316zm14.976-7.926L17.284 3.74l-.544 1.887 2.077-.4a.8.8 0 0 1 .84.369.8.8 0 0 1 .034.783L12.9 19.93l-.013.025-.015.023-.122.19a.801.801 0 0 1-.672.37.826.826 0 0 1-.634-.302.8.8 0 0 1-.16-.67l1.029-4.981-1.12.34a.81.81 0 0 1-.86-.262.802.802 0 0 1-.165-.67l.63-3.08-2.027.468a.808.808 0 0 1-.768-.233.81.81 0 0 1-.217-.6l.389-6.57-7.44-1.33a.612.612 0 0 0-.64.906L11.58 23.691a.612.612 0 0 0 1.066-.004l11.26-20.135a.612.612 0 0 0-.644-.9z" />
    </svg>
    <p className="font-medium mt-2">Vite</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/remix">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Remix</title>
      <path d="M21.511 18.508c.216 2.773.216 4.073.216 5.492H15.31c0-.309.006-.592.011-.878.018-.892.036-1.821-.109-3.698-.19-2.747-1.374-3.358-3.55-3.358H1.574v-5h10.396c2.748 0 4.122-.835 4.122-3.049 0-1.946-1.374-3.125-4.122-3.125H1.573V0h11.541c6.221 0 9.313 2.938 9.313 7.632 0 3.511-2.176 5.8-5.114 6.182 2.48.497 3.93 1.909 4.198 4.694ZM1.573 24v-3.727h6.784c1.133 0 1.379.84 1.379 1.342V24Z" />
    </svg>
    <p className="font-medium mt-2">Remix</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/astro">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Astro</title>
      <path
        d="M16.074 16.86C15.354 17.476 13.917 17.895 12.262 17.895C10.23 17.895 8.527 17.263 8.075 16.412C7.914 16.9 7.877 17.458 7.877 17.814C7.877 17.814 7.771 19.564 8.988 20.782C8.988 20.15 9.501 19.637 10.133 19.637C11.216 19.637 11.215 20.582 11.214 21.349V21.418C11.214 22.582 11.925 23.579 12.937 24C12.7812 23.6794 12.7005 23.3275 12.701 22.971C12.701 21.861 13.353 21.448 14.111 20.968C14.713 20.585 15.383 20.161 15.844 19.308C16.0926 18.8493 16.2225 18.3357 16.222 17.814C16.2221 17.4903 16.1722 17.1685 16.074 16.86ZM15.551 0.6C15.747 0.844 15.847 1.172 16.047 1.829L20.415 16.176C18.7743 15.3246 17.0134 14.7284 15.193 14.408L12.35 4.8C12.3273 4.72337 12.2803 4.65616 12.2162 4.60844C12.152 4.56072 12.0742 4.53505 11.9943 4.53528C11.9143 4.5355 11.8366 4.56161 11.7727 4.60969C11.7089 4.65777 11.6623 4.72524 11.64 4.802L8.83 14.405C7.00149 14.724 5.23264 15.3213 3.585 16.176L7.974 1.827C8.174 1.171 8.274 0.843 8.471 0.6C8.64406 0.385433 8.86922 0.218799 9.125 0.116C9.415 0 9.757 0 10.443 0H13.578C14.264 0 14.608 0 14.898 0.117C15.1529 0.219851 15.3783 0.386105 15.551 0.6Z"
        fill="currentColor"
      />
    </svg>
    <p className="font-medium mt-2">Astro</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/laravel">
    <svg
      role="img"
      viewBox="0 0 62 65"
      fill="currentColor"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
    >
      <path d="M61.8548 14.6253C61.8778 14.7102 61.8895 14.7978 61.8897 14.8858V28.5615C61.8898 28.737 61.8434 28.9095 61.7554 29.0614C61.6675 29.2132 61.5409 29.3392 61.3887 29.4265L49.9104 36.0351V49.1337C49.9104 49.4902 49.7209 49.8192 49.4118 49.9987L25.4519 63.7916C25.3971 63.8227 25.3372 63.8427 25.2774 63.8639C25.255 63.8714 25.2338 63.8851 25.2101 63.8913C25.0426 63.9354 24.8666 63.9354 24.6991 63.8913C24.6716 63.8838 24.6467 63.8689 24.6205 63.8589C24.5657 63.8389 24.5084 63.8215 24.456 63.7916L0.501061 49.9987C0.348882 49.9113 0.222437 49.7853 0.134469 49.6334C0.0465019 49.4816 0.000120578 49.3092 0 49.1337L0 8.10652C0 8.01678 0.0124642 7.92953 0.0348998 7.84477C0.0423783 7.8161 0.0598282 7.78993 0.0697995 7.76126C0.0884958 7.70891 0.105946 7.65531 0.133367 7.6067C0.152063 7.5743 0.179485 7.54812 0.20192 7.51821C0.230588 7.47832 0.256763 7.43719 0.290416 7.40229C0.319084 7.37362 0.356476 7.35243 0.388883 7.32751C0.425029 7.29759 0.457436 7.26518 0.498568 7.2415L12.4779 0.345059C12.6296 0.257786 12.8015 0.211853 12.9765 0.211853C13.1515 0.211853 13.3234 0.257786 13.475 0.345059L25.4531 7.2415H25.4556C25.4955 7.26643 25.5292 7.29759 25.5653 7.32626C25.5977 7.35119 25.6339 7.37362 25.6625 7.40104C25.6974 7.43719 25.7224 7.47832 25.7523 7.51821C25.7735 7.54812 25.8021 7.5743 25.8196 7.6067C25.8483 7.65656 25.8645 7.70891 25.8844 7.76126C25.8944 7.78993 25.9118 7.8161 25.9193 7.84602C25.9423 7.93096 25.954 8.01853 25.9542 8.10652V33.7317L35.9355 27.9844V14.8846C35.9355 14.7973 35.948 14.7088 35.9704 14.6253C35.9792 14.5954 35.9954 14.5692 36.0053 14.5405C36.0253 14.4882 36.0427 14.4346 36.0702 14.386C36.0888 14.3536 36.1163 14.3274 36.1375 14.2975C36.1674 14.2576 36.1923 14.2165 36.2272 14.1816C36.2559 14.1529 36.292 14.1317 36.3244 14.1068C36.3618 14.0769 36.3942 14.0445 36.4341 14.0208L48.4147 7.12434C48.5663 7.03694 48.7383 6.99094 48.9133 6.99094C49.0883 6.99094 49.2602 7.03694 49.4118 7.12434L61.3899 14.0208C61.4323 14.0457 61.4647 14.0769 61.5021 14.1055C61.5333 14.1305 61.5694 14.1529 61.5981 14.1803C61.633 14.2165 61.6579 14.2576 61.6878 14.2975C61.7103 14.3274 61.7377 14.3536 61.7551 14.386C61.7838 14.4346 61.8 14.4882 61.8199 14.5405C61.8312 14.5692 61.8474 14.5954 61.8548 14.6253ZM59.893 27.9844V16.6121L55.7013 19.0252L49.9104 22.3593V33.7317L59.8942 27.9844H59.893ZM47.9149 48.5566V37.1768L42.2187 40.4299L25.953 49.7133V61.2003L47.9149 48.5566ZM1.99677 9.83281V48.5566L23.9562 61.199V49.7145L12.4841 43.2219L12.4804 43.2194L12.4754 43.2169C12.4368 43.1945 12.4044 43.1621 12.3682 43.1347C12.3371 43.1097 12.3009 43.0898 12.2735 43.0624L12.271 43.0586C12.2386 43.0275 12.2162 42.9888 12.1887 42.9539C12.1638 42.9203 12.1339 42.8916 12.114 42.8567L12.1127 42.853C12.0903 42.8156 12.0766 42.7707 12.0604 42.7283C12.0442 42.6909 12.023 42.656 12.013 42.6161C12.0005 42.5688 11.998 42.5177 11.9931 42.4691C11.9881 42.4317 11.9781 42.3943 11.9781 42.3569V15.5801L6.18848 12.2446L1.99677 9.83281ZM12.9777 2.36177L2.99764 8.10652L12.9752 13.8513L22.9541 8.10527L12.9752 2.36177H12.9777ZM18.1678 38.2138L23.9574 34.8809V9.83281L19.7657 12.2459L13.9749 15.5801V40.6281L18.1678 38.2138ZM48.9133 9.14105L38.9344 14.8858L48.9133 20.6305L58.8909 14.8846L48.9133 9.14105ZM47.9149 22.3593L42.124 19.0252L37.9323 16.6121V27.9844L43.7219 31.3174L47.9149 33.7317V22.3593ZM24.9533 47.987L39.59 39.631L46.9065 35.4555L36.9352 29.7145L25.4544 36.3242L14.9907 42.3482L24.9533 47.987Z" />
    </svg>
    <p className="font-medium mt-2">Laravel</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/gatsby">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>Gatsby</title>
      <path d="M12 0C5.4 0 0 5.4 0 12s5.4 12 12 12 12-5.4 12-12S18.6 0 12 0zm0 2.571c3.171 0 5.915 1.543 7.629 3.858l-1.286 1.115C16.886 5.572 14.571 4.286 12 4.286c-3.343 0-6.171 2.143-7.286 5.143l9.857 9.857c2.486-.857 4.373-3 4.973-5.572h-4.115V12h6c0 4.457-3.172 8.228-7.372 9.17L2.83 9.944C3.772 5.743 7.543 2.57 12 2.57zm-9.429 9.6l9.344 9.258c-2.4-.086-4.801-.943-6.601-2.743-1.8-1.8-2.743-4.201-2.743-6.515z" />
    </svg>
    <p className="font-medium mt-2">Gatsby</p>
  </LinkedCard>
  <LinkedCard href="/docs/installation/manual">
    <svg
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
      className="w-10 h-10"
      fill="currentColor"
    >
      <title>React</title>
      <path d="M14.23 12.004a2.236 2.236 0 0 1-2.235 2.236 2.236 2.236 0 0 1-2.236-2.236 2.236 2.236 0 0 1 2.235-2.236 2.236 2.236 0 0 1 2.236 2.236zm2.648-10.69c-1.346 0-3.107.96-4.888 2.622-1.78-1.653-3.542-2.602-4.887-2.602-.41 0-.783.093-1.106.278-1.375.793-1.683 3.264-.973 6.365C1.98 8.917 0 10.42 0 12.004c0 1.59 1.99 3.097 5.043 4.03-.704 3.113-.39 5.588.988 6.38.32.187.69.275 1.102.275 1.345 0 3.107-.96 4.888-2.624 1.78 1.654 3.542 2.603 4.887 2.603.41 0 .783-.09 1.106-.275 1.374-.792 1.683-3.263.973-6.365C22.02 15.096 24 13.59 24 12.004c0-1.59-1.99-3.097-5.043-4.032.704-3.11.39-5.587-.988-6.38-.318-.184-.688-.277-1.092-.278zm-.005 1.09v.006c.225 0 .406.044.558.127.666.382.955 1.835.73 3.704-.054.46-.142.945-.25 1.44-.96-.236-2.006-.417-3.107-.534-.66-.905-1.345-1.727-2.035-2.447 1.592-1.48 3.087-2.292 4.105-2.295zm-9.77.02c1.012 0 2.514.808 4.11 2.28-.686.72-1.37 1.537-2.02 2.442-1.107.117-2.154.298-3.113.538-.112-.49-.195-.964-.254-1.42-.23-1.868.054-3.32.714-3.707.19-.09.4-.127.563-.132zm4.882 3.05c.455.468.91.992 1.36 1.564-.44-.02-.89-.034-1.345-.034-.46 0-.915.01-1.36.034.44-.572.895-1.096 1.345-1.565zM12 8.1c.74 0 1.477.034 2.202.093.406.582.802 1.203 1.183 1.86.372.64.71 1.29 1.018 1.946-.308.655-.646 1.31-1.013 1.95-.38.66-.773 1.288-1.18 1.87-.728.063-1.466.098-2.21.098-.74 0-1.477-.035-2.202-.093-.406-.582-.802-1.204-1.183-1.86-.372-.64-.71-1.29-1.018-1.946.303-.657.646-1.313 1.013-1.954.38-.66.773-1.286 1.18-1.868.728-.064 1.466-.098 2.21-.098zm-3.635.254c-.24.377-.48.763-.704 1.16-.225.39-.435.782-.635 1.174-.265-.656-.49-1.31-.676-1.947.64-.15 1.315-.283 2.015-.386zm7.26 0c.695.103 1.365.23 2.006.387-.18.632-.405 1.282-.66 1.933-.2-.39-.41-.783-.64-1.174-.225-.392-.465-.774-.705-1.146zm3.063.675c.484.15.944.317 1.375.498 1.732.74 2.852 1.708 2.852 2.476-.005.768-1.125 1.74-2.857 2.475-.42.18-.88.342-1.355.493-.28-.958-.646-1.956-1.1-2.98.45-1.017.81-2.01 1.085-2.964zm-13.395.004c.278.96.645 1.957 1.1 2.98-.45 1.017-.812 2.01-1.086 2.964-.484-.15-.944-.318-1.37-.5-1.732-.737-2.852-1.706-2.852-2.474 0-.768 1.12-1.742 2.852-2.476.42-.18.88-.342 1.356-.494zm11.678 4.28c.265.657.49 1.312.676 1.948-.64.157-1.316.29-2.016.39.24-.375.48-.762.705-1.158.225-.39.435-.788.636-1.18zm-9.945.02c.2.392.41.783.64 1.175.23.39.465.772.705 1.143-.695-.102-1.365-.23-2.006-.386.18-.63.406-1.282.66-1.933zM17.92 16.32c.112.493.2.968.254 1.423.23 1.868-.054 3.32-.714 3.708-.147.09-.338.128-.563.128-1.012 0-2.514-.807-4.11-2.28.686-.72 1.37-1.536 2.02-2.44 1.107-.118 2.154-.3 3.113-.54zm-11.83.01c.96.234 2.006.415 3.107.532.66.905 1.345 1.727 2.035 2.446-1.595 1.483-3.092 2.295-4.11 2.295-.22-.005-.406-.05-.553-.132-.666-.38-.955-1.834-.73-3.703.054-.46.142-.944.25-1.438zm4.56.64c.44.02.89.034 1.345.034.46 0 .915-.01 1.36-.034-.44.572-.895 1.095-1.345 1.565-.455-.47-.91-.993-1.36-1.565z" />
    </svg>
    <p className="font-medium mt-2">Manual</p>
  </LinkedCard>
</div>

## TypeScript

This project and the components are written in TypeScript. We recommend using TypeScript for your project as well.

However we provide a JavaScript version of the components as well. The JavaScript version is available via the [cli](/docs/cli).

To opt-out of TypeScript, you can use the `tsx` flag in your `components.json` file.

```json {10} title="components.json"
{
  "style": "default",
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "src/app/globals.css",
    "baseColor": "zinc",
    "cssVariables": true
  },
  "rsc": false,
  "tsx": false,
  "aliases": {
    "utils": "~/lib/utils",
    "components": "~/components"
  }
}
```

To configure import aliases, you can use the following `jsconfig.json`:

```json {4} title="jsconfig.json"
{
  "compilerOptions": {
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```

```

### 📄 installation/laravel.mdx

```
---
title: Laravel
description: Install and configure Laravel with Inertia
---

<Steps>

### Create project

Start by creating a new Laravel project with Inertia and React using the laravel installer `laravel new my-app`:

```bash
laravel new my-app --typescript --breeze --stack=react --git --no-interaction
```

### Run the CLI

Run the `shadcn` init command to setup your project:

```bash
npx shadcn@latest init
```

### Configure components.json

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use?
Which color would you like to use as base color?
Do you want to use CSS variables for colors? › yes
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```tsx {1,6} showLineNumbers
import { Button } from "@/Components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

</Steps>

```

### 📄 installation/manual.mdx

```
---
title: Manual Installation
description: Add dependencies to your project manually.
---

<Steps>

### Add Tailwind CSS

Components are styled using Tailwind CSS. You need to install Tailwind CSS in your project.

[Follow the Tailwind CSS installation instructions to get started.](https://tailwindcss.com/docs/installation)

### Add dependencies

Add the following dependencies to your project:

```bash
npm install tailwindcss-animate class-variance-authority clsx tailwind-merge lucide-react
```

### Configure path aliases

Configure the path aliases in your `tsconfig.json` file.

```json {3-6} title="tsconfig.json" showLineNumbers
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```

The `@` alias is a preference. You can use other aliases if you want.

### Configure tailwind.config.js

Here's what my `tailwind.config.js` file looks like:

```js title="tailwind.config.js"
/** @type {import('tailwindcss').Config} */
module.exports = {
  darkMode: ["class"],
  content: ["app/**/*.{ts,tsx}", "components/**/*.{ts,tsx}"],
  theme: {
    extend: {
      colors: {
        border: "hsl(var(--border))",
        input: "hsl(var(--input))",
        ring: "hsl(var(--ring))",
        background: "hsl(var(--background))",
        foreground: "hsl(var(--foreground))",
        primary: {
          DEFAULT: "hsl(var(--primary))",
          foreground: "hsl(var(--primary-foreground))",
        },
        secondary: {
          DEFAULT: "hsl(var(--secondary))",
          foreground: "hsl(var(--secondary-foreground))",
        },
        destructive: {
          DEFAULT: "hsl(var(--destructive))",
          foreground: "hsl(var(--destructive-foreground))",
        },
        muted: {
          DEFAULT: "hsl(var(--muted))",
          foreground: "hsl(var(--muted-foreground))",
        },
        accent: {
          DEFAULT: "hsl(var(--accent))",
          foreground: "hsl(var(--accent-foreground))",
        },
        popover: {
          DEFAULT: "hsl(var(--popover))",
          foreground: "hsl(var(--popover-foreground))",
        },
        card: {
          DEFAULT: "hsl(var(--card))",
          foreground: "hsl(var(--card-foreground))",
        },
      },
      borderRadius: {
        lg: `var(--radius)`,
        md: `calc(var(--radius) - 2px)`,
        sm: "calc(var(--radius) - 4px)",
      },
    },
  },
  plugins: [require("tailwindcss-animate")],
}
```

### Configure styles

Add the following to your styles/globals.css file. You can learn more about using CSS variables for theming in the [theming section](/docs/theming).

```css title="globals.css"
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --background: 0 0% 100%;
    --foreground: 222.2 47.4% 11.2%;
    --muted: 210 40% 96.1%;
    --muted-foreground: 215.4 16.3% 46.9%;
    --popover: 0 0% 100%;
    --popover-foreground: 222.2 47.4% 11.2%;
    --border: 214.3 31.8% 91.4%;
    --input: 214.3 31.8% 91.4%;
    --card: 0 0% 100%;
    --card-foreground: 222.2 47.4% 11.2%;
    --primary: 222.2 47.4% 11.2%;
    --primary-foreground: 210 40% 98%;
    --secondary: 210 40% 96.1%;
    --secondary-foreground: 222.2 47.4% 11.2%;
    --accent: 210 40% 96.1%;
    --accent-foreground: 222.2 47.4% 11.2%;
    --destructive: 0 100% 50%;
    --destructive-foreground: 210 40% 98%;
    --ring: 215 20.2% 65.1%;
    --radius: 0.5rem;
  }

  .dark {
    --background: 224 71% 4%;
    --foreground: 213 31% 91%;
    --muted: 223 47% 11%;
    --muted-foreground: 215.4 16.3% 56.9%;
    --accent: 216 34% 17%;
    --accent-foreground: 210 40% 98%;
    --popover: 224 71% 4%;
    --popover-foreground: 215 20.2% 65.1%;
    --border: 216 34% 17%;
    --input: 216 34% 17%;
    --card: 224 71% 4%;
    --card-foreground: 213 31% 91%;
    --primary: 210 40% 98%;
    --primary-foreground: 222.2 47.4% 1.2%;
    --secondary: 222.2 47.4% 11.2%;
    --secondary-foreground: 210 40% 98%;
    --destructive: 0 63% 31%;
    --destructive-foreground: 210 40% 98%;
    --ring: 216 34% 17%;
  }
}

@layer base {
  * {
    @apply border-border;
  }
  body {
    @apply font-sans antialiased bg-background text-foreground;
  }
}
```

### Add a cn helper

```ts title="lib/utils.ts" showLineNumbers
import { clsx, type ClassValue } from "clsx"
import { twMerge } from "tailwind-merge"

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```

### Create a `components.json` file

Create a `components.json` file in the root of your project.

```json title="components.json" showLineNumbers
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": false,
  "tsx": true,
  "tailwind": {
    "config": "tailwind.config.js",
    "css": "src/index.css",
    "baseColor": "zinc",
    "cssVariables": true,
    "prefix": ""
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  },
  "iconLibrary": "lucide"
}
```

### That's it

You can now start adding components to your project.

</Steps>

```

### 📄 installation/next.mdx

```
---
title: Next.js
description: Install and configure Next.js.
---

<Callout>

**If you're using Next.js 15, see the [Next.js 15 + React 19](/docs/react-19) guide.**

</Callout>

<Steps>

### Create project

Run the `init` command to create a new Next.js project or to setup an existing one:

```bash
npx shadcn@latest init
```

<Callout className="mt-4">

You can use the `-d` flag for defaults i.e `new-york`, `zinc` and `yes` for the css variables.

```bash
npx shadcn@latest init -d
```

</Callout>

### Configure components.json

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use? › New York
Which color would you like to use as base color? › Zinc
Do you want to use CSS variables for colors? › no / yes
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```tsx {1,6} showLineNumbers
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

</Steps>

```

### 📄 installation/remix.mdx

```
---
title: Remix
description: Install and configure Remix.
---

<Steps>

### Create project

Start by creating a new Remix project using `create-remix`:

```bash
npx create-remix@latest my-app
```

### Run the CLI

Run the `shadcn-ui` init command to setup your project:

```bash
npx shadcn@latest init
```

### Configure components.json

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use? › New York
Which color would you like to use as base color? › Zinc
Do you want to use CSS variables for colors? › no / yes
```

### App structure

<Callout>

**Note**: This app structure is only a suggestion. You can place the files wherever you want.

</Callout>

- Place the UI components in the `app/components/ui` folder.
- Your own components can be placed in the `app/components` folder.
- The `app/lib` folder contains all the utility functions. We have a `utils.ts` where we define the `cn` helper.
- The `app/tailwind.css` file contains the global CSS.

### Install Tailwind CSS

```bash
npm install -D tailwindcss@latest autoprefixer@latest
```

Then we create a `postcss.config.js` file:

```js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

And finally we add the following to our `remix.config.js` file:

```js {4-5}
/** @type {import('@remix-run/dev').AppConfig} */
export default {
  ...
  tailwind: true,
  postcss: true,
  ...
};
```

### Add `tailwind.css` to your app

In your `app/root.tsx` file, import the `tailwind.css` file:

```js {1, 4}
import styles from "./tailwind.css?url"

export const links: LinksFunction = () => [
  { rel: "stylesheet", href: styles },
  ...(cssBundleHref ? [{ rel: "stylesheet", href: cssBundleHref }] : []),
]
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```tsx {1,6} showLineNumbers
import { Button } from "~/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

</Steps>

```

### 📄 installation/vite.mdx

```
---
title: Vite
description: Install and configure Vite.
---

<Steps>

### Create project

Start by creating a new React project using `vite`:

```bash
npm create vite@latest
```

### Add Tailwind and its configuration

Install `tailwindcss` and its peer dependencies, then generate your `tailwind.config.js` and `postcss.config.js` files:

```bash
npm install -D tailwindcss postcss autoprefixer
```

```bash
npx tailwindcss init -p
```

Add this import header in your main css file, `src/index.css` in our case:

```css {1-3} showLineNumbers
@tailwind base;
@tailwind components;
@tailwind utilities;

/* ... */
```

Configure the tailwind template paths in `tailwind.config.js`:

```js {3}
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./index.html", "./src/**/*.{ts,tsx,js,jsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### Edit tsconfig.json file

The current version of Vite splits TypeScript configuration into three files, two of which need to be edited.
Add the `baseUrl` and `paths` properties to the `compilerOptions` section of the `tsconfig.json` and
`tsconfig.app.json` files:

```ts {11-16} showLineNumbers
{
  "files": [],
  "references": [
    {
      "path": "./tsconfig.app.json"
    },
    {
      "path": "./tsconfig.node.json"
    }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

### Edit tsconfig.app.json file

Add the following code to the `tsconfig.app.json` file to resolve paths, for your IDE:

```ts {4-9} showLineNumbers
{
  "compilerOptions": {
    // ...
    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
    // ...
  }
}
```

### Update vite.config.ts

Add the following code to the vite.config.ts so your app can resolve paths without error:

```bash
npm install -D @types/node
```

```typescript
import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})
```

### Run the CLI

Run the `shadcn-ui` init command to setup your project:

```bash
npx shadcn@latest init
```

### Configure components.json

You will be asked a few questions to configure `components.json`:

```txt showLineNumbers
Which style would you like to use? › New York
Which color would you like to use as base color? › Zinc
Do you want to use CSS variables for colors? › no / yes
```

### That's it

You can now start adding components to your project.

```bash
npx shadcn@latest add button
```

The command above will add the `Button` component to your project. You can then import it like this:

```tsx {1,6} showLineNumbers
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}
```

</Steps>

```

