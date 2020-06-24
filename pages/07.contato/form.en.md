---
title: Contact
routes:
  default: '/contact'
published: true
hide_git_sync_repo_link: true
hide_hypothesis: true
slug: contact
form:
    name: contact
    fields:
        name:
            label: Name
            placeholder: 'Your name'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        email:
            label: Email
            placeholder: 'Your current email address'
            type: email
            validate:
                required: true
        message:
            label: Message
            placeholder: 'Your message for us'
            type: textarea
            validate:
                required: true
        g-recaptcha-response:
            label: Captcha
            type: captcha
            recaptcha_not_validated: 'Invalid captcha!'
    buttons:
        submit:
            type: submit
            value: Send
        reset:
            type: reset
            value: 'Start over'
    process:
        captcha: true
        save:
            fileprefix: contact-
            dateformat: Ymd-His-u
            extension: txt
            body: '{% include ''forms/data.txt.twig'' %}'
        email:
            subject: '[Contact from website] {{ form.value.name|e }}'
            body: '{% include ''forms/data.html.twig'' %}'
        message: 'Thanks for contacting us!'
        display: thankyou
---

# Contact

We are located in Salvador, at the state of Bahia, Brazil, in the Faculty of Communication of the Federal University of Bahia. Below, you may find our location and a contact form.

![](logo.jpg?classes=s-rounded)

## Our location

[map-leaflet lat=-13.00145 lng=-38.51027 zoom=15 mapname=sede]
[a-markers markerColor="purple"
iconColor="white"
]
[{ "lat": -13.00145, "lng": -38.51027, "icon": "map-marker", "title": "Facom-UFBA" } ]
[/a-markers]
[/map-leaflet]

## Send us a message
