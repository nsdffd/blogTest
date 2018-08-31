# rakiB'slog

**rakiB'slog** is a theme for Jekyll. It is built keeping content in focus and is best for writers/developers who also like to share code with their essays. The theme was edited from the original theme named as **White Paper** by Vinit Kumar

# rakiB'slog in Action

- Home page

![home](https://raw.githubusercontent.com/nsdffd/blogtest/master/screenshot.png)


- Post Detail View

![post detail](https://raw.githubusercontent.com/nsdffd/blogtest/master/blog.png)

## How to use White Paper

Fork the repo to your account by clicking the button on the top right as shown in the image:

![fork](https://raw.githubusercontent.com/nsdffd/blogtest/master/fork.png) and then where you want to fork it as shown below.

Next, Go the the project settings and change the repository name to `<username>.github.io` where username is your username.

Change these entries in the `_config.yml` file:

Also, change this line in head.html [link](https://github.com/nsdffd/blogtest/blob/master/_includes/head.html#L27)

```html
<!-- From this -->
<link rel="stylesheet" href=" {{ '/css/main.min.css' | relative_url }}" type="text/css" />
<!-- To this -->
<link rel="stylesheet" href=" {{ '/css/main.min.css' | absolute_url }}" type="text/css" />

```


This will make sure that the path of CSS is correct and the theme loads correctly.

```yml
master_repo: false
url: "<username>.github.io"
rtl: false  # change to true if posts is in Arabic/other Right to left language.
```
Also, change all other fields in the `_config.yml` file to your choice.

## Installation

### Local Development

This theme requires you to install couple of tools first to setup jekyll locally.

```$
git clone git@github.com:nsdffd/blogtest.git

# If you have ruby installed.
gem install jekyll bundler

# If you have node installed.
npm install
sudo npm install -g grunt-cli  #to get the task runner for grunt.
bundle install
jekyll serve

# on running the serve script, the site will be live on
http://127.0.0.1:4000
```
This theme uses grunt to concat & minify the css for best performance. In order to prepare the css build. Run `grunt`
It will create a main.min.css file in the css folder.

### Switch Syntax Highlighting.

This theme also provides syntax highlighting in different theme. Inside css folder, there is a syntax folder.

```$
.
├── emacs.css
├── github.css
├── monokai.css
├── native.css
├── syntax.css
└── vim.css

```

Now in the gruntfiles.js

```js
concat: {
  dist: {
    src: [
      'css/base.css',
      'css/sytax/emacs.css', // change this to another theme if you prefer, like vim.css and run grunt
      'css/octicons.css'
    ],
    dest: 'css/<%= pkg.name %>.add.css'
  }
}
```

## License
* see [LICENSE](https://github.com/nsdffd/blogtest/blob/master/LICENSE) file

## Version
* Version 4.0.2

## Contact
#### Developer

* Homepage: http://blogtest.rakibfiha.me
* e-mail: mrahman06@qub.ac.uk
