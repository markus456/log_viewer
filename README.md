# MaxScale log viewer

This is a log file viewer for MariaDB MaxScale log files. The program is
intended to make it easier to isolate individual sessions from the MaxScale log,
especially when `log_info` has been enabled in MaxScale.

## Usage

```
log_viewer FILE [SESSION...]
```

The first argument to the program is the log file to read. Any additional
arguments after this are interpreted as session IDs which are used to filter the
output. For example, to limit the log file to sessions 3, 25 and 400 the
following could be used.

```
log_viewer /var/log/maxscale/maxscale.log 3 25 400
```

## Controls

The controls of the log viewer are:

```
→:         Next session
←:         Previous session
Shift + →: Go forward 100 sessions
Shift + ←: Go back 100 sessions
Up:        Scroll up
Down:      Scroll down
Page up:   Move up one page
Page down: Move down one page
'g':       Toggle global log interleaving
'f':       Filer to sessions that match this string (incremental)
'x':       Exclude sessions that match this string (incremental)
'o':       Only show matching lines
'r':       Reset filters
'm'        Interleave output of all filtered sessions
'n'        Include sessions with at least this many log lines
'/':       Find session by ID
'C'        Toggle color highlights for sessions
'N'        Next highlight color
'P'        Previous highlight color
'q':       Quit the program
```
