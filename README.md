# c-comments

Given a number of filenames as arguments this tool scans the files and outputs
only the comments and strings withing double quotes. 

Everything else it blanks out, so it outputs the same number of lines as in
the original file. The comments and strings are shown at the same horizontal
position as they were in the original file.

You can use this to for example spell-check comments and strings and not have
it check the actual source code.

Note that this only strips out C89 comments and is unaware of C99 (`//`)
comments.
