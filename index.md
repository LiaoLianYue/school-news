{%- capture site_tags -%}
    {%- for tag in site.tags -%}
        {{- tag | first -}}{%- unless forloop.last -%},{%- endunless -%}
    {%- endfor -%}
{%- endcapture -%}
{%- assign tags_list = site_tags | split:',' | sort -%}

{%- for tag in tags_list -%}
    <a href="./tags/#{{- tag -}}" class="btn btn-primary tag-btn"><i class="fas fa-tag" aria-hidden="true"></i>&nbsp;{{- tag -}}&nbsp;({{site.tags[tag].size}})</a>
{%- endfor -%}
