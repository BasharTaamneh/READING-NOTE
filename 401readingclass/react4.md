# Next.js - Dynamic Routes

## How to create dynamic routes in Next.js?

* What does that mean? Every Next.js project comes with a pages folder. The structure of the pages folder determines the structure of your routes and every file inside that folder maps to a route in your application.

Essentially, every time you want to create a route, you need to add a file in the pages folder. Keep in mind that the pages folder itself represents your root url (meaning /).

For static routing, you can create a new route by adding a index.js or a named file like about.js.

pages/index.js maps to /

pages/about.js maps to /about

Tip: For more info on how to create static routes (including nested routes), read my tutorial on static routing in Next.js.

But how does it work for dynamic routes? Say I wanted to create a blog, how would I add a route such as myblog.com/posts/:id?

Next.js handles dynamic routes by supporting brackets around parameters (e.g [id]) as a filename. Going back to my blog example, I would therefore create a [id].js file inside my posts folder.

As a result, /pages/posts/[id].js would map to /posts/[id] where id is the unique id of your post.

## Dynamic Nested Routes in Next.js


* Can I create dynamic nested routes? Say I wanted a page for comments related to a particular post, could I have a url such as /posts/[id]/[commentId]?

> The answer is Yes!

- For nested routes, you have to create a folder instead of a file. The syntax stays the same meaning that your folder would be called [id]. You can then add new routes inside. Here is the end result:

```
pages/
│   index.js -> url: /    
│
└───posts/
     |  index.js  -> url: /posts
     |
     └─── [id]/
             index.js       -> url: /posts/[id]
             commentId.js   -> url: /posts/[id]/[commentId]
```

## How to navigate to dynamic routes in Next.js?

Next.js offers a component called Link that allows for navigation between pages. This component accepts an href and wraps around a piece of code (say an anchor) to navigate to a page. Let's try it.

> Try #1:

```js
import Link from "next/link";

export default function Home() {
  return (
    <div>
      <h1>Welcome to my blog</h1>
      <div>
        <Link href="/posts/1">
          <a>Post #1</a>
        </Link>
      </div>
    </div>
  );
}
```

Straightforward, but hard-coded links are not very practical. I am going to create a separate posts object and use that to create my url.

> Try #2:

```js
import Link from "next/link";

const posts = [
  {
    id: 1,
    title: "Post #1"
  },
  {
    id: 2,
    title: "Post #2"
  }
];
export default function Home() {
  return (
    <div>
      <h1>Welcome to my blog</h1>
      {posts.map((post) => (
        <div key={`post-${post.id}`}>
          <Link href={`/posts/${encodeURIComponent(post.id)}`}>
            <a>{post.title}</a>
          </Link>
        </div>
      ))}
    </div>
  );
}
```

Better! But what if I update my route later? I will have to go through all my code and update all the links.

> Try #3:

```js
import Link from "next/link";

const ROUTE_POST_ID = "posts/[id]";
const posts = [
  {
    id: 1,
    title: "Post #1"
  },
  {
    id: 2,
    title: "Post #2"
  }
];
export default function Home() {
  return (
    <div>
      <h1>Welcome to my blog</h1>
      {posts.map((post) => (
        <div key={`post-${post.id}`}>
          <Link
            href={{
              pathname: ROUTE_POST_ID,
              query: { id: post.id }
            }}
          >
            <a>{post.title}</a>
          </Link>
        </div>
      ))}
    </div>
  );
}
```

What changed? Instead of an hard-coded url, the Link component can also accept an object for href.

This object contains two parameters pathname and query. The pathname is the route we want to navigate to (in our particular case, /posts/[id]) and the query which will contain all the data necessary for our dynamic route (like id).

The Link component takes those two and automatically formats it into the right url. That's much better!


## Access query parameters in your page


Can I access the parameters in my new page? In other words, when I get to /posts/[id], can I get the id part?

You can get all the information you need and more from the router itself. Simply, import useRouter and get the router object. The same way, we pass a query object for navigating query : { id: post.id }, we can retrieve it in our new page.

```js
import { useRouter } from "next/router";

export default function PostPage() {
  const router = useRouter();
  return <div>Post #{router.query.id}</div>;
}
```

Here is the end result:

