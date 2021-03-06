
[![CircleCI](https://circleci.com/gh/cyber-dojo/languages-start-points.svg?style=svg)](https://circleci.com/gh/cyber-dojo/languages-start-points)

- A docker-containerized micro-service for [https://cyber-dojo.org](http://cyber-dojo.org).
- The data source for the `choose a language & test-framework` page.

<img width="75%" src="https://user-images.githubusercontent.com/252118/97070783-fa349e80-15d2-11eb-85e3-e0a1201be060.png">

- Image is here [cyberdojo/languages-start-points](https://hub.docker.com/r/cyberdojo/languages-start-points/tags)
- The file [git_repo_urls.tagged](https://github.com/cyber-dojo/languages-start-points/blob/master/git_repo_urls.tagged) lists all the language-test-framework repositories (each repo contributes one `manifest.json`) to the image.
- The file [compressed.image_sizes.sorted](https://github.com/cyber-dojo/languages-start-points/blob/master/compressed.image_sizes.sorted) lists all the images named in these `manifest.json` files, together with their (compressed) sizes, in descending order.

***

The preferred way to create a language start-point image is using 'tagged' urls (where the seven
character url prefix is the first seven characters of a commit sha for the url).  
Eg, this command uses the [cyber-dojo](https://github.com/cyber-dojo/commander/blob/master/cyber-dojo) bash script to create a start-point image for 5 Ruby test-frameworks:
```bash
   cyber-dojo start-point create ruby-all \
      --languages \
        e889c83@https://github.com/cyber-dojo-start-points/ruby-approval \
        c1b2910@https://github.com/cyber-dojo-start-points/ruby-cucumber \
        6b72590@https://github.com/cyber-dojo-start-points/ruby-minitest \
        a9bd3a6@https://github.com/cyber-dojo-start-points/ruby-rspec    \
        3663c6f@https://github.com/cyber-dojo-start-points/ruby-testunit
```

Eg, this command uses the [cyber-dojo](https://github.com/cyber-dojo/commander/blob/master/cyber-dojo) bash script to create a start-point image for all test-frameworks in all languages:
```bash
  cyber-dojo start-point create cyberdojo/languages-start-points \
    --languages \
      $(cat git_repo_urls.tagged)
```

***

![cyber-dojo.org home page](https://github.com/cyber-dojo/cyber-dojo/blob/master/shared/home_page_snapshot.png)
