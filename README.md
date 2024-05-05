## Next.js App Router Course - Starter

- **`/app`**: Contains all the routes, components, and logic for your application, this is where you'll be mostly working from.
- **`/app/lib`**: Contains functions used in your application, such as reusable utility functions and data fetching functions.
- **`/app/ui`**: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.
- **`/public`**: Contains all the static assets for your application, such as images.
- **`/scripts`**: Contains a seeding script that you'll use to populate your database in a later chapter.
- **Config Files**: You'll also notice config files such as next.config.js at the root of your application. Most of these files are created and pre-configured when you start a new project using create-next-app. You will not need to modify them in this course.

## Commands
- `npx create-next-app@latest nextjs-dashboard --use-npm --example "https://github.com/vercel/next-learn/tree/main/dashboard/starter-example"`
- `cd nextjs-dashboard`
- `npm i`
- `npm run dev`

## Styling
- **Tailwind**
  - Tailwind is a CSS framework that speeds up the development process by allowing you to quickly write utility classes directly in your TSX markup.
- **CSS module**
  - CSS Modules allow you to scope CSS to a component by automatically creating unique class names, so you don't have to worry about style collisions as well.
- **Using the clsx library to toggle class names**
  - `clsx` is a library that lets you toggle class names easily
  
  ```tsx
  import clsx from 'clsx';
  export default function InvoiceStatus({ status }: { status: string }) {
    return (
      <span
        className={clsx(
          'inline-flex items-center rounded-full px-2 py-1 text-sm',
          {
            'bg-gray-100 text-gray-500': status === 'pending',
            'bg-green-500 text-white': status === 'paid',
          },
        )}
      >
      // ...
  )}
  ```

## Optimizing Fonts and Images
- Next.js automatically optimizes fonts in the application when you use the next/font module. It downloads font files at build time and hosts them with your other static assets. This means when a user visits your application, there are no additional network requests for fonts which would impact performance.
- This means when a user visits your application, there are no additional network requests for fonts which would impact performance.
- Images without dimensions and web fonts are common causes of layout shift due to the browser having to download additional resources.

### Why optimize images?

Next.js can serve static assets, like images, under the top-level `/public` folder. Files inside `/public` can be referenced in your application.

With regular HTML, you would add an image as follows:

```html
<img
  src="/hero.png"
  alt="Screenshots of the dashboard project showing desktop version"
/>
```

However, this means you have to manually:

- Ensure your image is responsive on different screen sizes.
- Specify image sizes for different devices.
- Prevent layout shift as the images load.
- Lazy load images that are outside the user's viewport.

Image Optimization is a large topic in web development that could be considered a specialization in itself. Instead of manually implementing these optimizations, you can use the `<Image>` component to automatically optimize your images.

#### The `<Image>` component

The `<Image>` Component is an extension of the HTML `<img>` tag, and comes with automatic image optimization, such as:

- Preventing layout shift automatically when images are loading.
- Resizing images to avoid shipping large images to devices with a smaller viewport.
- Lazy loading images by default (images load as they enter the viewport).
- Serving images in modern formats, like WebP and AVIF, when the browser supports it.

## Navigation
- Automatic code-splitting and prefetching
  - To improve the navigation experience, Next.js automatically code splits your application by route segments. This is different from a traditional React SPA, where the browser loads all your application code on initial load.
  - Splitting code by routes means that pages become isolated. If a certain page throws an error, the rest of the application will still work.
  - Furthermore, in production, whenever `<Link>` components appear in the browser's viewport, Next.js automatically prefetches the code for the linked route in the background. By the time the user clicks the link, the code for the destination page will already be loaded in the background, and this is what makes the page transition near-instant!

## Code Stacks
- NextJS
- Typescript (Javascript) VueJS + ReactJS
- ReactJS + React Hooks + Redux
- Server, Backend: NodeJS Express
- JSon Web Token, Cookie, Search, Pagination, Handle File Upload, Avatar
- 

2. Các bước thực hiện:
- Cài đặt git: https://git-scm.com
- Tạo tài khoản github: https://github.com/signup
- Tạo repository trên github
- git init
- git add .
- git commit -m "first commit"
- Tạo personal access token trên github setting
- Thay token, username và repo vào: git remote set-url origin https://<username>:<personal-access-token>@github.com/<user>/<your-repo>.git
- git push -u origin main
- Đăng nhập github tại máy
- Đẩy sourcecode lên github
