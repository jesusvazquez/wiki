# SABnzbd

### Example

```
sabnzbd:
  key: 123456
  url: http://localhost/sabnzbd/api?
  category: movies
```

### All possible parameters

```
sabnzbd:
  key: ...
  url: ...
  category: ...
  script: ...
  pp: ...
  priority: ...
  username: ...
  password: ...
```

## Override category

By setting [entry](/Entry) category you can override / specify sabnzbd category per item. To set it you can use plugins like [set](/Plugins/set), [manipulate](/Plugins/manipulate). pp stands for post processing, you can set a path to a script which sohould be called after sabnzbd downloaded the file. Further you can modify the Priority which is used for a file by sabnzbd with the priority parameter, the valid values can be found [[http://wiki.sabnzbd.org/api#toc36|here]].

See [this recipe](/Cookbook/Series/SeriesSabNZBd) for example how to set category from a series name.