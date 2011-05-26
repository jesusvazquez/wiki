== Regexp ==

Use regular expression to Accept or Reject entries. !FlexGet uses python regexp format and all matching is done case insensitive. This plugin may look a bit scary but in reality you rarely want anything more than what simple examples describe.

=== Simple examples ===

Accept entries matching regexp(s).

{{{
regexp:
  accept:
    - regexp 1
    - regexp 2
}}}

Reject permanently entries matching regexp(s). This should be used when you absolutely do not want to download matching entries, even if some other plugin (ie. `imdb`, `series`) would deem them acceptable.

{{{
regexp:
  reject:
    - regexp 1
    - regexp 2
}}}

Multiple operations. This would be useful when grabbing some shows and they appear with unwanted languages as well.

{{{
regexp:
  accept:
    - show name
  reject:
    - german
    - sweden
}}}

== Set custom path ==

Any regexp rule can set custom path for matching entry.

=== Example ===

{{{
regexp:
  accept: 
    - regexp here: ~/custom/path
}}}

or

{{{
regexp:
  accept: 
    - regexp here:
        path: ~/custom/path
}}}

== Full syntax ==

{{{
regexp:
  <operation>:
    - pattern 1
    - pattern 2: <custom path>
    - pattern 3:
        [not]:
          - pattern 4
        [path]: <custom path>
        [from]: <entry field> # applies to this pattern
        [set]:
            <entry field>: <value>
  [rest]: <operation>
  [from]: <entry field> # applies to all patterns
}}}

^[] = optional, <> = value^

Available operations: {{{accept}}}, {{{reject}}}, {{{accept_excluding}}} and {{{reject_excluding}}}.
Configuration may contain any number and combination of different operations.

== Operations described ==

=== accept ===
mark matching entries as accepted

=== reject === 
mark matching entries as rejected

=== accept_excluding === 
mark everything else except matches as accepted

=== reject_excluding ===
mark everything else except matches as rejected

[[Include(wiki:FilterOperations)]]