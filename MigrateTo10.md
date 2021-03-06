= Migrating from 0.9 to 1.0 (beta) =

First install the new version [wiki:Install instructions].

== Migration ==

Copy your old session and configuration files to new home, recommended place {{{~/.flexget/}}}.

!FlexGet 1.0 imports some information from 0.9 but not all. At the time of writing this only already downloaded content is imported.

== Deprecated plugins ==

Some plugins have been replaced with new ones.

=== Patterns, Ignore and Accept ===

These plugins have been removed. You'll need to convert these to use new [wiki:Plugins/regexp regexp] module. Luckily this is not hard to do since syntax is almost identical.

'''Patterns:'''

{{{
patterns:
  - foo
  - bar
}}}

Converts into:

{{{
regexp:
  accept:
    - foo
    - bar
}}}

'''Ignore:'''

{{{
ignore:
  - xxx
  - yyy
}}}

Converts into:

{{{
regexp:
  reject:
    - xxx
    - yyy
}}}

Combination of both would be:

{{{
regexp:
  accept:
    - foo
    - bar
  reject:
    - xxx
    - yyy
}}}

Unfortunately a bit more complex, but this is more explicit in !FlexGet terminology what it does and covers a lot more situations.

=== Regexp ===

Filtering system has been simplified a bit in 1.0, this requires few changes in regexp configuration. Remove all {{{rest: filter}}} lines.

=== Imdb ===

{{{filter_invalid}}} has been removed, instead use plugin [wiki:Plugins/imdb_required imdb_required].

== Series ==

Timeframe and name_patterns syntax has been changed, see documentation [wiki:Plugins/series#Timeframe here].

=== Cookies ===

New plugin, see [wiki:Plugins/cookies cookies]

=== Downloading complete feeds ===

In 0.9 feeds were implicitly downloaded completely without any accept. Ie

{{{
rss: <url>
download: <path>
}}}

Would have downloaded everything, this has been changed in 1.0 for various reasons.

{{{
rss: <url>
accept_all: yes
download: <path>
}}}

== First run ==

Your first run with 1.0 should execute all feeds, so use {{{--now}}} if necessary to force feeds with [wiki:Plugins/interval interval] to execute.