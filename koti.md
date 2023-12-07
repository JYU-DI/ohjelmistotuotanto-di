``` {settings=""}
preamble: preamble,/users/dezhidki/opetus/ohjelmistotuotanto-di/templates/preambles/preamble
comments: private
_fieldmacros: # TODO: FIX
  - 637558.ch_prog(2,6)=ch_prog
  - 637558.ch1_sec_luento_1
  - 637558.ch1_sec_luku_2_1
  - 637558.ch1_sec_luku_2_2
  - 637558.ch1_sec_tehtava_2_1
  - 637558.ch1_sec_tehtava_2_2
sidemenu_initial_state: closed
globalmacros:
  CHAPTER: |!!
{% macro section(name, url, p) -%}
<a {% if url %}href="%%url%%"{% endif %} class="ch-sec-url {% if not url %}disabled{% endif %}"><span class="ch-sec-title">%%name%%</span> {% if p != None %}%%progress(p|round|int)%%{% endif %}</a>
{%- endmacro %}

{% macro ch_title(ch_num) -%}
## [%%ch_num%%]{.ch-num} %%courseChapters[ch_num].title%%
{% if courseChapters[ch_num].points != False %}%%progress(("ch_prog"~ch_num)|local(0)|round|int)%%{% endif %}
{%- endmacro %}

{% macro ch_sections(ch_num) -%}
{%- for sec in courseChapters[ch_num].sections -%}
%%section(sec.title, ("/view/" ~ homePath ~ "/" ~ year ~ "/osa" ~ ch_num ~ sec.path) if sec.path else None, (sec.points|local(0)))%%
{%- endfor -%}
{%- endmacro %}
!!
themes:
  - users/dezhidki/opetus/ohjelmistotuotanto-di/tyylit/etusivu
```

#- {area="title-banner"}

``` {.title-content .nonumber atom="true"}
:::tim-jumbotron

:::jumbotron-title
[]{}

# Ohjelmistotuotanto

**2024**

:::

:::jumbotron-icons
{!!! ikoni voi laittaa tähän !!!}
:::

:::
```

#- {area_end="title-banner" .title-bottom}

#- {.section-container}
:::Warning
Tämä on testisivu!
:::

#- {area="info-banner" .task-area-inverted}

``` {.sec-head atom="true"}
***

## Tietoa opintojaksosta
```

#- {.instruction}
Tervetuloa opintojaksolle **Ohjelmistotuotanto**!

Kurssilla käsitellään ohjelmistotuotantoprojektien hallinnan, työvaiheiden ja työvälineiden perusteita. Erityinen
painotus ketterissä ohjelmistotuotantomenetelmissä.

Kurssin opetusjärjestelyt ja arvosteluperusteet on kuvattu [osassa 0](/osa0), lue ne tarkasti heti kurssin alussa!

- Luennot
  - ma 12-14 B123
  - ti 12-14 B123
  - Luennot ovat nähtävissä livenä [Unitubessa](https://video.helsinki.fi/unitube/live-stream.html?room=l10) 
  - Luennoista tulee myös tallenteet, ks. [aikataulu](/#aikataulu), vuoden 2021 zoom-luentojen tallenteet ovat myös käytössä
- [Miniprojekti](/miniprojekti)
- Yleisön pyynnöstä [linkki luentokalvoihin](https://github.com/ohjelmistotuotanto-hy/slides-23)
- Apua tehtävien tekoon
  - pajassa BK107 ma 10-12, ma 14-16, ke 10-12 ja pe 12-14 
- Kurssiin liittyvää keskustelua [Discordissa](https://study.cs.helsinki.fi/discord/join/ohtu), tule mukaan!
  - **HUOM:** kaikki epäasialliset, halventavat ja jotain ihmisryhmää syrjivät kommentit kanavalla ovat kiellettyjä ja tälläisten kommenttien esittäjät poistetaan kanavalta
- Kurssipalaute
  - Kurssilla on käytössä normaalin lopussa kerättävän palautteen lisäksi ns. jatkuva palaute: voit antaa milloin vain kurssihenkilökunnalle anonyymiä palautetta osoitteessa <https://norppa.helsinki.fi/targets/72482660/feedback>

``` {.sec-head atom="true"}
***

## Ajankohtaista
```

#- {.instruction}

include...

``` {.sec-head atom="true"}
***

## Kurssin materiaaleista
```

#- {.instruction}

Kurssimateriaalin ovat tehneet <a href="https://github.com/mluukkai">Matti Luukkainen</a> ja <a href="https://github.com/Kaltsoon">Kalle Ilves</a>. Lukuisat <a href="https://github.com/ohjelmistotuotanto-hy/ohjelmistotuotanto-hy.github.io/graphs/contributors">henkilöt</a> ovat parantaneet materiaalin laatua kirjoitus- ja asiavirhekorjauksin. Voit <a href="/osa0#typoja-materiaalissa">osallistua</a> kurssimateriaalin parantamiseen myös itse.

Tämä materiaali on lisensoitu <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons BY-NC-SA 3.0 -lisenssillä</a>, joten voit käyttää ja levittää sitä vapaasti, kunhan alkuperäisten tekijöiden nimiä ei poisteta. Jos teet muutoksia materiaaliin ja haluat levittää muunneltua versiota, se täytyy lisensoida samalla lisenssillä. Materiaalien käyttö kaupalliseen tarkoitukseen on ilman erillistä lupaa kielletty.

#- {area_end="info-banner"}

``` {.sec-head .section-container #aiheet atom="true"}
***

# Kurssin osat
```

#- {area="course-sections" .course-sections}

#- {area="progress-section0" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(0)%%

#- {.ch-section-list}
%%CHAPTER%%
%%ch_sections(0)%%
#- {area_end="progress-section0"}

#- {area="progress-section1" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(1)%%

#- {.ch-section-list}
%%CHAPTER%%
%%ch_sections(1)%%

#- {area_end="progress-section1"}

#- {area="progress-section2" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(2)%%

#- {.ch-section-list nocache="true"}
%%CHAPTER%%
%%ch_sections(2)%%

#- {area_end="progress-section2"}

#- {area="progress-section3" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(3)%%

#- {.ch-section-list nocache="true"}
%%CHAPTER%%
%%ch_sections(3)%%

#- {area_end="progress-section3"}

#- {area="progress-section4" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(4)%%

#- {.ch-section-list nocache="true"}
%%CHAPTER%%
%%ch_sections(4)%%

#- {area_end="progress-section4"}

#- {area="progress-section5" collapse="true" .progress-section nocache="true"}
%%CHAPTER%%
%%ch_title(5)%%

#- {.ch-section-list nocache="true"}
%%CHAPTER%%
%%ch_sections(5)%%

#- {area_end="progress-section5"}

#- {area_end="course-sections"}