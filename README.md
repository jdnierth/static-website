# Static Website

# Installation
## Windows
1. Install Chocolatery: Follow the installation guide of [Chocolatery Software Managment Tool](https://chocolatey.org/install). 

# Develop
1. Run the following command `make serve`from the `src` folder
2. The log will tell you under which domain the project is available from within the browser

# Theme
## Syntax
* Uses `yaml` for configuration files

# Documentation
* Template functions https://gohugo.io/functions/

# How to
1. Create a new project
`hugo new site <SITE_NAME>`
1. Change config.toml to config.yaml - At the time of writing this couldn't be set via the cli
 Change the content of your toml via this [Toolkit](https://toolkit.site/format.html).
    1. Navigate into the folder of your project
    1. Create a theme `hugo new theme <THEME_NAME>`
1. 

## Multilingual site
1. https://regisphilibert.com/blog/2018/08/hugo-multilingual-part-1-managing-content-translation/


## Snippets
`
    {{ $pltax := i18n "programminglanguagetax" }}
    <ul>
        {{ range $taxonomyname, $taxonomy := .Site.Taxonomies }}
        <li><a href="{{ "/" | relLangURL}}{{ $taxonomyname | urlize }}">{{ $taxonomyname }}</a>
            <ul>
                {{ range $key, $value := $taxonomy }}
                {{ $key }}
                <ul>
                    {{ range $value.Pages }}
                    <li><a href="{{ .Permalink}}"> {{ .LinkTitle }} </a> </li>
                    {{ end }}
                </ul>
                {{ end }}
            </ul>
        </li>
        {{ end }}
    </ul>
`