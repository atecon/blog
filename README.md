# Howto

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
