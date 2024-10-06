

**I'm using Windows Operating system. You can use whichever you like**
# 1. Getting started

Jekyll Installation requires ruby. So first let's install ruby.

1. Head onto https://rubyinstaller.org/downloads/ to download ruby runtime.
2. Select the required version ( I did the latest Ruby+Devkit 3.3.5-1 ).
3. Finish the installation by selecting default options.
4. Run `gem -v` to check if installation has succeeded.
5. If everything goes fine, you'll see the gem version.
6. Also make sure that you have `gcc` and `make`.

Install Jekyll bundler

1. After successfully installing ruby and gem, now we'll start installing Jekyll bundler.
2. Run `gem install jekyll bundler`
3. Let gem do it's thing.
4. After successful installation, run `jekyll -v`.
5. If you see the jekyll version, That’s it, you’re ready to use Jekyll!

# 2. Creating a new Jekyll website

1. Navigate to the path where you wish to create the new website.
2. Run `jekyll new <project-name>` ( . if you wish to create in `pwd` ).
3. Let Jekyll do its thing.
4. Try running `bundle exec jekyll serve`
5. If you get error related to `wdm` , simply open the `Gemfile` and comment following line:
	 `gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]`
6. Then re-run `bundle exec jekyll serve`.
7. The bundler will do it's thing and the website will be served at `localhost:4000`.

🥂 Congrats!  By this point, you've completed the basic setup of Jekyll and now we'll be moving onto building the project as per our needs.

