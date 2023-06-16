# Personal Website

```
lexeme78557.github.io
```

This is a personal website using Jekyll to help host some interactive data visualizations. There are also some blog posts on randomly selected deep learning topics.

## Sources

This is an amalgamation of [portfolYOU](https://github.com/YoussefRaafatNasry/portfolYOU) and [4dcu.be](https://github.com/4dcu-be/4dcu.be).

[portfolYOU](https://github.com/YoussefRaafatNasry/portfolYOU) was used for:
 * overall style, taking off a few elements -- Blog, About, Projects all are included here
 * also progress bars for skills are modified to contain words, not percentages
 
[4dcu.be](https://github.com/4dcu-be/4dcu.be)
 * vega-lite additions -- found in the `_plugins` folder and the vega-added things in `assets/js`

# Info for how this was created

1. Start by searching for Jeykll themes: https://github.com/topics/jekyll-theme
2. pick the following: https://github.com/YoussefRaafatNasry/portfolYOU
3. clone and follow the "Installation" instructions here: https://youssefraafatnasry.github.io/portfolYOU/docs/
4. Added port
5. remove Gemfile.lock if needed
trying to install with: bundle install --path ~/.gem
5. `bundle install` in directory 

for local execution, please run
```
bundle exec jekyll serve
```

