<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Amporisihina ny hametraka nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) aloha, ary avy eo dia `direnv allow` rehefa miditra ao amin'ny lahatahiry ( [ny .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) dia hotanterahina ho azy rehefa miditra ao amin'ny lahatahiry).

Ny dikany dia: fandikana sinoa amin'ny teny japoney, koreana, anglisy, anglisy amin'ny fiteny hafa rehetra. Raha te hanohana sinoa sy anglisy fotsiny ianao dia afaka manoratra `zh: en` .

Ny dikany dia: dikanteny sinoa amin'ny teny japoney, koreana, anglisy, anglisy amin'ny fiteny hafa rehetra. Raha te hanohana sinoa sy anglisy fotsiny ianao dia afaka manoratra `zh: en` .

* [kaody eo anoloana](https://github.com/xxai-art/web)
* [Fonosana fiteny ho an'ny tranokala manontolo](https://github.com/xxai-art/web/tree/main/i18n)
* [Fonosana fiteny ho an'ny maody fidirana](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Tranonkala antontan-taratasy amin'ny fiteny maro](https://github.com/xxai-doc)

Ny fiteny fandaharana eo anoloana dia [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , izay manampy endri-javatra sasany mifototra amin'ny syntax coffeescript, jereo [./coffee_plus.md](./coffee_plus.md) .

## Internationalization ny tranonkala sy ny antontan-taratasy

Amboary amin'ireto tetikasa 3 manaraka ireto

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Ny tovana dia `.mdt` , azonao ampiasaina ny fehezanteny mitovitovy amin'ny `<+ ./coffee_plus/import.js>` hanondroana rakitra ivelany, ary mamokatra marika miaraka amin'ny tovana `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Ny dikanteny Markdown dia tsy handika kaody sy rohy, ary hametraka fehezanteny voadika. Raha ovaina ny fandikan-teny nefa tsy ovaina ny lahatsoratra tany am-boalohany, ny fanatanterahana azy indray dia tsy hosoloina ny fanovana ny dikanteny.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Ny rakitra amin'ny fiteny handikana ireo vohikala noforonin'ny `yaml` .

### Torolàlana momba ny automatique fandikan-teny

Jereo ny tahiry kaody [xxai-art/doc](https://github.com/xxai-art/doc)

Amporisihina ny hametraka nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) aloha, ary avy eo dia `direnv allow` rehefa miditra ao amin'ny lahatahiry ( [ny .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) dia hotanterahina ho azy rehefa miditra ao amin'ny lahatahiry).

Mba hialana amin'ny fototry ny kaody lehibe voadika amin'ny fiteny an-jatony, dia namorona fototra fehezan-dalàna manokana ho an'ny fiteny tsirairay aho ary namorona fikambanana iray hitahiry ny fototry ny fehezan-dalàna.

Ny fametrahana ny fari-piainan'ny tontolo iainana `GITHUB_ACCESS_TOKEN` ary avy eo mihazakazaka [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) dia hamorona ho azy ny fitehirizana kaody.

Mazava ho azy, azonao atao koa ny mametraka azy ao anaty code base.

Fandikan-teny script [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Ny code script dia adika toy izao manaraka izao:

[bunx](https://bun.sh/docs/cli/bunx) dia fanoloana npx, izay haingana kokoa. Mazava ho azy, raha tsy nametraka bun ianao dia azonao atao ny mampiasa `npx` .

`bunx mdt zh` dia mamadika `.mdt` ao amin'ny lahatahiry zh ho `.md` , jereo ny rakitra 2 mifandray etsy ambany

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` no kaody fototra ho an'ny fandikan-teny (raha `nodejs` ihany no napetrakao, fa tsy napetraka `bun` sy `direnv` dia azonao atao koa ny mampandeha `npx i18n` handika teny).

Hizara [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) izy io, toy izao manaraka izao ny firafitry ny `i18n.yml` amin'ity antontan-taratasy ity:

```
en:
zh: ja ko en
```

Ny dikany dia: fandikana sinoa amin'ny teny japoney, koreana, anglisy, anglisy amin'ny fiteny hafa rehetra. Raha te hanohana sinoa sy anglisy fotsiny ianao dia afaka manoratra `zh: en` .

Ny farany dia [ny gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , izay mamoaka ny votoatiny eo anelanelan'ny lohateny lehibe sy ny dikanteny voalohany amin'ny `README.md` an'ny fiteny tsirairay mba hamoronana fidirana `README.md` . Ny code dia tena tsotra, azonao jerena ny tenanao.

Google API dia ampiasaina amin'ny fandikan-teny maimaim-poana. Raha tsy afaka miditra amin'ny Google ianao dia amboary sy mametraha proxy, toy ny:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Ny script fandikan-teny dia hamorona cache voadika ao amin'ny lahatahiry `.i18n` , azafady jereo miaraka amin'ny `git status` ary ampidiro ao amin'ny tahiry kaody mba hisorohana ny fandikana miverimberina.

Alefaso azafady `bunx i18n` isaky ny manova ny dikanteny ianao hanavao ny cache.

Raha ovaina miaraka ny lahatsoratra tany am-boalohany sy ny dikanteny dia ho sahiran-tsaina ny cache, ka raha te hanova ianao dia iray ihany no azonao ovaina, ary avy eo dia mandehana `bunx i18n` hanavao ny cache.
