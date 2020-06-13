---
title: Contato
published: true
hide_git_sync_repo_link: true
hide_hypothesis: true
form:
    name: contato
    fields:
        name:
            label: Nome
            placeholder: 'Nome completo'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        email:
            label: Email
            placeholder: 'Endereço de email'
            type: email
            validate:
                required: true
        message:
            label: Mensagem
            placeholder: 'Texto da mensagem'
            type: textarea
            validate:
                required: true
        g-recaptcha-response:
            label: Captcha
            type: captcha
            recaptcha_not_validated: 'Captcha inválido!'
    buttons:
        submit:
            type: submit
            value: Enviar
        reset:
            type: reset
            value: 'Apagar e recomeçar'
    process:
        captcha: true
        save:
            fileprefix: contato-
            dateformat: Ymd-His-u
            extension: txt
            body: '{% include ''forms/data.txt.twig'' %}'
        email:
            subject: '[Contato via site] {{ form.value.name|e }}'
            body: '{% include ''forms/data.html.twig'' %}'
        message: 'Obrigado por entrar em contato!'
        display: obrigado
---

# Contato