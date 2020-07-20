# Test GitHub Pages Deploy

Testing that that Github Pages can serve a Hugo site using the `personal-web` theme.

## Steps to Reproduce

In terminal:

```{sh}
mkdir <test_repo_name>
cd <test_repo_name>
mkdir themes
git init
cd themes
git submodule add https://github.com/bjacquemet/personal-web.git
cd ..
hugo --contentDir "themes/personal-web/exampleSite/content" --themesDir "themes"  --config "themes/personal-web/exampleSite/config.toml" -d "docs" --baseURL "https://<github_username>.github.io/<test_repo_name>"
git add --all
git commit -m "initial commit"
```

Create empty __<test_repo_name>__ repo on GitHub.  Then in terminal:

```
git remote add origin https://github.com/<github_username>/<test_repo_name>
git push -u origin master
```

in the settings for __<test_repo_name>__ set the Github Pages to serve from `docs`.