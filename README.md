# Djedi CMS

Django content management as it should be

[![Build Status](https://travis-ci.org/5monkeys/djedi-cms.png?branch=master)](https://travis-ci.org/5monkeys/djedi-cms)
[![Coverage Status](https://coveralls.io/repos/5monkeys/djedi-cms/badge.png?branch=master)](https://coveralls.io/r/5monkeys/djedi-cms?branch=master)
[![Downloads](https://pypip.in/v/djedi-cms/badge.png)](https://crate.io/package/djedi-cms)

## Install

Install djedi cms using pip in your desired python environment

```sh
$ pip install djedi-cms
```
> **Note:** djedi-cms is built on top of the content pipeline library [content-io][]


## Configure
* Add `djedi` to `INSTALLED_APPS`
* Enable django admin or include `djedi.urls` in your root urls with namespace `admin`
* Manage syncdb *(if using default django model djedi backend)*


### Enable djedi cms admin panel

Load `djedi_admin` in your base template and add admin tag at the bottom of your page
```django
{% load djedi_admin %}
<body>
    ...
    {% djedi_admin %}
</body>
```


## Usage

Load `djedi_tags` in a template and use `node` or `blocknode` tag

```django
{% load djedi_tags %}
<body>
    <h1>{% node 'page/title.txt' default='Djedi' %}</h1>

    {% blocknode 'page/body.md' %}
        ## I'm a djedi apprentice
        This is fun!
    {% endblocknode %}
</body>
```

[content-io]: https://github.com/5monkeys/content-io/
