<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Hè ricumandemu per installà nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) prima, è dopu `direnv allow` dopu à l'ingressu à u cartulare ( [u .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) serà eseguitu automaticamente dopu à l'ingressu à u cartulare).

U significatu hè: traduzzione cinese in giapponese, coreanu, inglese, traduzzione inglese in tutte l'altri lingue. Se vulete solu sustene u cinese è l'inglese, pudete scrive solu `zh: en` .

U significatu hè: traduzzione cinese in giapponese, coreanu, inglese, traduzzione inglese in tutte l'altri lingue. Se vulete solu sustene u cinese è l'inglese, pudete scrive solu `zh: en` .

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

### Istruzzioni per l'automatizazione di a traduzzione di documenti

Vede u repository di codice [xxai-art/doc](https://github.com/xxai-art/doc)

Hè ricumandemu per installà nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) prima, è dopu `direnv allow` dopu à l'ingressu à u cartulare ( [u .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) serà eseguitu automaticamente dopu à l'ingressu à u cartulare).

Per evità a basa di codice grande tradutta in centinaie di lingue, aghju creatu una basa di codice separata per ogni lingua è creatu una urganizazione per almacenà a basa di codice.

Stabilisce a variabile di l'ambiente `GITHUB_ACCESS_TOKEN` è poi eseguisce [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) crea automaticamente u repository di codice.

Di sicuru, pudete ancu mette in una basa di codice.

Riferimentu di script di traduzzione [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

U codice di script hè interpretatu cusì:

[bunx](https://bun.sh/docs/cli/bunx) hè un sustitutu per npx, chì hè più veloce. Di sicuru, sè ùn avete micca bun installatu, pudete aduprà `npx` invece.

`bunx mdt zh` rende `.mdt` in u repertoriu zh cum'è `.md` , vede i 2 schedarii ligati sottu

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` hè u codice core per a traduzzione (se avete solu `nodejs` installatu, ma `bun` è `direnv` ùn sò micca stallati, pudete ancu eseguisce `npx i18n` per traduce).

Analizerà [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , a cunfigurazione di `i18n.yml` in stu documentu hè a seguente:

```
en:
zh: ja ko en
```

U significatu hè: traduzzione cinese in giapponese, coreanu, inglese, traduzzione inglese in tutte l'altri lingue. Se vulete solu sustene u cinese è l'inglese, pudete scrive solu `zh: en` .

L'ultimu hè [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , chì estrae u cuntenutu trà u titulu principale è u primu subtitulu di `README.md` di ogni lingua per generà una entrata `README.md` . U codice hè assai simplice, pudete guardà ellu stessu.

L'API di Google hè aduprata per a traduzzione libera. Se ùn pudete micca accede à Google, cunfigurà è stabilisce un proxy, cum'è:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

U script di traduzzione genererà un cache traduttu in u cartulare `.i18n` , verificate cù `git status` è aghjunghje à u repository di codice per evità traduzzioni ripetuti.

Per piacè run `bunx i18n` ogni volta chì mudificà a traduzzione per aghjurnà a cache.

Se u testu uriginale è a traduzzione sò mudificate à u stessu tempu, u cache serà cunfusu, perchè se vulete mudificà, pudete solu mudificà unu, è poi run `bunx i18n` per aghjurnà a cache.
