# Authentication

## What is OAuth?

OAuth is an open-standard authorization protocol or framework that provides applications the ability for “secure designated access.” For example, you can tell Facebook that it’s OK for ESPN.com to access your profile or post updates to your timeline without having to give ESPN your Facebook password. This minimizes risk in a major way: In the event ESPN suffers a breach, your Facebook password remains safe.

OAuth doesn’t share password data but instead uses authorization tokens to prove an identity between consumers and service providers. OAuth is an authentication protocol that allows you to approve one application interacting with another on your behalf without giving away your password.

## Give an example of what using OAuth would look like

~~~
The simplest example of OAuth in action is one website saying “hey, do you want to log into our website with other website’s login?” In this scenario, the only thing the first website – let’s refer to that website as the consumer – wants to know is that the user is the same user on both websites and has logged in successfully to the service provider – which is the site the user initially logged into, not the consumer.

Facebook apps are a good OAuth use case example. Say you’re using an app on Facebook, and it asks you to share your profile and pictures. Facebook is, in this case, the service provider: it has your login data and your pictures. The app is the consumer, and as the user, you want to use the app to do something with your pictures. You specifically gave this app access to your pictures, which OAuth is managing in the background.

Your smart home devices – toaster, thermostat, security system, etc. – probably use some kind of login data to sync with each other and allow you to administer them from a browser or client device. These devices use what OAuth calls confidential authorization. That means they hold onto the secret key information, so you don’t have to log in over and over again.
~~~

## How does OAuth work? What are the steps that it takes to authenticate the user?

OAuth is about authorization and not authentication. Authorization is asking for permission to do stuff. Authentication is about proving you are the correct person because you know things. OAuth doesn’t pass authentication data between consumers and service providers – but instead acts as an authorization token of sorts.

