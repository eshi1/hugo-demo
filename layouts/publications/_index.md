{{ define "main" }} {{ partial "page-header.html" . }} {{with .Params.image}}
<section
    class="section"
    class="container"
    style="background-image:url({{ . | relURL }});background-position: 50% 50%; background-size: cover; background-repeat: no-repeat;height: 300px"
></section>
{{end}}
<section class="section">
    <div class="container">
        <div class="row justify-content-center align-items-center">
            <div class="col-lg-12 lead">
                {{ with .Params.publications }}
                <ol>
                    {{ range . }}
                    <li style="padding: 4px 0">
                        <a href="{{.url}}" title="{{ .text }}" target="_blank">{{ .text | markdownify }}</a>
                    </li>
                    {{ end }}
                </ol>
                {{ end }}
            </div>
        </div>
    </div>
</section>

{{ end }}
