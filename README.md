# nettest

A copy of golang.org/x/net/nettest, tweaked for our own purposes.

The main change is that the tests in TestConn are run in parallel, which can save significant time (particularly helpful as these tests should be run multiple times). However, in the event of a deadlock, this can cause the resulting goroutine dump to be polluted with goroutines from other tests. To aid in debugging deadlocks, there is a 'single-threaded' version, which can be retrieved using `go get github.com/getlantern/nettest@single-threaded`.
