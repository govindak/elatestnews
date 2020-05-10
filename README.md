# elatestnews.com


# Using yarn
yarn setup:yarn

# Using npm
npm run setup:npm
```

### Scaffold your project

This command will launch both of your backend and frontend servers and do a data migration in your backend server

```bash
# Using yarn
yarn build:yarn
yarn develop:yarn

# Using npm
npm run build:npm
npm run develop:npm
```

Alternatively, you can still start your servers separately:

### Start the backend server

```bash
cd backend

# Using yarn
yarn build
yarn seed
yarn develop

# Using npm
npm run build
npm run seed
npm run develop
```

### Start the frontend server

```bash
cd frontend

# Using yarn
yarn develop

# Using npm
npm run develop
```

Gatsby server is running here => [http://localhost:8000](http://localhost:8000)
Strapi server is running here => [http://localhost:1337](http://localhost:1337)

## Gatsby Cloud

You may want to deploy this starter frontend on [Gatsby Cloud](https://www.gatsbyjs.com/dashboard) in order to try the Gatsby Preview maybe!

- Fork this starter on your own Github account
- Create a new site by choosing the option "I already have a Gatsby site"

![Create a New site](/medias/create-a-new-site.png)

You'll be asked to select the repository you want to use

- Select your new Strapi Starter Gatsby Blog repository you just forked and specify the Gatsby project folder which is `frontend` in this starter

![Repository](/medias/repository.png)

- You can then copy the webhook url and skip this step

![Skip step](/medias/skip.png)

- Paste your Strapi `API_URL` for both of your `Builds Environment variables` and `Preview Environment variables` (we consider that you deployed your strapi server)

![Env](/medias/env.png)

Now you'll need to create a Webhook on your strapi server in order to tell Gatsby cloud to build your Gatsby project each time your create/update/delete content

- Open your Strapi admin panel and go to [Webhooks](http://localhost:1337/admin/settings/webhooks)
- Create a new Webhook with following properties:
  - Name: `Gatsby Cloud`
  - Url: The first Webhook Url Gatsby Cloud provide in your Gatsby Dashboard Sites. It should be something like this: `https://webhook.gatsbyjs.com/hooks/data_source/` without the `/publish/`
  - Check every Events for `Entry` and `Media`

That's it! Now Strapi will inform Gatsby Cloud to build your Gatsby project everytime you create/update/delete content

![Env](/medias/gif.gif)

Enjoy this starter
