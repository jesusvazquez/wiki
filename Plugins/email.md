= Email =

Send an e-mail based on a jinja2 template with feed results.

The default template will list of all succeeded (downloaded) entries and look like this:

{{{
Subject: [FlexGet] feedname: X new entries downloaded
Content: 
FlexGet has just downloaded X new entries for feed feedname:
- release title (torrent url)
- release title (torrent url)
- release title (torrent url)
- release title (torrent url)
}}}

{{{
Config:
  from          : the email address from which the email will be sent (required)
  to            : the email address(es) of the recipient(s) (required)
  subject       : the subject for the email (jinja replacement is supported)
  template      : name of the template file to use (default will be used if not specified)
  smtp_host     : the host of the smtp server
  smtp_port     : the port of the smtp server
  smtp_username : the username to use to connect to the smtp server
  smtp_password : the password to use to connect to the smtp server
  smtp_tls      : should we use TLS to connect to the smtp server ?
  smtp_ssl      : should we use SSL to connect to the smtp server ?
  active        : is this module active or not ?
}}}

Config basic example:

{{{
email:
  from: xxx@xxx.xxx
  to: xxx@xxx.xxx
  smtp_host: smtp.host.com
}}}

Config example with smtp login and multiple recipients:

{{{
email:
  from: xxx@xxx.xxx
  to:
    - xxx@xxx.xxx
    - yyy@yyy.yyy
  smtp_host: smtp.host.com
  smtp_port: 25
  smtp_username: my_smtp_login
  smtp_password: my_smtp_password
}}}

Config multi-feed example:

{{{
presets:
  global:
    email:
      from: xxx@xxx.xxx
      to: xxx@xxx.xxx
      smtp_host: smtp.host.com

feeds:
  feed1:
    rss: http://xxx
  feed2:
    rss: http://yyy
    email:
      active: False
  feed3:
    rss: http://zzz
    email:
      to: zzz@zzz.zzz
}}}

Default values for the config elements:

{{{
email:
  active: True
  smtp_host: localhost
  smtp_port: 25
  smtp_username:
  smtp_password:
}}}

Gmail example:
{{{
    from: from@gmail.com
    to: to@gmail.com
    smtp_host: smtp.gmail.com
    smtp_port: 587
    smtp_username: gmailUser
    smtp_password: gmailPassword
    smtp_tls: yes
}}}

== Built-In Templates ==

There are two templates that come built in.
 default:: This will send emails with a list of accepted entries, and/or a list of failed entries. (this template is used automatically if you do not specify one.)
 failed:: This will only send emails when there are entries that have failed.

== Custom Templates ==

You can create your own custom templates for the email plugin in the jinja2 templating language. They should be placed in <configpath>/templates, and their filename specified as the {{{template}}} option. See the [http://flexget.com/browser/trunk/flexget/templates/email/default.template default template] for an example.