The [common analogy](https://oauth.net/about/introduction/) I’ve seen used while researching OAuth is the valet key to your car. The valet key allows the valet to start and move the car but doesn’t give them access to the trunk or the glove box.

![example](https://blogvaronis2.wpengine.com/wp-content/uploads/2012/04/oauth-explained-960x584.png)

An OAuth token is like that valet key. As a user, you get to tell the consumers what they can use and what they can’t use from each service provider. You can give each consumer a different valet key. They never have the full key or any of the private data that gives them access to the full key.

- **How OAuth Works**

There are 3 main players in an OAuth transaction: the user, the consumer, and the service provider.  This triumvirate has been affectionately deemed the OAuth Love Triangle.

In our example, Joe is the user, Bitly is the consumer, and Twitter is the service provided who controls Joe’s secure resource (his Twitter stream).  Joe would like Bitly to be able to post shortened links to his stream.  Here’s how it works:

**Step 1** – The User Shows Intent

- Joe (User): “Hey, Bitly, I would like you to be able to post links directly to my Twitter stream.”
  
- Bitly (Consumer): “Great! Let me go ask for permission.”

**Step 2 –** The Consumer Gets Permission

- Bitly: “I have a user that would like me to post to his stream. Can I have a request token?”

- Twitter (Service Provider): “Sure.  Here’s a token and a secret.”

- The secret is used to prevent request forgery.  The consumer uses the secret to sign each request so that the service provider can verify it is actually coming from the consumer application.

**Step 3 –** The User Is Redirected to the Service Provider

- Bitly: “OK, Joe.  I’m sending you over to Twitter so you can approve.  Take this token with you.”

- Joe: “OK!” Bitly directs Joe to Twitter for authorization.

*This is the scary part. If Bitly were super-shady Evil Co. it could pop up a window that looked like Twitter but was really phishing for your username and password.  Always be sure to verify that the URL you’re directed to is actually the service provider (Twitter, in this case).*

**Step 4 –**The User Gives Permission

- Joe: “Twitter, I’d like to authorize this request token that Bitly gave me.”

- Twitter: “OK, just to be sure, you want to authorize Bitly to do X, Y, and Z with your Twitter account?”

- Joe: “Yes!”

- Twitter: “OK, you can go back to Bitly and tell them they have permission to use their request token.”

- Twitter marks the request token as “good-to-go,” so when the consumer requests access, it will be accepted (so long as it’s signed using their shared secret).

**Step 5 –** The Consumer Obtains an Access Token

- Bitly: “Twitter, can I exchange this request token for an access token?”
Twitter: “Sure.  Here’s your access token and secret.”

**Step 6 –** The Consumer Accesses the Protected Resource

- Bitly: “I’d like to post this link to Joe’s stream.  Here’s my access token!”
Twitter: “Done!”

*In our scenario, Joe never had to share his Twitter credentials with Bitly.  He simply delegated access using OAuth in a secure manner.  At any time, Joe can login to Twitter and review the access he has granted and revoke tokens for specific applications without affecting others.  OAuth also allows for granular permission levels.  You can give Bitly the right to post to your Twitter account, but restrict LinkedIn to read-only access.*


## What is OpenID?

OpenID allows you to use an existing account to sign in to multiple websites, without needing to create new passwords.

You may choose to associate information with your OpenID that can be shared with the websites you visit, such as a name or email address. With OpenID, you control how much of that information is shared with the websites you visit.

With OpenID, your password is only given to your identity provider, and that provider then confirms your identity to the websites you visit.  Other than your provider, no website ever sees your password, so you don’t need to worry about an unscrupulous or insecure website compromising your identity.

OpenID is rapidly gaining adoption on the web, with over one billion OpenID enabled user accounts and over 50,000 websites accepting OpenID for logins.  Several large organizations either issue or accept OpenIDs, including Google, Facebook, Yahoo!, Microsoft, AOL, MySpace, Sears, Universal Music Group, France Telecom, Novell, Sun, Telecom Italia, and many more.

## What is the difference between authorization and authentication?

Authentication confirms that users are who they say they are. Authorization gives those users permission to access a resource.

## What is Authorization Code Flow?


Authorization code flow is used to obtain an access token to authorize API requests. ... Access tokens while having a limited lifetime, can be renewed with a refresh token. A refresh token is valid indefinitely and provides ability for your application to schedule tasks on behalf of a user without their interaction.

## What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?


The Authorization Code Flow + PKCE is an OpenId Connect flow specifically designed to authenticate native or mobile application users. This flow is considered best practice when using Single Page Apps (SPA) or Mobile Apps. PKCE, pronounced “pixy” is an acronym for Proof Key for Code Exchange.

## What is Implicit Flow with Form Post?

![](https://images.ctfassets.net/cdy7uua7fh8z/6m0uE4E7Hpzbdhyh9dEuYK/e36c910ff47a7540bf27e23c02822624/auth-sequence-implicit-form-post.png)

Implicit Flow with Form Post flow uses OIDC to implement web sign-in that is very similar to the way SAML and WS-Federation operates. The web app requests and obtains tokens through the front channel, without the need for secrets or extra backend calls.

## What is Client Credentials Flow?

![](https://curity.io/images/resources/standards/oauth/flows/cc-flow-01.svg?v=20210408
)
The Client Credentials flow is a server to server flow. There is no user authentication involved in the process. ... This flow is useful for systems that need to perform API operations when no user is present. It can be nightly operations, or other that involve contacting OAuth protected APIs.

## What is Device Authorization Flow?

![](https://images.ctfassets.net/cdy7uua7fh8z/1A6jpG3W1H6SC9ZK92NyKd/40af53209f90a7c392f621f329fb4424/auth-sequence-device-auth.png)

With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text.

## What is Resource Owner Password Flow?

![](https://www.oreilly.com/library/view/getting-started-with/9781449317843/httpatomoreillycomsourceoreillyimages986441.png)


The Resource Owner Password Credentials flow allows exchanging the username and password of a user for an access token and, optionally, a refresh token. The primary difference is that the user's password is accessible to the application.