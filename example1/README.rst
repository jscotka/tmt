
.. _overview:

======================
NOTES
=====================

SYMLINKS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

  - Some symlinks inside FMF would be useful ``(mark ^)`` to link another tree item (if working with plans and profiles)
  - or use jinja or some another templating?


PLANS ~= PROFILES
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 -  basic priority: plans before profiles
 -  what is ``difference`` from perspective of profile and plan, from my PoV it is same, just add extra way how to override values for plans
 - maybe merge via cmd line option (after merging /etc/tmt and ~/.config/tmt): --merge /path/to/plans/oveeride/fmf/tree,
 - so tmt run ``--merge redhat (alias to some path /var/lib/tmt/redhat) --merge /custom/CI/volume/path``


PRIORITY
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 - sequence: system, project, (user, custom (cmdline e.g. CI)) ?
 -  /etc/tmt/plans/default /etc/plans/* "project"/plans ~/.config/tmt/plans CMDLINE(custom path(s) - CI) /etc/tmt/profiles ~/.config/tmt/profiles ...


HIDING OF TMT CONFIG ELEMENTS
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 - which one to hide?
 - /plans/default, /profiles, /options could be hidden, or part of some optional dotted tree like: /.tmt
 - to not spoil user plans data from project, but may be also useful to see it?

 - WARNING with customization, to avoid to store some data inside project and let it inside user configuration,
 - maybe better to explicitly do it via cmdline option --merge anyhow


MERGE LEVEL RULES
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 - merging has to be done at **tmt level**, to know ``semantics`` (what apply where, plans, tests, steps, whatevert)
 - in case of ``FMF level``, there is possible just ``full path merge`` when structure is known
 - or in case you do not know structure we have to invent some selectors (filters, to which node (leaf) apply items)
   - maybe both merging makes sense
 - merging works as applying to all children nodes
 - 