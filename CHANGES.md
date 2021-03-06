## v0.7.4 (2016-11-10)

* Protect flow reads from EPIPE exceptions (this can happens on Windows)
  (#104, @samoht)
* Log a message when FID pool is exhausted (#98, @talex5)
* Close socket if we get an error trying to connect (#97, @talex5)

## v0.7.3 (2016-07-18)

* remove the remaining uses of stringext (in the CLI example)

## v0.7.2 (2016-07-15)

* fix more dependency issues in the META file

## v0.7.1 (2016-07-15)

* switch to topkg
* make protocol-9p.unix depends on io-page.unix to workaround an issue
  the channel implementation
* remove the dependency to stringext
* fix missing dependencies causing a compilation issue on 4.03

## v0.7.0 (2016-07-12)

* remove dependency on ctypes
* support named pipes on Win32
* report Win32 errors
* client: don't clunk the fid after remove
* client: deallocate_fid should clunk before markind fid as free
* client: remove: always mark the fid as free
* client: don't clunk a fid if walk fails
* server: fix deadlock on Eof which prevents connection cleanup
* use the channel module for buffered packet reading
* unix: don't allocate per request, use a per-connection 32KiB buffer

## v0.6.0 (2016-04-10)

* server: supply no exception converter by default
* dependency on lambda-term (for the shell) is now optional
* add support for Win32
* use logs library
* reject messages longer than 640 KiB

## v0.5.0 (2016-03-01)

* remove an unnecessary copy in the read path
* add documentation for Server_unix_9p
* add a `shell` subcommand for the CLI with history and line-editing
* server: allow per-connection state
* unix: transform Unix.EPIPE into `Eof
* when pretty-printing, don't print payloads
* add wstat/update to client API
* lofs: sequential read/write increased by 9-10x
* server: handle errors in the dispatcher loop
* client: allow clients to handle I/O errors and recover

## v0.4.0 (2016-01-25)

* Remove OASIS from build system
* Remove use of -pack, now use the index module Protocol_9p with aliases
* Expose previously hidden Response.sizeof_header
* Expose previously hidden Response.Read.sizeof_header
* Add Request.sizeof_header
* Add Request.Write.sizeof_header

## v0.3 (2016-01-20)

* Add version/attach mount debug messages
* Pass initial connection attach to receive callback handler

## v0.2 (2016-01-04)

* Respect negotiated msize in read
* Add LICENSE file

## v0.1 (2015-12-13)

* Initial version
