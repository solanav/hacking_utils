*Disclaimer*: Do not hack from your home wifi. At least use a Whonix VM. Read the [The Hitchhiker’s Guide to Online Anonymity](https://anonymousplanet.org/) for protection. And please use bounces for your scary discovery. *This instant guide is for educational purpose only and I'm not gonna hold any responsibility for your security*. Please be careful.

These methods below are used by anyone from RF to average Dread users. They are very easy to pick up and get dirty. And I certainly used to be comfortable with these tricks.

- **File Upload Shelling** - Every defacer knows this method. You go to a target site, you use something like `dirbuster` to find the file upload page (I use web proxy like `zaproxy` because it's quicker), if you are lucky the upload form can allow any file, you can just upload the correct [webshells](https://github.com/BlackArch/webshells) for the right web-app. But most of the time you will encounter something like an image upload, which can be easily solved by adding an image header to your webshell. File upload shelling is often used along side with SQLi to gain access to server backend, because once you have a shell up you can do practically anything.

- **S3 and Azure** - Every blackhat knows this trick. Majority of the data dumps on the internet come from people hijacking S3 and Azure. There are a couple of ways you can get started. [There is a search engine for it.](https://buckets.grayhatwarfare.com/) For specific target there are a couple of tools you can use like `slurp` to enumerate the buckets linked to the site you need to find, `bucket-stream` and `shhgit` to gather open buckets or AWS keys from Certificate Transparency (CT) certstream. You don't even need an AWS key to download data from the S3, use `aws-s3-downloader`. As for Azure you can use `StorageExplorer` to access public blobs. Search up `Capital One` and `Paige Thompson` and read up how she did it with the S3 bucket. If you can please support and write letter to Paige, please fight for her to stay in woman's prison, the CA state government has denied her trans rights.

- **SQL Injection** - SQLi is done by query inputs that request the server to do things it shouldn't. SQL databases that are vulnerable to SQLi because their databases are unsanitized. Common technique is used with `GET` or `POST` HTTP forms. To test if a site is vulnerable you can insert a single quote `'` or in HTML encode `%27`. Beside dumping data, SQLi can be used for other things like like DBA privilege escalation for the SQL server's admins, or just creating webshell (backdoor) on the server with stacked queries for something like an OOB shell. Search up `sqlmap` and `bbqsql`, and please write and support `Jeremy Hammond`, he was released in January. Search up about Stratfor hack, which involved SQLi.

- **NoSQL** - You probably heard about the crypto exchange hacks once every while. A lot of these hacks involved NoSQL like MongoDB and CouchDB and it was unbelievable easy to siphon data from. All you need is a free `Shodan.io` account to search for either port `27017` or `27018`, `mongodump` to download data, and `bsondump` to output the raw BSON into readable JSON. All you need is a Whonix VM in Qubes. Anyway, I still don't know why but Chinese crypto exchanges love to use Mongo, and yet left their shit wide open.

- **REST API Scraping** - From 2018 to 2020 I scraped over 1000 Slack workspaces with open API access and collected 10 millions of users. Up until mid-2020, Slack had a Legacy API that could allow any user to download data from the whole workspace, and you can enumerate every user on the workspace with email, name, phone, profile pic and their Skype contact. Slack never made public about this despite I wasn't the only hacker who reported the problem to them. In the case of MoveOn it involved social engineering that got me into their workspaces. I modified `slackpirate` for dumping and used `Google CSE` to scrape the web for Slack invites and registrations such as `Heroku` or `TypeForm`

- **Phishing** - I was gonna write about how to ransomware with phishing but it gonna get me v&amp; for real so I'd keep this one short. Subcowmandante Marcos said this: *Social engineering, specifically spear phishing, is responsible for the majority of hacks these days.* There are many FOSS phishing frameworks out there like `king-phisher` `mercure` `gophish` `FiercePhish` `credsniper` which ironic because they are built for pentesting and here we are they can be used for fighting the state. Search up `powershell-empire` `p0wnedShell` `koadic` `powersploit` and `pupy`, learn how they work and what didn't work. Also, just for fun, [The Art of Mac Malware](https://taomm.org/vol1/pdfs.html) and [MalwareTech's guides](https://www.malwaretech.com/category/malware-analysis), please support `Marcus Hutchins` if you can.

---

I hope this guide can gives you some idea of where to start. I know, it's a whole lot of researching between DuckDuckGo, Wikipedia and StackExchange to learn about these. But I just want to prove that hacking can be learned easily without barrier and can be quickly used for your direct action. And these certainly aren't the only techniques, but I narrowed them down for learning purposes.

---

# Other resources for homework:

*Subcowmandante Marcos (Phineas Fisher) writings*: https://theanarchistlibrary.org/category/author/subcowmandante-marcos

*Advanced Penetration Testing*: https://www.academia.edu/32535497/Advanced_penetration_testing

The Grugq's *OPSEC: Because Jail is for wuftpd*: https://www.youtube.com/watch?v=9XaYdCdwiWU

CTF and Sandbox for testing: https://www.hackthebox.eu/ https://www.vulnhub.com/ https://dvwa.co.uk/

(honorable mention: https://hackthissite.org/)

r/SocialEngineering r/NetSec r/crypto r/privacytoolsIO r/privacy r/AskNetSec r/OpSec

---

> When we speak truth to power we are ignored at best and brutally suppressed at worst.

> - **Jeremy Hammond**

Stay safe and stay free, comrades!
