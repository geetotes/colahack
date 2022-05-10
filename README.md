# Colahack Cloudflare Workers Boilerplate

This is a boilerplate static HTML site for Cloudflare workers. It has continous integration provided by Github actions and is designed to be easy to fork and set up your own static html site through cloudflare workers.

The site served from here is the homepage of [Cola Hack Night](https://colahack.com), located at `colahack.com`

## Development

This site uses Cloudflare's [wranger])https://www.npmjs.com/package/@cloudflare/wrangler) tool. Run the development environment with

```
wrangler dev
```

And open [http://localhost:8787/](http://localhost:8787/) to preview the site.

## Deployment

This project uses Github actions to automaticlly deploy changes.


## To make your own

### Update Cloudflare Credentials

1) Update the Zone ID and Account ID in `wrangler.toml` to your own. [This file is ok to check into source control.](https://github.com/cloudflare/wrangler/issues/209#issuecomment-541654484). You can find your zone id [here](https://developers.cloudflare.com/workers/get-started/guide/#:~:text=You%20can%20get%20your%20zone_id,Zone%20ID%20on%20the%20right.)
2) In your forked repository's **Settings -> Secrets -> Actions**, add your own `CF_API_TOKEN` (your cloudflare API token) as a repository secret. This allows the Github _Deploy_ Action to run sucessfully to your worker. To create your Cloudflare API token, click on **API Tokens -> Create Token** in Cloudflarew and use the Edit Cloudflare Workers template.
3) In `wrangler.toml`, update your routes from `colahack.com`

After you've updated the cloudflare credentials and made the HTML your own, making and commit and pushing it to the `master` branch will trigger a deployment to cloudflare workers.