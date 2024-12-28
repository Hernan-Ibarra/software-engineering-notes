
# Reviews

This is where I write reviews/notes specific to each of the resources listed in resources.md. Here 'coffee' means a regular-sized cup of black coffee, no sugar, of medium-high strength. 

___

## [How Does the Internet Work?][1] by Rus Shuler  

**STATUS**: Completed 

**EFFORT**: 2 coffees  

Excellent read, explains everything at a very high level without being too lossy with information. Only issue: it is a bit outdated, so the experiments don’t work or not as well (and some are Windows-specific). 

### What I learned: 

- Every computer needs an IP address (permanent or temporary) to communicate through the Internet. Also, we have effectively ran out of ‘static’ (i.e. permanent) IP addresses! Or we had, at least. Only in 2017 the new system of IP addresses, IP version 6, was made Internet Standard. The move was (is?) somewhat expensive and therefore slow. For context, the previous version of IP addresses, version 4, only allows 2^32 possible combinations (~4 billion), whereas this new version allows for 128 bits of information (~many trillion trillion possibilities).

- How do we turn a stream of bits into useful information? This is accomplished by using the **protocol stack**. The stack is just a bunch of rules and conventions to interpret data (bits) and direct it to the appropriate places. The protocol stack on the Internet is referred to as TCP/IP. It is divided into four sections:
    -  **Application Protocol Layer:** Protocols that are specific to an Internet service, such as the WWW or e-mail.
    - **Transmission Control Protocol Layer (TCP):** Protocol directing information (packets) to or from applications within the computer, or to/from the IP Layer below. The addresses it uses to manage the exchange are called ports.
    - **Internet Protocol Layer (IP):** Protocol for directing the packets to another computer, using IP addresses.
    - **Hardware Layer**: Converts packets (bits) to network signals and back. 

- Routers have a directory of IP addresses, so they can 'route' the data to their destination. However, routers usually do not have the necessary address. When that happens they send the packets to a 'bigger' router which has more IP addresses. There the process is repeated if necessary. 

- Most users don't deal directly with IP addresses but rather with **domain names**, e.g. 'www.google.com'. How does a web browser knows where to send the packets? Simple: it uses a **Domain Name Service (DNS)**. Similar to routers, a DNS has a directory, but in this case it contains information matching domain names to IP addresses. Again, if the DNS doesn't find the domain name, it relies on a bigger DNS, and so on.

- The World Wide Web (WWW) needs a protocol for sending and receiving websites. The most used one by far is HTTP. I won't summarize the description of how this works, since I think the explanation in the article is already succinct and well written. 

- I didn't understand much of the TCP/IP protocols from this article. Could use more details here. 

___

## [How Internet Infrastructure Works][2] by Jeff Tyson  

**STATUS**: Completed 

**EFFORT**: 1/2 coffee 

An OK read, not very informative (and outdated). Some valuable nuggets of information but not worth the time, in my opinion.

### What I learned: 

- [The Internet Society][11] is a thing! They "oversee the formation of the policies and protocols that define how we use and interact with the Internet", among other things. 

- Mbps = megabits per second. MBps = mega*bytes* per second.

- Internet backbones are typically fiber optic trunk lines

- URL = Uniform Resource Locator. Top-level domain examples = {.com, .gov, .edu, .org}. Second-level domain examples = {yahoo, google, microsoft}.  

- DNS servers cache: they save IP addresses for requests resolved with the help of another DNS.

- "All of the machines on the Internet are either servers or clients" 

- An ISP give you a temporary IP address (that is set for your session only) so that they don't have to remember IP addresses for every customer, only for the modems they have.

___

## [What really happens when you navigate to a URL][3] by Igor Ostrovsky

**STATUS**: Completed 

**EFFORT**: 0 coffees!  

10/10 article. Concise and to the point. Actually helpful diagrams. Concrete and relatable examples. It gave me some insight into how an HTTP interaction might actually go about.

### What I learned: 

- When the browser is trying to find an IP address from a domain name it checks the items below in order until if finds the address.
    1. Its own cache (Browser cache).
    2. OS cache.
    3. Router's cache.
    4. ISP's DNS cache.
    5. If it still hasn't found the address then the DNS will redirect to other DNSs recursively (all the way until the root nameserver).

- Suppose you are looking for the services of a big domain name, like facebook.com. Clearly one server will not be able to handle all the clients that are looking for facebook.com. There are several ways around this.
    - Round-robin DNS: The DNS lookup returns multiple IP addresses rather than just one.
    - Load-balancer: The DNS returns the IP address of a load-balancer, which is a piece of hardware that forwards requests to other servers, depending on how busy they are.
    - Geographic DNS: The DNS returns an IP address which depends on where the client is located. Great for static content (not great for dynamic content since the different servers across the world have to coordinate so they show the same information).

___

[1]: https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm
[2]: https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/Howstuffworks.htm
[3]: http://igoro.com/archive/what-really-happens-when-you-navigate-to-a-url/ 
[4]: https://zwischenzugs.com/2018/06/08/anatomy-of-a-linux-dns-lookup-part-i/
[5]: https://www.amazon.co.uk/Computer-Networks-Andrew-S-Tanenbaum/dp/0132126958
[6]: https://gaia.cs.umass.edu/kurose_ross/about.php
[7]: https://beej.us/guide/bgnet0/html/split/
[8]: https://youtube.com/playlist?list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&si=O_pxRwUrF6VOPZWi
[9]: https://youtube.com/playlist?list=PLowKtXNTBypH19whXTVoG3oKSuOcw_XeW&si=oqOGriWmCsl9z3jj 
[10]: https://jvns.ca/blog/networking-zine-launch/
[11]: https://www.internetsociety.org
[12]: https://www.youtube.com/watch?v=3QiPPX-KeSc
