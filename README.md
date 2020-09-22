<div align="center">

## PHP IP Address Logfile


</div>

### Description

A simple script to add IP addresses to a file called ip.txt - Can be easily expanded, but is mainly used to show how to open files, read from them, and add on to them.
 
### More Info
 
PSCode may screw up the formatting. If so, just either remove the comments or I'll come by and fix it by uploading, but it's such a small bit of code that I wouldn't want to do that.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[David A\. Edwards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/david-a-edwards.md)
**Level**          |Beginner
**User Rating**    |5.0 (25 globes from 5 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__8-1.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/david-a-edwards-php-ip-address-logfile__8-1450/archive/master.zip)





### Source Code

```
<?						// Quick IP log thing for SonicBlue by Davus
ignore_user_abort(1);				// In case the user closes the page first, it won't screw up
$f = fopen("ip.txt", "r");			// Open the file for reading
$l = fread($f, filesize("ip.txt"));		// Read from point 1 to the end (file size)
fclose($f);					// Got the data, enough for that
if (!strstr($l, $_SERVER['REMOTE_ADDR'])) {	// If the IP address is not already there....
$f = fopen("ip.txt", "a");			// Open for append (adds to end of file)
fwrite($f, $_SERVER['REMOTE_ADDR']."\n");	// Write their IP address to the logfile followed by new line
fclose($f); }					// Writing done, save/close the file
?>
```

