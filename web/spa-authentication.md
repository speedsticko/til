oauth2
open connect id
saml

Goal: 
Rails web-app with Devise for user authentication. 
Emberjs client using Oauth2 for authorization (and authentication). 
At first I was trying to use ember-simple-auth (ESA) and the Devise Authenticator but this required some other Gems or hacks to get Devise to work with token authentication. Oauth2 access tokens seemed like a better standardized approach and there's a decent looking Gem called Doorkeeper. I wanted to continue to be able to log in directly using Devise but also allow Oauth2 access with password grant.
