

## update nokogiri
```console
 sudo gem install nokogiri 1.10.4
```


```console
hxm@hxm-desktop:/opt/Writing/patrickhuang888.github.io$ jekyll
Traceback (most recent call last):
	10: from /usr/local/bin/jekyll:23:in `<main>'
	 9: from /usr/local/bin/jekyll:23:in `load'
	 8: from /var/lib/gems/2.5.0/gems/jekyll-3.8.3/exe/jekyll:11:in `<top (required)>'
	 7: from /var/lib/gems/2.5.0/gems/jekyll-3.8.3/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
	 6: from /var/lib/gems/2.5.0/gems/bundler-1.16.4/lib/bundler.rb:107:in `setup'
	 5: from /var/lib/gems/2.5.0/gems/bundler-1.16.4/lib/bundler/runtime.rb:26:in `setup'
	 4: from /var/lib/gems/2.5.0/gems/bundler-1.16.4/lib/bundler/runtime.rb:26:in `map'
	 3: from /usr/lib/ruby/2.5.0/forwardable.rb:229:in `each'
	 2: from /usr/lib/ruby/2.5.0/forwardable.rb:229:in `each'
	 1: from /var/lib/gems/2.5.0/gems/bundler-1.16.4/lib/bundler/runtime.rb:31:in `block in setup'
/var/lib/gems/2.5.0/gems/bundler-1.16.4/lib/bundler/runtime.rb:313:in `check_for_activated_spec!': You have already activated jekyll 3.8.3, but your Gemfile requires jekyll 3.7.4. Prepending `bundle exec` to your command may solve this. (Gem::LoadError)

```
command error, using 
```console
bundle exec jekyll serve
```

[jekyll doc](https://jekyllrb.com/docs/)


发现_config.yml里url的配置没有加http，之前写的是patrickhuang888.github.io,生成出来的图片地址总是不对，比如变成https://patrickhuang888.github.io/misc/.../images/ide.jpg,  改成完整的url以后就正常了