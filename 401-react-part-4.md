## REACT Part 4

Notes on Next.js [dynamic routes](https://nextjs.org/learn/basics/dynamic-routes)

- How to statically generate pages with dynamic routes using getStaticPaths.
- How to write getStaticProps to fetch the data for each blog post.
- How to render markdown using remark.
- How to pretty-print date strings.
- How to link to a page with dynamic routes.
- Some useful information on dynamic routes.


Notes on Next.js[deployment](https://nextjs.org/learn/basics/deploying-nextjs-app)

- How to deploy your Next.js app to Vercel.
- The DPS Workflow: Develop, Preview, and Ship.
- How to deploy your Next.js app to your own hosting provider.

Also look at [static file serving](https://nextjs.org/docs/basic-features/static-file-serving)

Next.js can serve static files, like images, under a folder called public in the root directory. Files inside public can then be referenced by your code starting from the base URL (/).

For example, if you add an image to public/me.png, the following code will access the image:
```
import Image from 'next/image'

function Avatar() {
  return <Image src="/me.png" alt="me" width="64" height="64" />
}

export default Avatar
```

Video on [Next.js 10](https://www.youtube.com/watch?v=JWCS5IdECVI)

