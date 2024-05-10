# Scene

A unit of design that encapsulates a set of reactive event relationships, which are expressed through Bindings. Scenes run asynchronously and can be in one of three states:

- Disarmed, Inactive
- Armed, Inactive
- Armed, Active

When a Scene is activated/deactivated it is built on/off:

- Armed, Inactive -> Building On -> Active
- Active -> Building Off -> Inactive, Armed