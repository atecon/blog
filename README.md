# How-to build your Hugo static-website
I have to say that it took me quite a while to set up [my homepage](https://atecon.github.io/).

## Run the web-server
```
cd ./blog/ateconssite
hugo server
```

## Create a new thread
```
cd ./blog/ateconssite
hugo new <TYPE>/<FILENAME>.md
```

As <TYPES> I distinguish between:
	- posts
	- research

For more see: https://gohugo.io/content-management/types/

For each type a subfolder is created under ```./blog/ateconssite/content```

The ```./blog/ateconssite/config.toml``` file configures the links to each content <TYPE>.


# References
- Create a hugo project: https://www.youtube.com/watch?v=LIFvgrRxdt4
- On dir. structure: https://www.jakewiesler.com/blog/hugo-directory-structure
- On dir. structure: https://bwaycer.github.io/hugo_tutorial.hugo/content/using-index-md/
- https://youtu.be/0GZxidrlaRM
- My template: https://fribbledom.com/

