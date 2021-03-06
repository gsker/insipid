# Insipid
Insipid is a web-based bookmark manager similar to the
[del.icio.us service](https://en.wikipedia.org/wiki/Delicious_(website)).

Rename the `insipid-config.cgi.example` to `insipid-config.cgi` and edit it,
replacing the example values with those that match your system.  Make sure
that the line `dbtype` is set:

### For MySQL:
    dbtype = mysql

### For PostgreSQL:
    dbtype = Pg

Create a user and password for the database if you don't have one assigned
to you by your adiministrator or ISP.  Doing this is beyond the scope of this
readme file---refer to the MySQL or PostgreSQL server documentation for more
help.

Rename the `htaccess` file to `.htaccess` and add a `RewriteBase` clause to the
top, such as:

    RewriteBase /~luke/

You can optionally add `insipid.cgi` to the list of files in the
`DirectoryIndex` line (for example, `DirectoryIndex index.cgi insipid.cgi`).

The non-standard Perl packages required for use (with their Debian package
names) are:

|   Module        |     Debian Package     |
|-----------------|------------------------|
| `Date::Format`  |  `libtimedate-perl`    |
| `XML::Parser`   |  `libxml-parser-perl`  |
| `XML::Writer`   |  `libxml-writer-perl`  |

Once the configuration is finished, access the `insipid.cgi` through your
web browser at the URL you've configured and the database should be
automatically configured.

If you ever upgrade Insipid, the database schema will be automatically
updated upon access.

## In-Production Example
 * [madphilosopher's insipid bookmarks](https://b.cyxd.ca/)
