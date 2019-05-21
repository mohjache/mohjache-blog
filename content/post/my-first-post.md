---
date: 2019-05-21
title: "Automating Certificate Renewal Within Your App"
draft: true
---

I never really like how we would get and renew certificates. It was a manual process that spanned usually two days which circumvented or completely ignored some industry standards since we had our own internal CA. If were working on one environment and one product it would be fine. However in total we had about 90 applications with three different environments that needed to be included. Now it my math checks out, that would be 270 certificates that would have to be managed. To circumvent this, we had Octopus manage and notify if a certificate would be ending expiration and the certificates themselves had a five year expiration.

Coming back from NDC Security, I've not only realised how far the dark path we have gone but to take the path of light would be something that should've been second nature to us. I totally get it though, each developer including myself picks their fires to fight and this definitely wasn't one of them. There also could be some legislative requirement from the powers that be that would require them to molest your traffic.

Out of curiosity I created the most disgusting way to automate the certificate issuance process as part of you actual dotnet core web app. The thinking was I could basically inject the info I need from octopus depending on environment and then never have to worry about certificates again. 