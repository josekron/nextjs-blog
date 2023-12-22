## Nextjs Tutorial - Blog

I took some notes when following the [tutorial](https://nextjs.org/learn/basics/create-nextjs-app). 

I had previous knowledge about Nodejs and Reactjs so the notes are mostly new concepts from Nextjs.

## Notes

### Create a Next.js app

```npx create-next-app@latest nextjs-blog --use-npm --example "https://github.com/vercel/next-learn/tree/main/basics/learn-starter"```

```npm run dev```

### Pages

[Docs](https://nextjs.org/docs/pages/building-your-application/routing)

Next.js automatically optimizes your application for the best performance by code splitting, client-side navigation, and prefetching (in production).

* A page is a React Component.
* Pages are associated with a route based on their file name.

* `pages/index.js` is associated with the `/route`.
* `pages/posts/first-post.js` is associated with the `/posts/first-post` route.

* `next/link`: enables client-side navigation between pages and accepts props for the navigation behaviour.

[Docs about Link](https://nextjs.org/docs/pages/api-reference/components/link)


### Styling and static files

[Docs](https://nextjs.org/docs/pages/building-your-application/styling)

* `CSS Modules`: locally score CSS at the component-level buy automatically creating unique class names.
* `Alternatives to CSS Modules`: Sass, Tailwind CSS, styled-components.

* `Global CSS files`: only inside `pages/_app.js` to add some CSS to be loaded by every page.

* Images in: `Public/images/`
* `Next/image`: an extension of the HTML <image> element that ensure the image is responsive and optimise it.

* Tips (clsx for toggle class names and Tailwind): https://nextjs.org/learn-pages-router/basics/assets-metadata-css/styling-tips

### Pre-rendering and Data Fetching

[Docs](https://nextjs.org/docs/pages/building-your-application/routing)

By default, Next.js pre-renders the HTML of every page.

* `Static Generation`: is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request. It can be done with and without data.

`Function getStaticProps`: fetch external data and send it as props to the page.

* `Server-side Rendering`: is the pre-rendering method that generates the HTML on each request.

`Function getServerSideProps`: is called at request time so its parameter (context) contains request specific parameters.

```You should ask yourself: "Can I pre-render this page ahead of a user's request?" If the answer is yes, then you should choose Static Generation.```

* `Client-side Rendering`: If you do not need to pre-render the data. For internal dashboards that SEO is not relevant.

`SWR`: new React hook for data fetching on the client side: https://swr.vercel.app/ 

### Dynamic Routes

The case where each page path depends on external data.

[Docs](https://nextjs.org/docs/pages/building-your-application/routing/dynamic-routes)

Pages that begin with [ and end with ] are dynamic routes in Next.js.

* Tips (examples, fallback, catch-all routes, custom 404 page): https://nextjs.org/learn-pages-router/basics/dynamic-routes/dynamic-routes-details

### API Routes

An API endpoint as a Node.js serverless function.

[Docs](https://nextjs.org/docs/pages/building-your-application/routing/api-routes)

```
In pages/api:export default function handler(req, res) {
  res.status(200).json({ text: 'Hello' });
}
```

* `Dynamic API Routes`: https://nextjs.org/docs/pages/building-your-application/routing/api-routes#dynamic-api-routes













