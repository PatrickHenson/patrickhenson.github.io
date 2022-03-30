# patrickhenson.github.io

This repository contains the contents of my personal website, hosted using GitHub pages.

For the best experience, visit [https://patrickhenson.com](https://patrickhenson.com).

## Build & Update


# Build local
bundle exec jekyll serve


# Install
```
# 1. Install Ruby
sudo apt -y install ruby ruby-dev

# 2. Update ~/.bashrc
# Add the following at the bottom:
export GEM_HOME=$HOME/gems
export PATH=$HOME/gems/bin:$PATH

# 3. Install Bundler and Jekyll
gem install bundler
gem install jekyll

# 4. Install dependencies and update
bundle install
bundle update

```

# Update
```
bundle update github-pages

# configuration file: ./_config.yml
# source: ./
# destination: ./_site

```

## Test Local

After building and serving, you can preview the Jekyll site at [http://localhost:4000](http://localhost:4000)

## License

The contents of this project are shared under the [Apache 2.0 License](https://opensource.org/licenses/Apache-2.0).  If you do choose to share or use any of the content I've generated, please let me know!  You can find my contact information in the project.
