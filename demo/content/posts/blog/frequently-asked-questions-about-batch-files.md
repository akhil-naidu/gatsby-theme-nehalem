---
title: Frequently Asked Questions About Batch Files
path: /frequently-asked-questions-about-batch-files
tags:
  - Cyber Security
metaImage: assets/faq.jpeg
featuredImage: ./faq.jpeg
excerpt: So now we’ve got a bunch of batch file viruses under our belt. Now it’s
  time to further solidify your understanding of batch scripting, so that you
  can start making your own useful batch files (malicious or not).
created: 2020-06-29T03:37:12.286Z
updated: 2020-06-29T03:37:12.334Z
---
So now we’ve got a bunch of [batch file viruses](https://blog.leewardslope.com/introduction-to-batch-file-viruses) under our belt. Now it’s time to further solidify your understanding of batch scripting, so that you can start making your own useful batch files (malicious or not). Read up on any new command’s help documentation before using them, or simply run them [inside a virtual machine](https://blog.leewardslope.com/setting-up-a-virtual-machine-to-practice-hacking).

Included below are some of the most common questions regarding batch files, in general. If you are to truly master the art of working with batch files (and the viruses you can make with them), you’ll need to know the answers to these. Batch file programming is very easy, even non-technical people can get the hang of it pretty quickly. Soon enough, you’ll be making your own little scripts (and viruses).

## 1. Should I use .bat or .cmd as the extension of a batch file?

Use either, it doesn’t matter (mostly). There are some [minor technical differences](https://en.wikipedia.org/wiki/Batch_file#Filename_extensions) between the two but nothing that we need to concern ourselves with while using them on modern Windows operating systems.

## 2. How to add comments to a batch file?

There are two ways to add comments to batch files:

* `rem`

  ```shellsession
  @echo off
  REM This line will be skipped by the interpreter
  ping leewardslope.com
  ```
* `::`

  ```shellsession
  @echo off
  :: This line will also be skipped by the interpreter
  ping leewardslope.com
  ```

## 3. How to make a batch file sleep or wait for X seconds?

Say you want to pause for 4 seconds. The following is a popular hack for doing this:

```shellsession
ping 127.0.0.1 -n 5 > nul
```

This command pings the localhost IP address. The parameter  `-n 5`  means it will ping five times. The first ping happens at `t=0` and there’s a time delay of 1 second between each ping so that gives us a 4 second delay where our batch file seems to be doing nothing. Finally, `> nul` eats up the output of the command so we don’t see it during execution.

Another way to set a timeout in a batch file is to simply use the `timeout` command:

```shellsession
timeout 4
```

This displays a countdown in the output window like:

```shellsession
Waiting for 3 seconds, press a key to continue ...
```

If you don’t want to see the countdown:

```shellsession
timeout 4 > nul
```

Be careful, the `timeout` command can be skipped by pressing any key. Also, the command `timeout x` means “sleep anywhere between x-1 and x seconds”, so it’s a little inaccurate.

## 4. How to run multiple batch files from within a batch file?

Say you have three batch files that you want to call from one `master.bat`. There’s a couple ways to run these other batch files from inside `master.bat`:

* This method will execute the batch files one after the other in the same process:

  ```shellsession
    call batch1.bat
    call batch2.bat
    call batch3.bat
  ```
* This method will spawn different command windows each running one batch file:

  ```shellsession
  start cmd /k call batch1.bat
  start cmd /k call batch2.bat
  start cmd /k call batch3.bat
  ```

## 5. How to echo a newline in batch files?

Using `echo.` you can print out a blank line.

```shellsession
echo hello
echo.
echo world
```

Make sure that there are no spaces between `echo` and `.`. The above snippet prints:

```shellsession
hello
world
```

## 6. How to run two commands in one line using cmd.exe or batch files?

* When working in a cmd.exe prompt: `echo hello & echo world`. This outputs: `hello world.`
* For batch files, use `&&` instead of `&` like `echo hello && echo world`.

## 7. How to check if a file exists from within a batch file?

We can do this by using the constructs `if` and `exist`:

```shellsession
if exist [INSERT_FILE_NAME_HERE] (
    echo file exists
) else (
    echo file doesn't exist
)
```

If you don’t care about `else` just leave it out. For example:

```shellsession
if exist myfile.txt echo file exists
```

## 8. How to write the output of a command to a file?

```shellsession
dir > output.txt
```

This will write the output of the command `dir` to `output.txt`.

## 9. How to execute a command N times (in a loop) in batch files?

For a single command, we can use the one liner:

```shellsession
for /l %%x in (1, 1, 100) do echo %%x
```

For looping multiple commands:

```powershell
for /l %%x in (1, 1, 100) do (
   echo %%x
   echo something else
)
```

**Explanation:** The iteration variable `%%x` is initialized to `1` and incremented by `1` after every iteration until it equals `100`. The above is for use in a batch file, for using in a command window directly use a single `%` instead of `%%`.

## 10. How to iterate through files and subdirectories within a directory?

For use in a command window:

* Files in the current directory: `for %f in (.\*) do echo %f`
* Subdirectories in the current directory: `for /D %s in (.\*) do echo %s`
* Files in current and all subdirectories: `for /R %f in (.\*) do echo %f`
* Subdirectories in current and all subdirectories: `for /R /D %s in (.\*) do echo %s`

For batch files, replace `%` with `%%`:

* Files in the current directory: `for %%f in (.\*) do echo %%f`
* Subdirectories in the current directory: `for /D %%s in (.\*) do echo %%s`
* Files in current and all subdirectories: `for /R %%f in (.\*) do echo %%f`
* Subdirectories in current and all subdirectories: `for /R /D %%s in (.\*) do echo %%s`

## 11. How to get a list of all running services from the command line?

The command `net start` will output a list of all the currently running services.

## 12. How to start or stop services from the command line?

```shellsession
net start [serviceName]
```

and

```shellsession
net stop [serviceName]
```

## 13. How to check for admin privileges in a batch file?

The command `net session` can be used to check whether the batch file has administrator privileges or not:

```shellsession
net session >nul 2>&1
if %errorLevel% == 0 (
    echo Success: Administrative permissions confirmed.
) else (
    echo Failure: Current permissions inadequate.
)
```

**Explanation**: First we direct the output and error streams of the `net session` command to `nul` and check whether the command executes successfully (errorLevel = 0), which means we have admin privileges, or the command receives an error (errorLevel!=0), which means we don’t have admin privileges.

## 14. How to check if a program is running or not in a batch file?

The following snippet checks whether `chrome.exe` (Google Chrome) is running or not:

```shellsession
tasklist /FI "IMAGENAME eq chrome.exe" 2>NUL | find /I /N "chrome.exe">NUL
if %errorLevel% == 0 (
    echo Program is running
) else (
    echo Program is not running
)
```

## 15. How to forcibly kill a process using batch files?

The command `taskkill` along with the `/f` modifier can be used to forcefully shutdown all processes that match the given name (the `/im` parameter). The process ID (`/pid`) can be used to kill a single instance (For example, one specific Google Chrome tab).

```shellsession
taskkill /f /im "Taskmgr.exe"
```

Note that you may require admin privileges to kill some processes.

## 16. How to quickly create a large file in Windows?

We can do this using `fsutil`.

```shellsession
fsutil file createnew [fileName] [length]
```

This creates a file with a name `fileName` and size `length` (in bytes). This would be a sparse file, i.e. composed of just a string of zeros. For example:

```shellsession
fsutil file createnew useless.txt 1024
```

will create a 1 kilobyte file named `useless.txt`.

## 17. How to copy all the files from one folder to another using a windows command?

`xcopy` is a utility built into Windows that does exactly this.

```shellsession
xcopy /s C:\source C:\target
```

Remember to enclose the path in double quotes if the path contains spaces (e.g: `"C:\Some Folder"`).

## 18. How to delete a folder along with all the subfolders and files?

The `rmdir` command is used to delete directories.

```shellsession
rmdir "FolderName" /s /q
```

* **/s** is used to specify removal of the entire directory tree under `FolderName`.
* **/q** specifies ‘quiet mode’, that is, delete without requiring confirmation.

## [](https://xeushack.com/frequently-asked-questions-about-batch-files#19-how-to-see-the-help-documentation-for-a-command)19. How to see the help documentation for a command?

Open up a command window and type `help [command_name]`. For example: `help taskkill`.

- - -

And that wraps up our little series on batch files (almost). You should now head out and start experimenting on your own. Who knows, you just might make something that can fly under the radar of an anti-virus. Now let’s look a few ideas for [making your own batch file viruses](https://blog.leewardslope/how-to-make-your-own-viruses).