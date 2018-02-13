# Content for jayrgee.net blog

This repository contains the content for the [jayrgee.net](https://jayrgee.net) blog website.  The content is written in markdown with supporting image files.

The blog website is generated using [Hexo.io](https://hexo.io) and deployed to [Github Pages](https://pages.github.com).

## Using Hexo

> Full details on using Hexo.io can be found in the [Hexo.io documentation](https://hexo.io/docs)

## Cloning this project

Clone the project and change into the directory created by the clone

```
git clone origin git@github.com:jayrgee/jayrgee.github.io-hexo.git
cd jayrgee.github.io-hexo
```

### Getting the Git submodule

The git submodule used with this project needs to be pulled in after cloning the project:

* themes/landscape-jayrgee - a customised fork of the default _landscape_ theme

To pull this submodule in, use the following commands

```
git submodule init
git submodule update
```

The contents of the submodule should now have been copied (cloned) into the project.

### Install all hexo modules

Now install the node modules required for Hexo, as defined in the `packages.json` file

```
npm install
```

## Writing blog content

I've defined `npm` scripts for basic Hexo functions.

```
npm run write
```

...which is the same as running the following Hexo commands:

```
hexo serve --draft --open
```

### Creating a new Post

```
hexo new "name of post"
```

### Creating a new Draft

```
hexo new draft "name of draft"
```


## Generating a build

When generating a new build it is a good idea to clean first:

```
hexo clean
hexo generate
```

## Deployment

To deploy to Github pages, use the hexo deploy command

```
hexo deploy
```

> Note, if you are not the owner of the Github Pages repository for this site, you will not be able to deploy the code without first changing the details in the deployment section of the `_config.yml` file.

## References

This project was informed by the following blog post and github repo by jr0cket:

* http://jr0cket.co.uk/hexo/managing-hexo-website-content-with-git-and-github.html
* https://github.com/jr0cket/jr0cket.github.io-hexo
