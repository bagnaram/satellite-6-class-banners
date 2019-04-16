## Satellite 6.x Classification Banners


In order to add a spiffy classification banner to Satellite, the Foreman UI will need templating. The actions below are simeple and require two lines to be added.

The banner definition below can be changed, while this one remains generic for dynamic data.

```
<div align='center' id='header-classification' style='font-family: Arial,sans-serif; font-size: 14px; line-height: 1.42857; border-top: 1px solid #FF000; border-bottom: 1px solid #FF0000; font-weight: bold; background-color: yellow' width='100%'> Dynamic Content- Highest Possible Classification is: FOO-BAR</div>
```

**Installation**


1. Add the lines below to `/usr/share/foreman/app/views/home/_topbar.html.erb` after line 33
```
<\button>
<button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-admin">
  <span class="glyphicon glyphicon-cog"></span>
</button>
<div class="container">
  <div align='center' id='header-classification' style='font-family: Arial,sans-serif; font-size: 14px; line-height: 1.42857; border-top: 1px solid #FF000; border-bottom: 1px solid #FF0000; font-weight: bold; background-color: yellow' width='100%'>
  Dynamic Content- Highest Possible Classification is: FOO-BAR
</div>
<!-- menu -->
<% if User.current %>
```

2. Restart Foreman and Apache for the changes to take effect.
```
# systemctl restart foreman httpd
```