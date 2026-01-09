---
date:
  created: 2026-01-09
description: Implementing Keycloak as the Single Sign-On of choice in my homelab. Easy way to lose access and/or rights to your stuff.
---
While the Holiday season was a time filled with family joy, it was a busy time. Between packing presents and *driving home for Christmas* there was little time to work on projects. Such as this blog.

I took a longer than expected break from computers. And you know what? It was great!
Taking care of my family and giving them the time they deserve was very fulfilling. I do like my role as husband and father.

Now that we all got back to work and Kindergarten, I started once again thinking about hobby-stuff. I do provide four services that require login to family. This number won't shrink. What is a better time to implement Single Sign-On than now? Well, yesterday of course! That's why I stood up a Keycloak instance and secured my first app with it.
Setting up a `docker-compose.yml` wasn't as straightforward as I expected. This was the part that took me the longest. The examples are out of date and the [official documentation](https://www.keycloak.org/guides#server) does not provide the necessary bits in one place.

Eventually I pieced it all together, cherry picking parameters and variables from various places.
After that, configuration was maybe not a walk in the park, but a much more pleasant experience. I followed the official guide and set up a child `realm` and `client`, the client being the webapp. 

Basically its:

1. put Keycloak *realm* URL, client ID and secret into webapp

2. put link to webapp into Keycloak

*Congratulations! You now can log-in to the app using SSO.* If only it were this easy..
Now the accounts got merged? Squashed? Yes, based on the `Username` field in Keycloak, my admin account to the webapp got demoted and I no longer can log in using the old password. Word of caution here to anyone trying this at home. **Do. Make. Backups!**

I started the migration to SSO with the most recent app added to the homelab as it didn't hold any valuable data yet. I did it haphazardly, one might say I yolo'ed it, but in doing so I quickly discovered what the next steps will be:

1. revise the backup strategy (oh God why haven't I done it already?)

2. test disaster recovery

3. configure accounts carefully, with all required `roles` set in advance

4. migrate the less important apps to SSO

5. after that, and ONLY after, enable SSO for `immich` and `paperless-ngx`

Progress was made.
