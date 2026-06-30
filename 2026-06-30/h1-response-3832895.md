# HackerOne Response — Report #3832895

**Target:** slackb.com: Wildcard CORS (Access-Control-Allow-Origin: *)  
**Submitted:** 2026-06-30  
**Closed:** 2026-06-30  
**Closed by:** bugtriage-jorge  
**Resolution:** Informative  
**Bounty:** None

---

## Full Response

> Thank you for your report.
>
> Please keep in mind that our HackerOne program does not generally accept theoretical or potential reports, and requires that researchers demonstrate how the behavior they have found can be used in an attack.
>
> Whilst the endpoint you are reporting is configured with a permissive CORS configuration, this behavior does not necessarily pose a security risk on its own. In particular, this endpoint is an unauthenticated endpoint that does not contain any sensitive information that an attacker could not already obtain by requesting the URL from their own browser.
>
> Please keep in mind that a CORS misconfiguration is only considered to pose a security risk where the endpoint discloses sensitive information about the currently authenticated user, or can be used to carry out state-changing actions on the user's account.
>
> With this in mind, we will close this report as Informative.
>
> Thanks, and good luck with your future bug hunting.
