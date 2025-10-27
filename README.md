# CS305
Projects for CS305: Software Security at Southern New Hampshire University

In this course, we worked with a hypothetical client named Artemis Financial, who had a financial planning application in dire need of security.
This application handled customer financial data from around the globe, and relied on Maven and the Spring Framework to manage all of its dependencies.
It was our job to analyze their application, run static tests using the OWASP dependency check tool, design layers of security by refactoring their code,
and ultimately provide them with secure file verification and authentication.

I believe I handled interpreting the dependency check results very well when we ran static testing on our client's application. I was able to suss out
many false positives within the results, as well as determine whether certain vulnerabilities were critical or not, which ultimately gave the client
better direction for improving their original codebase. Beyond static testing, it is important to code securely because it prevents users from having
their data stolen by malicious actors, it protects the integrity of data stored within an application or in transit, and it protects the reputation
of the company that owns that software, as their customers can continue to use their product without worrying about any of the issues I mentioned.

That being said, running the vulnerability assessment was initially very difficult for me because the codebase for the project was so out of date.
Many of the dependencies had not been updated in years, and the OWASP dependency checker had been updated far beyond the version of Java in which
the application was built. This led to many headaches and lots of troubleshooting back and forth with my professor, who somehow retained saint-like
patience throughout the entire ordeal (even though I was in full panic mode). Once we got it working, it was smooth sailing, and I was able to slowly
run through the rest of the vulnerability assessment flowchart without much trouble.

I was able to increase layers of security within Artemis Financial's application by applying some industry standard mitigations to the code. First,
I used the SHA-256 hash algorithm to create a hash key that could be used as a checksum for file verification. Next, I created a self-signed digital
certificate to demonstrate how the application could be made secure through the use of the HTTPS protocol. Granted, the self-signed certificate was
only for proof-of-concept: the real application would need to contact a third-party certificate authority to be issued a digital certificate that 
would enable SSL/TLS. This would allow all data moving to and from the application to be encrypted, protecting that data from interception as it could
not be decrypted without the server's private key. I believe I would use these techniques again in the future, along with static testing to create
secure web applications.

To make sure the code and software application were functional and secure after adding these layers to the code, I ran the OWASP dependency check once
and reviewed my code manually to make sure I had not accidentally introduced new vulnerabilities into my code. The dependency check did not detect any
vulnerabilities that did not already exist in the code (all of the outdated dependencies), and I made sure to follow good OOP principles when adding
my checksum and digital certificate. 

I would definitely use the OWASP dependency check tool again if I were developing another application using Java and Maven, as it was very useful
for tracking down outdated and exploited dependencies. I would also make use of the Oracle webpage dedicated to defining encryption algorithms, as
there are tons to choose from and there is absolutely no way I will remember each one and what, specifically, makes them useful over others.

If a potential employer wanted to see an example of my work to show my skills, knowledge, and expereience in this field, I would show them my Server
Controller Code and Summary from my Practices for Secure Software Report. I believe both of these demonstrate that I not only know how to implement a
good algorithm cipher for checksums, but I can also explain why that cipher works and how it adds security to the application.
