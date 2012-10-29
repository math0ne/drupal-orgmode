A drupal module and some associates elisp code that will allow you to manage drupal content in emacs org-mode, be aware that if you use this module to manage a content type, you cannot make any changes to that content through drupal.

FEATURES

* Manage a drupal content type with a directory of org files
* CCK Support
* Taxonomy Support
* Push based publishing (your site updates in real time)
* Node image Support
* URL Alias support
* Uses org generated html for body of post

![screenshots](http://floatsolutions.com/docs/screenshot.png)

INSTALLATION

* Install the drupal module
* Configure the drupal module
* Create a directory under your default files directory where the files will be kept
* Setup the variables below in your .emacs file
  
```elisp
(require 'org-publish)
(setq org-drupal-dir "C:\\Users\\math\\Dropbox\\home\\orgdrupal") ;;the local directory where you will store your site org files
(setq org-drupal-dir-remote "X:\\drupalorg\\sites\\default\\files\\drupalorg") ;;the drupal files directory where the published files will be stored (use a tramp address here to publish to your remote site)
(setq org-drupal-default-user "username") ;;the drupal username you want to publish under (must exist in drupal)
(setq org-drupal-default-category "A category") ;;any categories you want added to new posts by default
(setq org-publish-use-timestamps-flag nil) ;; this makes sure we publish even if no files are modified

;;optional push based publishing, comment out if you don't want to use
(setq org-drupal-secret "F487fEWw8764GFsiuwhfbw3rerRRW221")
(setq org-drupal-sitename "http://drupalorg.local")
(load-file "~/.emacs.d/drupalorg.el")
  ```
* Copy the drupalorg.el to the directory you specified above

USAGE

* To create a new post you would run: org-drupal-new-post
* To pubish run org-drupal-publish
* Drupal will update:
** When you log in as admin and force it from the admin screen
** On cron run
** If you have push basd publishing on when you run org-drupal-publish

TODO

* Allow editing of org files in drupal
* Pull changed org files into emacs
* More secure push based publishing (api module?)
* Create org specifice css
