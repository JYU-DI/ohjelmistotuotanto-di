``` {plugin="timMenu" .hidden-print .section-top .section-nav}
openingSymbol: ""
separator: ""      
backgroundColor: "transparent"  # Menu bar background color (overrides basicColors)
textColor: black            # Menu bar text color (overrides basicColors)
fontSize: 1em
topMenu: false              # Show menu at the top when scrolling from below
basicColors: false          # Use TIM default color scheme in menu bar
keepLinkColors: true
hoverOpen: false             # Allow opening menus without clicking
menu: |!!
- [[]{.glyphicon .glyphicon-home} Ohjelmistotuotanto koti](/view/%%homePath%%/%%year%%/koti#aiheet){.home-link .btn .btn-default}
- [[]{.glyphicon .glyphicon-chevron-down} Osa %%chapterNumber%%: %%courseChapters[chapterNumber].title%%]{.chapter-name .btn .btn-default width=300}
{% for i, ch in courseChapters.items() %}
   - [Osa %%i%%: %%ch.title%%](/view/%%homePath%%/%%year%%/osa%%i%%)
{% endfor %}
!!
```