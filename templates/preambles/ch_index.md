``` {settings=""}
css: |!!
.sec-list, .sec-list p {
  display: flex;
  flex-direction: column;
  gap: 8px;
   
   .sec-link p { display: none; }

   .sec-link {
     display: inline-flex;
     align-items: center;
     text-decoration: none !important;
     padding: 4px 6px;

     &:hover {
       background-color: RGB(0 0 0 / 5%);
     }

     &.disabled {
       color: #aeaeae;
       pointer-events: none;
     }
   }

   .sec-title {
     margin-right: auto;
   }

  .ch-progress {
    width: 300px;

    @media screen and (max-width: 724px) {
      width: 100px;
    }
  }
}

.paragraphs {
  user-select: none;
}
!!
```

# Osa %%chapterNumber%%: %%courseChapters[chapterNumber].title%%

#- {.instruction}
Tähän osaan kuuluvat kappaleet:

#- {.instruction}
:::sec-list
{% for sec in courseChapters[chapterNumber].sections %}
<a href="{% if sec.path %}/view/%%homePath%%/%%year%%/%%chapterDir%%/%%chapterNumber%%/%%sec.path%%{% endif %}" class="sec-link {% if not sec.path %}disabled{% endif %}"><span class="sec-title">%%sec.title%%</span> {% if sec.points %}%%progress(0)%%{% endif %}</a>
{% endfor %}
:::