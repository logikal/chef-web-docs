.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

Use the |resource mdadm| resource to manage |raid| devices in a |linux| environment using the |mdadm| utility. The |resource mdadm| provider will create and assemble an array, but it will not create the config file that is used to persist the array upon reboot. If the config file is required, it must be done by specifying a template with the correct array layout, and then by using the |resource mount| provider to create a file systems table (fstab) entry.
