Heroku buildpack: PhantomJS
=======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) of PhantomJS(http://phantomjs.org).

Usage
-----

Example usage:

```shell
$ heroku create --stack cedar --buildpack https://github.com/stomita/heroku-buildpack-phantomjs.git

# or if your app is already created:
$ heroku buildpacks:add https://github.com/stomita/heroku-buildpack-phantomjs

$ git push heroku master
```

or my version:

```shell

mkdir rem
git clone https://elasa:mypass@gitlab.com/elasa/ieee2.git
cd i*
git init
git add .
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
heroku apps:destroy --app=test-python-ieee --confirm test-python-ieee
heroku create --stack cedar-14 --buildpack https://github.com/ddollar/heroku-buildpack-multi.git
heroku apps:rename test-python-ieee
heroku git:remote -a test-python-ieee
#heroku buildpacks:set https://github.com/ddollar/heroku-buildpack-multi.git

rm -rf .buildpacks
git commit -am "make it better"

#echo "https://github.com/procrastinatio/heroku-buildpack-python-phantomjs" >> .buildpacks
#echo "http://github.com/srbartlett/heroku-buildpack-phantomjs-2.0.git" >> .buildpacks
echo "https://github.com/stomita/heroku-buildpack-phantomjs.git" >> .buildpacks
#echo "https://github.com/Heroku-elasa/heroku-buildpack-python-ieee.git" >> .buildpacks
echo "https://github.com/Heroku-elasa/heroku-buildpack-python.git" >> .buildpacks

git commit -am "make it better"
git add .
git commit -a  -m "first commit"
#git checkout -b  newbranch
git push heroku master

heroku config:add LD_LIBRARY_PATH=/usr/local/lib:/usr/lib:/lib:/app/vendor/phantomjs/lib
heroku run bash
vendor/phantomjs/bin/phantomjs


```
