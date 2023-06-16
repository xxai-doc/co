<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Parte di u codice di u situ web hè open source, benvenutu per aiutà à ottimisà a traduzzione.

## codice front-end

* [codice front-end](https://github.com/xxai-art/web)
* [Pacchetti di lingua per u situ in tuttu](https://github.com/xxai-art/web/tree/main/i18n)
* [Pacchetti di lingua per i moduli di login](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Documentazione multilingue di u situ web](https://github.com/xxai-doc)

U linguaghju di prugrammazione front-end hè [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , chì aghjunghje alcune funziunalità basatu nantu à a sintassi di coffeescript, vede [./coffee_plus.md](./coffee_plus.md) .

## Internazionalizazione di siti web è documenti

Custruite nantu à i seguenti 3 prughjetti

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  U suffissu hè `.mdt` , pudete aduprà a sintassi simili à `<+ ./coffee_plus/import.js>` per riferite à i schedari esterni, è generà marcatu cù u suffissu `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  A traduzzione di Markdown ùn traduce micca i codici è i ligami, è mette in cache e frasi tradutte. Se a traduzzione hè mudificata, ma u testu originale ùn hè micca mudificatu, eseguisce di novu ùn sovrascriverà micca a mudificazione di a traduzzione.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  File di lingua per a traduzzione di siti web generati `yaml` .
