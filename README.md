> Note from DevRel Kinsta

So, first of all, using package.json to manage processes is a good idea but it then requires manually adding buildpacks, so in the end, it's quite a pain :D

## What I did
- removed the package.json
- you created a lock on your Mac, so it only had arm64-darwin-22. I added x86_64-linux
- I created a Procfile with a web process - thanks to this, everyone who will add this repo will get this process added as default, but if you deployed it once, you have to update it in the Processes tab in mykinsta
- the launch process builds and executes the server - bundle exec jekyll build && ruby -run -e httpd _site
