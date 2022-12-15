# api-hub-credentials-ap
## A draft proposal for the Registration API

 - Hosted and part of the The API Hub
 - Called by the HIP API Platform

# Resources

Nope (already hosted in HIP Portal: Deployment Configuration + OAS)
 - APIs         : The APIs and their versions
 - Endpoint     : The Endpoints with scopes for a version (Just the OAS file?)

Yup 
 - Credentials  : Credentials and their scopes

# The Registration API 

## Get Credentials

See OpenAPI Specification files

## Get changes (to credentials)


Github uses ETags see below:
(from: https://docs.github.com/en/rest/activity/events?apiVersion=2022-11-28)
>

> Events
> The Events API is a read-only API to the GitHub events.
> 
> These events power the various activity streams on the site.
> 
> The Events API can return different types of events triggered by activity on GitHub. For more information about the specific events > that you can receive from the Events API, see "GitHub Event types." An events API for repository issues is also available. For more > information, see the "Issue Events API."
> 
> Events are optimized for polling with the "ETag" header. If no new events have been triggered, you will see a "304 Not Modified" > response, and your current rate limit will be untouched. There is also an "X-Poll-Interval" header that specifies how often (in > seconds) you are allowed to poll. In times of high server load, the time may increase. Please obey the header.
> 
> $ curl -I https://api.github.com/users/tater/events
> > HTTP/2 200
> > X-Poll-Interval: 60
> > ETag: "a18c3bded88eb5dbb5c849a489412bf3"
> 
> # The quotes around the ETag value are important
> $ curl -I https://api.github.com/users/tater/events \
> $    -H 'If-None-Match: "a18c3bded88eb5dbb5c849a489412bf3"'
> > HTTP/2 304
> > X-Poll-Interval: 60
> Only events created within the past 90 days will be included in timelines. Events older than 90 days will not be included (even if > the total number of events in the timeline is less than 300).

## Proposed Sequence Diagram

[![](https://mermaid.ink/img/pako:eNrFVG1r2zAQ_iuHPq3UThw5TmzDGjZa1n7oCFthMPJFsU-2wJYy6bwuK_nvk_KyttAPgxZmMJbv5bl7dNzzwCpTIyuZwx8D6govlWis6Fca_CMGMnro12gP_xYrAtus3_EkiXiWRf57dnCFZyMsqUpthCb4sLyJl50gaWwPwsH1zTLY4GR7OWtpLIkuxN-1uI-_HtaPoZ8NIXQoCYx8VqGET0hQtUI36OC-RQ3UokUQ_tXm5HlEepocX1ycHws_wymhGmwHcQtKxtpojHtBVVvCik1W7BHrkOtR4mekS_iCbmO0Q0iTaegdbk2tpMJ6pV_DSTnwzYDG-6P3f9Hy04dzWIptZ0RdwtWdaOC9h-FPYV7NNYyQ7g2IuiZltKfz1tPkb0PbnmBQ14fDS1tz2Jyzf74UqawjcLh3n24ohm-tICDjt8c5UHoBdx8v4Yp8K9KaHirRdcHd-LxwdDRIuXizG1ssFq_dgONFsYj1aHuhai9CD8G8Yn70Pa5YKFSjFENHodjOhw6bWhBe1YqMZaUUncOIBZX6utUVK8kOeAo6CtnfqDAs9EkPjLaboHiNcuQhK6OlaoLdk_XmlmjjyvE4uEeNonZYjyrTj52qW69U7c9iNp7xWS54irN5KrI0rav1pMgln05kPU8mXLDdLmK47_L2IK97lY2YF7lQ6RcreZqM8nye8mleZPNJkc0itvVmzkdJPk2nRZEVPMmT3CP9NsbzSEbFfJIk01mS8SLl87TY433fOwPz3R_e3ctQ?type=png)](https://mermaid.live/edit#pako:eNrFVG1r2zAQ_iuHPq3UThw5TmzDGjZa1n7oCFthMPJFsU-2wJYy6bwuK_nvk_KyttAPgxZmMJbv5bl7dNzzwCpTIyuZwx8D6govlWis6Fca_CMGMnro12gP_xYrAtus3_EkiXiWRf57dnCFZyMsqUpthCb4sLyJl50gaWwPwsH1zTLY4GR7OWtpLIkuxN-1uI-_HtaPoZ8NIXQoCYx8VqGET0hQtUI36OC-RQ3UokUQ_tXm5HlEepocX1ycHws_wymhGmwHcQtKxtpojHtBVVvCik1W7BHrkOtR4mekS_iCbmO0Q0iTaegdbk2tpMJ6pV_DSTnwzYDG-6P3f9Hy04dzWIptZ0RdwtWdaOC9h-FPYV7NNYyQ7g2IuiZltKfz1tPkb0PbnmBQ14fDS1tz2Jyzf74UqawjcLh3n24ohm-tICDjt8c5UHoBdx8v4Yp8K9KaHirRdcHd-LxwdDRIuXizG1ssFq_dgONFsYj1aHuhai9CD8G8Yn70Pa5YKFSjFENHodjOhw6bWhBe1YqMZaUUncOIBZX6utUVK8kOeAo6CtnfqDAs9EkPjLaboHiNcuQhK6OlaoLdk_XmlmjjyvE4uEeNonZYjyrTj52qW69U7c9iNp7xWS54irN5KrI0rav1pMgln05kPU8mXLDdLmK47_L2IK97lY2YF7lQ6RcreZqM8nye8mleZPNJkc0itvVmzkdJPk2nRZEVPMmT3CP9NsbzSEbFfJIk01mS8SLl87TY433fOwPz3R_e3ctQ)















### License

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").






