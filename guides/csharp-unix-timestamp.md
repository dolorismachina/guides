# Get Unix time in C#

In JavaScript getting the current Unix timestamp is trivial, with the ``` Date.now() ``` function which returns the number of milliseconds elapsed since 1st January 1970.

``` DateTime.Now ``` static property in C#, which someone familiar with JavaScript's ``` Date.now() ``` might first look at when trying to get the current timestamp, is ``` DateTime ``` object that contains all kinds of information about the current date and time which, while incredibly useful, doesn't actually include the timestamp so commonly used in development.

In recent versions of .NET, ``` DateTime ``` class includes a static field ``` DateTime.UnixEpoch ``` that holds the ``` DateTime ``` object containing information about the date and time on 1st January 1970. Using ``` DateTime.Now ``` and ``` DateTime.UnixEpoch ``` the current timesamp can be found with no more than a few lines of code.

```c#
// Get time elapsed since 00:00:00.0000000 UTC, January 1, 1970 as a DateTime object.
var timeElapsed = DateTime.Now - DateTime.UnixEpoch;

// Get the timestamp as seconds.
var seconds = Math.Floor(timeElapsed.TotalSeconds);

Console.WriteLine($"Seconds elapsed: {seconds}");
```

Results in

```sh
$ Seconds elapsed: 1626736656 
```

```c#
// Get the timestamp as milliseconds.
var milliseconds = Math.Floor(timeElapsed.TotalMilliseconds);

Console.WriteLine($"Milliseconds elapsed: {milliseconds}");
```

Results in

```sh
$ Milliseconds elapsed: 1626736656207 
```
