# f#
<a href="https://developer.mozilla.org/en-US/docs/Web">MDNWeb</a><br/>
<a href="https://portswigger.net/web-security">PortSwigger</a><br/>
<a href=""></a><br/>
<a href="https://owasp.org/www-community/attacks/">Owasp-Attacks</a><br/>
<a href="https://owasp.org/www-project-top-ten/">Owasp-Top10</a><br/>
<a href="https://owasp.org/www-community/Vulnerability_Scanning_Tools">ScanningTools</a><br/>
<a href="https://www.mozilla.org/en-US/security/bug-bounty/">MDNBB</a><br/>

<h2>Web Application basics</h2>
Learn how a request works, HTTP headers, JSON requests, how a browser works, how they communicate and send data to the servers, DNS etc. <a href="https://developer.mozilla.org/en-US/docs/Web">MDN Web</a>

<b>Common scope vulnerabilities.</b> You will need to know common scope vulnerabilities such as Remote Code Execution (RCE), Cross Site Request Forgery (CSRF), Cross Site Scripting (XSS), Injections (SQL, Command etc.), Clickjacking, Open Redirects, etc.

<b>Read blogs.</b> Learn new techniques from other bug bounty hunters so that you can test it out during your testing.

>If you are new to Bug Bounty program, you might not feel confident that you can find something a public program. This is something that a lot of hackers are struggling with. If you haven’t found a lot of security vulnerabilities yet, it might payoff to practice on Capture The Flag (CTF). Exploiting something for the first time is difficult and eye-opening. Apply the same structure if you would apply when looking in real targets as this help you a build a solid foundation and will help you to become an amazing hacker. Use bug bounty as a way to expand your knowledge and not as a race. Write simple scripts and use available tools to expand the process of expanding attack surface [...] Understand the web application and figure out what assets the web application are trying to protect. Think like an engineer of the web application. (Jobert Abma, Hackerone Cofounder)

<b>Learn how to make and then break.</b> You need to know how a web or mobile application is developed first so that you can understand how the thing works and hence how it can be broken down. This is beneficial for your long-term development rather than being a hunter that only knows how to send payloads (obtained from internet). Build a few web applications to understand how the web architecture works.

> From <a href="https://twitter.com/spaceraccoonsec/status/1250403032971407360?s=20"> Spaceraccoon's tweet</a>: To be blunt, I don't automate. I tried building a pipeline and failed. You can succeed just by learning the fundamentals. Check out @PortSwigger's web academy, watch @NahamSec's stream, read @Hacker0x01 disclosures. And learn how to build what you're hacking.

<section aria-labelledby="a_few_key_messages"><h2 id="a_few_key_messages"><a href="#a_few_key_messages">A few key messages</a></h2><div class="section-content">
<h2>A web application cannot trust any data from the web browser</h2>
<p>Almost all of the security exploits in the previous sections are successful when the web application trusts data from the browser. Whatever else you do to improve the security of your website, you should sanitize all user-originating data before it is displayed in the browser, used in SQL queries, or passed to an operating system or file system call.</p>
<div class="notecard warning" id="sect6">
  <p><strong>Warning:</strong> The single most important lesson you can learn about website security is to <strong>never trust data from the browser</strong>. This includes, but is not limited to data in URL parameters of <code>GET</code> requests, <code>POST</code> requests, HTTP headers and cookies, and user-uploaded files. Always check and sanitize all incoming data. Always assume the worst.</p>
</div>
<p>A number of other concrete steps you can take are:</p>
<ul>
  <li>Use more effective password management. Encourage strong passwords. Consider two-factor authentication for your site, so that in addition to a password the user must enter another authentication code (usually one that is delivered via some physical hardware that only the user will have, such as a code in an SMS sent to their phone).</li>
  <li>Configure your web server to use <a href="/en-US/docs/Glossary/HTTPS">HTTPS</a> and <a href="/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security">HTTP Strict Transport Security</a> (HSTS). HTTPS encrypts data sent between your client and server. This ensures that login credentials, cookies, <code>POST</code> requests data and header information are not easily available to attackers.</li>
  <li>Keep track of the most popular threats (the <a href="https://owasp.org/www-project-top-ten/" class="external" target="_blank">current OWASP list is here</a>) and address the most common vulnerabilities first.</li>
  <li>Use <a href="https://owasp.org/www-community/Vulnerability_Scanning_Tools" class="external" target="_blank">vulnerability scanning tools</a> to perform automated security testing on your site. Later on, your very successful website may also find bugs by offering a bug bounty <a href="https://www.mozilla.org/en-US/security/bug-bounty/faq-webapp/" class="external" target="_blank">like Mozilla does here</a>.</li>
  <li>Only store and display data that you need. For example, if your users must store sensitive information like credit card details, only display enough of the card number that it can be identified by the user, and not enough that it can be copied by an attacker and used on another site. The most common pattern at this time is to only display the last 4 digits of a credit card number.</li>
</ul>
<p>Web frameworks can help mitigate many of the more common vulnerabilities.</p></div></section>
