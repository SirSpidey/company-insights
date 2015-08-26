# Company Insights powered by IBM Watson

See the "personality" of your companies twitter feed and compare it to your competitors. 
Also see where you're mentioned in the news and what others are saying about you.


# Local Setup

Requires [Node.js] and [Bower]. 
Grab a copy of the code and install the dependencies:

```sh
npm install
npm install --global bower gulp
bower install
```

Next create your API keys for [Twitter], [AlchemyAPI], and [Personality Insights].

For private projects, the simplest option is to put your API keys directly in `config.js`.
For public projects, either store them in environment variables, or alternatively, create a file named `.env` like so:

```
ALCHEMY_AIP_KEY=<api_key>

PERSONALITY_INSIGHTS_USERNAME=<username>
PERSONALITY_INSIGHTS_PASSWORD=<password>

TWITTER_CONSUMER_KEY=<consumer_key>
TWITTER_CONSUMER_SECRET=<consumer_secret>
TWITTER_ACCESS_TOKEN_KEY=<access_token_key>
TWITTER_ACCESS_TOKEN_SECRET=<access_token_secret>
```
  
Finally, run `gulp` to start compile the front-end assets and start app:

```sh
gulp
```

## Deploying to Bluemix

** todo: add a one-click deploy-to-bluemix button, make sure gulp runs on bluemix **

Install the [Cloud Foundry] [`cf` command line tool] and edit `manifest.yml` to have a unique name and domain/subdomain.
Then run

```sh
cf push
```

Next set your [AlchemyAPI] and [Twitter] keys:

```sh
cf set-env <app name from manifest.yml> ALCHEMY_AIP_KEY <api_key>
cf set-env <app name from manifest.yml> TWITTER_CONSUMER_KEY <consumer_key>
cf set-env <app name from manifest.yml> TWITTER_CONSUMER_SECRET <consumer_secret>
cf set-env <app name from manifest.yml> TWITTER_ACCESS_TOKEN_KEY <access_token_key>
cf set-env <app name from manifest.yml> TWITTER_ACCESS_TOKEN_SECRET <access_token_secret>
```

[Node.js]: https://nodejs.org/
[Bower]: http://bower.io/
[Twitter]: https://apps.twitter.com/
[AlchemyAPI]: http://www.alchemyapi.com/api/register.html
[Personality Insights]: https://www.ibm.com/smarterplanet/us/en/ibmwatson/developercloud/doc/getting_started/gs-credentials.shtml
[Cloud Foundry]: https://www.cloudfoundry.org/
[`cf` command line tool]: https://github.com/cloudfoundry/cli/releases
