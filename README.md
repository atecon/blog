# How-to build your Hugo static-website
I have to say that it took me quite a while to set up [my homepage](https://atecon.github.io/) on github-pages.

Under references you find valuable sources on how to set up things. As an introduction I really recommend [this 10 minutes video](https://www.youtube.com/watch?v=LIFvgrRxdt4).

I especially struggled with how Hugo handles directory structures. Showing the content of an `_index.md` file requires, don't ask me why, adding
```html
<div class="post-content">
  {{ .Content }}
</div>
```
to the the `./themes/layouts/_default/list.html` file as follows:

```html
{{ define "main" }}
  <article>
    <h1>{{ .Title }}</h1>
    <div class="post-content">
      {{ .Content }}
    </div>
    <ul class="posts-list">
      {{ range where .Paginator.Pages "Type" "!=" "page" }}
        <li class="posts-list-item">
          <a class="posts-list-item-title" href="{{ .Permalink }}">{{ .Title }}</a>
          <span class="posts-list-item-description">
            {{ partial "icon.html" (dict "ctx" $ "name" "calendar") }}
            {{ .PublishDate.Format "Jan 2, 2006" }}
            -
            {{ partial "icon.html" (dict "ctx" $ "name" "clock") }}
            {{ .ReadingTime }} min read
          </span>
        </li>
      {{ end }}
    </ul>
    {{ partial "pagination.html" $ }}
  </article>
{{ end }}
```

# Install Hugo on Ubuntu
```bash
sudo snap install hugo
```

# Workflow

## Run the web-server
```bash
cd ./blog/ateconssite
hugo server -D  # -D for dynamic refreshing
```

## Create a new thread
```bash
cd ./blog/ateconssite
hugo new <TYPE>/<FILENAME>.md
```

As <TYPES> I distinguish between:
	- posts
	- research

For more see: https://gohugo.io/content-management/types/

For each type a sub-folder is created under ```./blog/ateconssite/content```

The ```./blog/ateconssite/config.toml``` file configures the links to each content <TYPE>.

## Deploy your changes
```bash
cd ./blog/ateconssite
hugo -t  <THEMENAME>
```
`-t` is just an option for a specific theme. My current <THEMENAME> is m10c.

Next, we need to update the submodule repo:
```bash
cd ./blog/ateconssite/public  # enter the gihub.io relatively linked repo
git add .
git commit -m "SOME COMMIT MESSAGE"
git push origin main          # push to main on gihub.io relatively linked repo
```


# References
- Create a Hugo project: https://www.youtube.com/watch?v=LIFvgrRxdt4
- On dir. structure: https://www.jakewiesler.com/blog/hugo-directory-structure
- On dir. structure: https://bwaycer.github.io/hugo_tutorial.hugo/content/using-index-md/
- https://youtu.be/0GZxidrlaRM
- My template: https://fribbledom.com/
