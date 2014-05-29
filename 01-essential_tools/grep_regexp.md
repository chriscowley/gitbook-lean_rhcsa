This is without a shadow of a doubt one of the most important things that any System Administrator does. When something is broken, or just not working as it should, your first port of call is the _logs_. This are (potentially) very big text files, and you will need to find what you need in them.

The primary tool for this is an old utility called `grep`. This looks through a given file for a given piece of text. The format is quite simple:

```
grep 'string to search for' filename
```

So if you want to know what packages have been installing you would run:

```
[root@test ~]# grep 'yum' /var/log/messages
Jun 27 13:34:45 localhost yum[2656]: Installed: 1:perl-Pod-Escapes-1.04-131.el6_4.x86_64
Jun 27 13:34:46 localhost yum[2656]: Installed: 4:perl-libs-5.10.1-131.el6_4.x86_64
Jun 27 13:34:47 localhost yum[2656]: Installed: 3:perl-version-0.77-131.el6_4.x86_64
Jun 27 13:34:47 localhost yum[2656]: Installed: 1:perl-Module-Pluggable-3.90-131.el6_4.x86_64
<...>
Jul 15 09:56:23 localhost yum[1177]: Updated: openldap-2.4.23-32.el6_4.1.x86_64
Jul 15 09:56:24 localhost yum[1177]: Updated: dbus-glib-0.86-6.el6.x86_64
Jul 15 09:56:26 localhost yum[1177]: Updated: libxml2-2.7.6-12.el6_4.1.x86_64
```

That command searched through /var/log/messages for every line that contains the text string `yum`.

If no file is specified, you `grep` takes its input from STDIN:

```
dmesg | grep 'e1000'
```

will find any mentions of an Intel gigabit NIC driver in the startup logs.

That little line is the most basic usage of `grep`. It is a lot more powerful than that. By using the flag `-E` you are no longer looking for a simple string in a file, but a _Regular Expression_ (or REGEX as they are called by those in the know). These strike fear into many, even seasoned, sysadmins; they can be extremely complicated, but you can start of quite simple fairly easily.

The simplest use of a Regex is the literal characters. This is effectively the same as an exact string match. Adding `-E` to the `grep` command above would have the exact results. The power of them come in when you start using the special characters (or metacharacters):

  * `|` is basically an *or* character. If you do not know if you are search an English or American document, you could use `colour|color` and if will find all instances of  *colour* in both languages.
  * `.` matches any single character. For example `q.e` matches *qwe*, *qre* or any other 3 character string that starts with `q` and end in `e`.
  * `[ ]` denotes a _character class_ which matches one of the several characters.
    * `gr[ea]y` matches either *grey* or *gray*, but not *greay*.
    * Adding a `-` between the characters denotes a range. `[0-9]` will match any *single digit* number.
    * These can be combined, so `[0-9a-fA-F]` will match any single digit hexadecimal number.
    * Starting with a `^` negates the class. `q[^u]` means "*q* followed by a character that is not *u*", such as *iraq is*, but not *question*.
  *  `^` is the beginning of a line. `^[hc]at` matches *hat* and *cat*, but only at the start of a line.
  * `$` is the end of a line. `[hc]at]$` matched both *hat* and *cat* at the end of a line.
  * `?` matches the preceding element 0 or 1 times. `ab?c` matches *ac* and *abc*. 
  * `*` matches the preceding element 0 or more times. `ab*c` matches *ac*, *abc*, *abbc*, *abbbc* and so on.
  * `+` matches the preceding element 1 or more times. `ab+c` matches *abc*, *abbc*, *abbbc* and so on. 
  * `{m,n}` matches the preceding element at least `m` times and a maximum of `n` times. So `a[2,3]` will match *aa* and *aaa*. 

If you want to search for any of the above characters then you need to *escape* them using `\`. So \[.\] will match any single character that is enclosed in square brackets.  
