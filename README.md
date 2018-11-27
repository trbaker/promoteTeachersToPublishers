# promoteTeachersToPublishers
Reads ArcGIS Online users and promotes teachers (with certain usernames) to publishers.

Update SSO-created teacher account
As ArcGIS Online SSO assigns all new accounts to one role, this script can find certain differences in usernames and then changes those users' roles. The use case that drove this script requested inbound teachers be promoted to publishers while students remained as users in the system. Optionally, this script could be save to a .py file and set as a scheduled task.
This script returns all the members of an organization and then filters out:
non-SSO usernames (assumes SSO usernames must end with underscore subdomain)
usernames older than 1 week
usernames that don't contain six consecutive digits. This is a condition in this specific use case that differentiates student usernames from teacher usernames. You will need to change the regular expression used to differentiate between the teacher and student accounts in your situation.
A teacher tag is added and qualifying username promoted to org_publisher.
YOU SHOULD UPDATE LINES: 6, 12, 20(use your own regex)
Script based on ArcGIS Online API for Python 1.5.1, Python 3.6, Anconda 4.4
-trbaker/November 2018
