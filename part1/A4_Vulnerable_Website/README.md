**Vulnerable website Identified –**
http://users.ece.cmu.edu/~pgrover/files/
The identified vulnerable website is a publicly accessible directory hosted by Carnegie Mellon University. This website by found by operating on the prompt "index of /" "parent directory" in the search engine which returned a number of vulnerable websites such as this.
**Vulnerabilities Identified –**
1)The website uses HTTP protocol instead of HTTPS, which means the data transmitted between the user and the server is not encrypted.
2)The website also exposes an open directory listing, allowing anyone to view and access the files stored on the server without proper authentication.
**Why is it vulnerable?**
These vulnerabilities make the website insecure for several reasons. The use of HTTP means that data transmission is not protected making its vulnerable to interception. This makes the connection relatively insecure as attackers on the same network can intercept or monitor the data being transmitted. Furthermore, the open directory listing exposes files that may contain sensitive or unintended information. The page displays a list of files including pdfs, images and folders which can be freely accessed and downloaded.

