# Drydock

## Prerequisites

To install this project, you'll need the following things installed on your machine.

1. [Jekyll](http://jekyllrb.com/) & [Bundler](https://bundler.io/) - `$ gem install jekyll bundler` 
2. [NodeJS](http://nodejs.org) - use the installer. 
3. [Yarn](https://yarnpkg.com/en/) - `brew install yarn` _**(Optional)**_
  4. [CloudCanoon](https://docs.cloudcannon.com/) - Give the client an interface to manage their site with a simple CMS. _**(Suggested for Clients)**_

## Local Development & Installation

1. Clone this repo, or download it into a directory of your choice.
    
      ```shell
    git clone https://github.com/ginfuru/drydock.git
    ```
2. Inside the directory, run `yarn install` -> **FYI** you can use `npm` in place of `yarn`
     
      ```shell
    cd drydock
    yarn install
    ```

## Usage

**Note:** If you are having trouble with the commands, prepending `bundle exec` to you command should solve the issues:

    ```shell
  bundle exec yarn start
  ```

### Start Development

This will give you file watching, browser synchronisation, auto-rebuild, CSS injecting etc.

  ```shell
  yarn start
  ```

### Build for Production

This will set the `JEKYLL_ENV` to `production` and use the production config file(s) set in `drydock.config.js` to override default setting.
You can easily deploy your site build with the command
```shell
yarn run build
```

## See More Commands

This will display all available commands.

```shell
yarn run
```

### Jekyll

As this is just a Jekyll project, you can use any of the commands listed in their [docs](https://jekyllrb.com/docs/usage/)

## What's inside the Drydock

- [gulp](http://gulpjs.com/)
- [Sass](http://sass-lang.com/)
- [Autoprefixer](https://github.com/postcss/autoprefixer)
- [PostCSS](http://postcss.org/)
- [Bourbon](http://bourbon.io/)/[Neat](http://neat.bourbon.io/)/[Bitters](http://bitters.bourbon.io/)
- [Webpack](https://webpack.github.io/)
- [UglifyJS](https://github.com/mishoo/UglifyJS2)
- [imagemin](https://github.com/imagemin/imagemin)
- [Browsersync](https://www.browsersync.io/)

## Configurations and Defaults

You can change the configurations by editing `drydock.config.js`.

- ### port

    default: `4000`  
    options: integer  

- ### tasks

    Tasks to run when you exec `yarn start` or `gulp` commands.

    - #### imagemin

        To minify images.

        default: `true`  
        options: boolean (`true` / `false`)

    - #### sass

        To compile Sass.

        default: `true`  
        options: boolean (`true` / `false`)

    - #### server

        To compile sources via Jekyll and to keep browsers in sync with file changes via Browsersync.

        default: `true`  
        options: boolean (`true` / `false`)

    - #### webpack

        To bundle JavaScript files.

        default: `true`  
        options: boolean (`true` / `false`)

- ### paths

    Settings about paths.

    - #### dest

        The destination directory for the whole project.

        default: `"_site"`  
        options: string

    - #### posts

        The directory of posts source files.

        default: `"_posts"`  
        options: string

    - #### assets

        The directory to gather all assets.

        default: `"./assets"`  
        options: string  
        example: `"./"` (directly under the theme direcotry)

    - #### css

        The CSS destination directory for Sass.

        default: `"css"`  
        options: string  
        example: `"stylesheets"`

    - #### js

        The JavaScript destination directory for Browserify.

        default: `"js"`  
        options: string  
        example: `"javascripts"`

    - #### images

        The destination directory of compressed image files for imagemin.

        default: `"images"`  
        options: string  
        example: `"img"`

    - #### sass

        The directory of Sass files.

        default: `"_sass"`  
        options: string  
        example: `"src/sass"`

    - #### jsSrc

        The directory of JavaScript source files to bundle up by Browserify.

        default: `"_js"`  
        options: string  
        example: `"src/js`"

    - #### imagesSrc

        The directory of image source files to compress.

        default: `"_images"`  
        options: string  
        example: `"src/images"`

- ### jekyll

    Jekyll settings.

    - #### config

        Jekyll config files.

        - ##### default

            The default Jekyll config file(s).

            default: `"_config.yml"`  
            options: string (`"FILE1[,FILE2,...]"`)  
            example: `"_config1.yml,_config2.yml"`

        - ##### development

            Development mode config file(s) to override default settings.

            default: `""`  
            options: string (`"FILE1[,FILE2,...]"`)  
            example: `"_config_development"`

        - ##### production

            Production mode config file(s) to override default settings.

            default: `""`  
            options: string (`"FILE1[,FILE2,...]"`)  
            example: `"_config_production"`

- ### sass

    Sass settings.

    - #### outputStyle

        The output style of Sass.

        default: `"compressed"`  
        options: `"expanded"`, `"nested"`, `"compact"`, `"compressed"`

- ### autoprefixer

    Autoprefixer settings.

    - #### browsers

        List of browsers, which are supported in your theme.

        default: `["> 1%", "last 2 versions", "Firefox ESR"]`  
        options: array. See [Browserslist docs](https://github.com/ai/browserslist#queries) for available queries.  
        example: `["> 5%", "last 2 versions", "IE 8"]`

- ### js

    JavaScript settings.

    - #### entry

        File name(s) of JavaScript entry points.

        default: `["main.js"]`  
        options: array  
        example: `["pluginA.js", "pluginB.js", "main.js"]`
