## Resume

### Setup
1. Install Ruby
[RubyInstaller for Windows](https://rubyinstaller.org/downloads/)
```
ruby -v
```

2. Install Jekyll
```
gem install bundler jekyll
jekyll -v
```

3. Run & Debug 
```
bundle exec jekyll serve
```
Open the browser to `localhost:4000`

4. Build
```
bundle exec jekyll build
```
### Gem-based Theme
1. Create a `Gemfile`
```
source "https://rubygems.org"

gem "jekyll-theme-minimal-resume"
```

2. `bundle install`

---
For more details, refer to the [Jekyll docs](https://jekyllrb.com/docs/) </br>
This resume is made with a Jekyll theme, based on the [crispgm/resume](https://github.com/crispgm/resume/tree/master)