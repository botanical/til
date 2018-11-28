#### Ruby's require and require_relative

In Ruby, `require` is a method that loads a given file and allows you to reference and execute code from that file. 
`require` uses `$LOAD_PATH` to find files and
should be used to load external files like installed gems.

`require_relative`, on the other hand is used to load files from a "relative" path, and should be used to load
files that are within your directory. `require_relative` uses the current location of the file using the statement to load files.