![](https://mariestarck.com/content/images/2020/12/next-js-dynamic-routing.gif)


## Extra: Access your Next.js router and navigate with the useRouter hook


* Say you want to navigate to a new page other than through a link, for example by clicking a button, you can do this with the router. Remember the useRouter we used to get our query parameters? You can also use it to push a new page (or go back).

```js
import { useRouter } from "next/router";

const ROUTE_POST_ID = "posts/[id]";
const posts = [
  {
    id: 1,
    title: "Post #1"
  },
  {
    id: 2,
    title: "Post #2"
  }
];
export default function Home() {
  const router = useRouter();

  const navigate = (id) =>
    router.push({
      pathname: ROUTE_POST_ID,
      query: { id }
    });

  return (
    <div>
      <h1>Welcome to my blog</h1>
      {posts.map((post) => (
        <div key={`post-${post.id}`}>
          <button onClick={() => navigate(post.id)}>{post.title}</button>
        </div>
      ))}
    </div>
  );
}
```
## Extra: Access your Next.js router and navigate with the HOC withRouter

* Unfortunately, hooks don't work with class components (meaning components that extends React.Component). That's where the withRouter HOC comes in handy.

It will wrap around your class component and allow you to access the router through its props.

```js
import React from "react";
import { withRouter } from "next/router";

const ROUTE_POST_ID = "posts/[id]";
const posts = [
  {
    id: 1,
    title: "Post #1"
  },
  {
    id: 2,
    title: "Post #2"
  }
];
class Home extends React.Component {
  navigate = (id) =>
    this.props.router.push({
      pathname: ROUTE_POST_ID,
      query: { id }
    });

  render() {
    return (
      <div>
        <h1>Welcome to my blog</h1>
        {posts.map((post) => (
          <div key={`post-${post.id}`}>
            <button onClick={() => this.navigate(post.id)}>{post.title}</button>
          </div>
        ))}
      </div>
    );
  }
}
export default withRouter(Home);
```

There you go! I created a sandbox if you would like to see the complete code and play around with it a bit:[Next.js Dynamic Routing CodeSandbox.
](https://codesandbox.io/s/nextjs-dynamic-routing-bye86)

# Next.js - Deployment

**Push to GitHub**

Before we deploy, let’s push our Next.js app to GitHub if you haven’t done so already. This will make deployment easier.

On your personal GitHub account, create a new repository called nextjs-blog.
The repository can be public or private. You do not need to initialize it with a README or other files.
If you need help setting up your repo, take a look at this guide on GitHub.

> Then:

If you haven’t initialized the git repository locally for your Next.js app, do so now.
Push the Next.js app to your GitHub repository.
To push to GitHub, you can run the following commands (replace <username> with your GitHub username):

```
git remote add origin https://github.com/<username>/nextjs-blog.git
git push -u origin main
```

**Deploy to Vercel**

The easiest way to deploy Next.js to production is to use the Vercel platform developed by the creators of Next.js.

Vercel is a serverless platform for static and hybrid applications built to integrate with your headless content, commerce, or database. We make it easy for frontend teams to develop, preview, and ship delightful user experiences, where performance is the default. You can start using it for free — no credit card required.

**Create a Vercel Account**

First, go to https://vercel.com/signup to create a Vercel account. Choose Continue with GitHub and go through the sign up process.

**Import your nextjs-blog repository**

Once you’re signed up, import your nextjs-blog repository on Vercel. You can do so from here: https://vercel.com/import/git.

You’ll need to Install Vercel for GitHub. You can give it access to All Repositories.
Once you’ve installed Vercel, import nextjs-blog.
You can use default values for the following settings — no need to change anything. Vercel automatically detects that you have a Next.js app and chooses optimal build settings for you.

Project Name
Root Directory
Build Command
Output Directory
Development Command
When you deploy, your Next.js app will start building. It should finish in under a minute.



**Next.js and Vercel**


Vercel is made by the creators of Next.js and has first-class support for Next.js. When you deploy your Next.js app to Vercel, the following happens by default:

Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from the Vercel Edge Network, which is blazingly fast.
Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.
Vercel has many more features, such as:

Custom Domains: Once deployed on Vercel, you can assign a custom domain to your Next.js app. Take a look at our documentation here.
Environment Variables: You can also set environment variables on Vercel. Take a look at our documentation here. You can then use those environment variables in your Next.js app.
Automatic HTTPS: HTTPS is enabled by default (including custom domains) and doesn't require extra configuration. We auto-renew SSL certificates.
You can learn more about the platform in the Vercel documentation.

Preview Deployment for Every Push
The steps below are optional — you can try it or just read it through.

After deploying to Vercel, try doing the following if you can:

Create a new branch on your app.
Make some changes and push to GitHub.
Create a new pull request (GitHub help page).
You should see a comment by the vercel bot on the pull request page.

**Preview Deployment URL**

Try clicking on the Preview URL inside this comment. You should see the changes you just made.

When you have a pull request open, Vercel automatically creates a preview deployment for that branch on every push. The preview URL will always point to the latest preview deployment.

You can share this preview URL with your collaborators and get immediate feedback.

If your preview deployment looks good, merge it to main. When you do this, Vercel automatically creates a production deployment.

Develop, Preview, Ship
We’ve just gone through the workflow we call DPS: Develop, Preview, and Ship.

Develop: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.
Preview: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL. We can share this preview URL with others for feedback. In addition to doing code reviews, you can do deployment previews.
Ship: We’ve merged the pull request to main to ship to production.
We strongly recommend using this workflow when developing Next.js apps — it will help you iterate on your app faster.