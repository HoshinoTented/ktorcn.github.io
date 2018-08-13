---
layout: post
title:  "Ktor IntelliJ IDEA Plugin 0.2.1"
categories: plugin
date: 2018-08-13
featured: true
#image: /blog/images/plugin.jpg
---

Today we have released the 0.2.1 version of the plugin for IntelliJ IDEA.

This version is mostly focused on Swagger/OpenAPI improvements.

### YAML Support

Previous versions only supported JSON model files, and you had to manually convert models first.
This version allows to parse YAML models too.

### Unnamed objects

In prior versions unnamed objects were represented as an Any.
This version now generates classes for those objects, using some heuristics for the names.

### Detecting login routes

This version tries to detect JWT-based login routes, and tries to generate some entry code for them.

![](/blog/images/plugin-0.2.1/swagger-login-heuristics.png){: style="width:50%;height:auto;"}

### More work on OpenAPI 3.0

Now more code from OpenAPI 3.0 models is generated. Requires more work, but still better than before.

### Generated `api.http` file

One nice new addition, is that along the code files, the plugin generates an `api.http` file.
* This files serves as a documentation file: showing the available routes, along expected headers
and sample parameters and bodies. 
* If you have IntelliJ IDEA Ultimate, you can also call the routes directly with its integrated HTTP Client.

![](/blog/images/plugin-0.2.1/api-http.png){: style="width:50%;height:auto;"}

This file is generated with samples, and it is aware of the login heuristics.
So you can grab this sample [swagger.json](https://github.com/ktorio/ktor-init-tools/blob/eb5c84fafc53849aeb6cbb0f435a5da7dd0ff552/ktor-generator/jvm/testresources/swagger.json) file from the [realworld](https://github.com/gothinkster/realworld) API, start the application,
login with the API and automatically store the token in a few clicks, and perform other
documented authenticated calls.

![](/blog/images/plugin-0.2.1/api-http-run.png){: style="width:50%;height:auto;"}

Pretty convenient!

Remember that this is a pre-release, and it is likely to contain bugs and issues
If you have the chance, please, try it out and give us feedback at Slack so we can improve it :)
