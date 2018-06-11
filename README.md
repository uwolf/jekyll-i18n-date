# jekyll-i18n-date
## Tiny yet quite robust filter plugin for DateTime Localization in Jekyll
Based on deleted https://github.com/gacha/gacha.id.lv/blob/master/_plugins/i18n_filter.rb

## Usage
1. Add `jekyll-i18n-date` to `_plugins` folder of your site.
2. Create folder `_locales` and put some locale files from <https://github.com/svenfuchs/rails-i18n/tree/master/rails/locale> there.
3. Add lang variables to `_config.yaml` or to frontmatter of any page/post like this:
  ```yaml
  lang: de
  ```
4. Localize your Date/DateTime/Time variables with 
  ```liquid
   {{ page.date | localize: "%d.%m.%Y" }}
  ```
  or
  ```liquid
   {{ post.date | localize: "%d.%m.%Y", "es" }}
   
  ```
## Precedence
1. Lang parameter in liquid
2. Page
3. Site

If no locale file for language parameter is found in `_locales` or date is nil, default date format is displayed.
If "date" happens to be an integer value, it is converted with `Time.at()` (this rather suprising behaviour should probably be changed)
