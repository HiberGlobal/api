# Changelog

When adding an entry to the changelog, a separate file should be made in this directory for that entry. This prevents
merge conflicts on releases with the changelog file. On a release, all files in this directory that are in the correct
format, will be added to the `CHANGELOG.md` file in the parent directory in lexicographical order.
The format of the filename should be:
```
WEB-<DESCRIPTIVE_NAME>.md
```
where `<DESCRIPTIVE_NAME>` can be anything that describes the change. A typical format
would be to use `WEB-<TICKET_NUMBER>-<DESCRIPTION>` where `<TICKET_NUMBER>` is the Jira ticket number that this change
refers to. If there are files in the directory that are not in the correct format, the CircleCI build will fail.

Finally, be wary of headers used in the changes. The text in a file will be added directly to `CHANGELOG.md`, so any
headers used here should be smaller than the headers for the version number in that file. If they are not (meaning less
than 4 #'s) the CircleCI build will fail.
