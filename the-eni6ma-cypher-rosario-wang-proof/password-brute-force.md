# Password Brute Force

Jan 24, 2024

<figure><img src="https://miro.medium.com/v2/resize:fit:938/1*lXDB5zWZDSky9dWJWyWx7g.png" alt="" height="465" width="700"><figcaption><p>Password Complexity</p></figcaption></figure>

In the intricate field of cybersecurity, the creation and cracking of passwords stand as crucial elements. This arena is plagued with the difficulties of formulating strong passwords, further complicated by the persistent advisement to regularly change them. This narrative delves into the mathematical principles underlying these security protocols, revealing why simplistic passwords, such as those with only six characters or solely lowercase letters, are inadequate for robust security. Additionally, it unveils the strategies hackers use to decode passwords, even when direct access to password information is lacking in compromised data.

The essence of password security lies in the concept of a “space” of possibilities, determined by the password’s length and its compositional elements. A six-character password using only lowercase letters exists within a space of over 308 million possibilities. However, expanding this to a 12-character password incorporating a mix of uppercase and lowercase letters, numbers, and symbols, the possibility space escalates to a staggering 19 x 10²¹ possibilities, making it exponentially more challenging to crack. The entropy of these spaces is calculated using a specific formula, indicating the complexity of the password. Cybersecurity experts, recommend passwords or encryption keys that occupy a space of at least 100 bits, with 128 bits being ideal for long-term security. This is against the backdrop of Moore’s Law, which reflects the rapid advancement of computational power.

128 bits = 16 char

The pursuit of a secure password is vital for digital identity protection. The security of a password is dependent on the size of the possibility space, influenced by the character set size and the password length. Various scenarios illustrate the time it would take for hackers to exhaust all character combinations, considering the evolution of computing power. For example, a 6-character password using 26 character language it could be cracked within an hour as of 2019. In contrast, a 20-character password from a 200-character set, which creates a possibility space of 1.05 x 10⁴⁶, would take an estimated 222 years to crack.

## Cracking a 128 bit Password <a href="#id-0d3a" id="id-0d3a"></a>

Utilizing a 128bit or 16 char password selected from the alphabet (language) of only uppercase letters you would have 26¹⁶ which is : 142,734,349,946,674,900,000,000 or approximately in the short scale number system One hundred forty-two Sextillion, Seven hundred thirty-four Quintillion, Three hundred forty-nine Quadrillion, Nine hundred forty-six Trillion, Six hundred seventy-four Billion, Nine hundred Million possible permutations! This number can be represented in scientific notation as 1.427343499466749 × 10²³.

So how long would this take to crack? Well, that depends. In the realm of high-performance computing, we might tackle this with a NVIDIA A100 GPU for example. As of January of 2024, the A100 , known for its prowess in floating-point operations per second (FLOPS) is the fastest production GPU money can buy. To gauge A100 efficiency, consider the the brute-force task of iterating through 142,734,349,946,674,900,000,000 possibilities. Estimating the time required for this task hinges on the GPU’s operational throughput. The A100’s theoretical peak, approximately running at its fastest Core FP32 @19.5 teraFLOPS (19.5 trillion floating-point operations per second), serves as our benchmark.

[**\[NVIDIA A100 SPECS — LINK\]**](https://www.nvidia.com/content/dam/en-zz/Solutions/Data-Center/a100/pdf/nvidia-a100-datasheet-us-nvidia-1758950-r4-web.pdf)

How much would this cost you?\
— **1x nVidia A100 GPU MSRP: $27,671.00** [**\[Link\]**](https://www.google.com/search?q=nvidia+a100+cost)\
**— A100 consumes 2628 kWh / year of electricity.** [**\[Link\]**](https://folding.lar.systems/gpu\_ppd/brands/nvidia/folding\_profile/ga100\_a100\_pcie\_40gb)\
**— 2628 kWh @ $10 /hr = $26,280/year**\
_($10/kWh : Alaska cheapest price_ [_\[Link\]_](https://www.electricchoice.com/electricity-prices-by-state/) _)_

**229.5 years X $26,280 elect. = $6,000,000**\
**1x nVidia A100 GPU \~MSRP = $27,000** _(cost per A100 GPU)_\
**Grand Total : $6,027,000 in 1 yr.** _(not exactly chump change)_

To breach a single 16-character password, the investment required is substantial. The total brute force cost remains constant, irrespective of the number of GPUs utilized; adding more GPUs merely reduces the time necessary for cracking. To decrease the cracking duration to one year, one would need 229 NVIDIA A100 GPUs. Given that each A100 has an MSRP of $28,000, the initial hardware expenditure alone amounts to a staggering $6.2 million. Furthermore, the energy expenditure remains unchanged. Consequently, the total cost to decrypt a 16-character, 128-bit password within a year, while running the process in parallel, would be around $12,000,000.

> **229x2628 kWh/yr @$10/hr = $6 Million**\
> **229 A100s \* @$27k ea. = $6 Million**\
> **Grand Total: $12 Million in 1 yr.**

So you can crack the 128bit / 16 char password for approximately:

> **1 Year @ $12,000,000 or**\
> **228 Years @ $6,027,000**

<figure><img src="https://miro.medium.com/v2/resize:fit:891/1*3vpJO8knzC4dECqX7U9p_Q.png" alt="" height="440" width="665"><figcaption></figcaption></figure>

## Password Hacking is Not Worth It! <a href="#a807" id="a807"></a>

When it is all said and done, cracking a 16-character, 128-bit password could cost approximately:\
**— 1 YEAR: $12,000,000 ($12 Million)**\
**— 228 YEARS: $6,027,000 ($6 Million)**

The prospect of spending such an astronomical amount to crack a single 16-character, 128-bit password borders on the ludicrous, especially when considering the financial context of an average American. With an estimated cost of up to $12,000,000 to breach this password within a year, or $6,027,000 over 228 years, the economics of such an endeavor simply do not add up for the typical individual.

Most Americans, holding perhaps around $100,000 in their bank accounts at most, are far from justifying this level of expenditure for password cracking. The disparity between the potential financial gain from accessing an average individual’s account and the immense resources required to crack such a secure password makes it an implausible and unwise investment. This vast expense is more akin to the budgets of large-scale corporate or governmental operations, not something justified in attempting to access the assets of an average person. Hence, for the average American, the notion of deploying such extensive resources to crack a single password is not only financially unreasonable but also defies practical logic.

The sheer impracticality of brute-forcing a 128-bit password renders it a highly unattractive endeavor for any hacker. With the astronomical costs and time involved, attempting to crack such a password is akin to digging a tunnel to the other side of the Earth with a spoon — a futile and economically senseless pursuit. For the average Joe, this translates to a reassuring level of security. The average person’s digital assets or bank account, typically not exceeding extraordinary amounts, are realistically far from the radar of a hacker contemplating such a gargantuan task. The economic return simply doesn’t justify the herculean effort and resources required. Therefore, for the everyday individual, the threat of a brute force attack on a 128-bit password is about as concerning as the chances of being struck by a meteorite while picking up the morning newspaper. In the vast landscape of cybersecurity threats, this particular scenario is one that the average person can comfortably place low on their list of worries.

## The Mathematics Behind Passwords <a href="#id-212b" id="id-212b"></a>

The realm of password creation and cracking is an ever-evolving battleground in the world of cybersecurity. We’ve all encountered the frustration of crafting a password only to be met with rejection for being too weak, and the constant advice to change passwords regularly. But what exactly makes these measures essential for safety? In this exploration, we delve into the mathematical foundation of these security recommendations, shedding light on why a mere six characters won’t cut it for a strong password and why the use of lowercase letters alone is discouraged. Additionally, we’ll unveil how hackers can decipher passwords, even in cases where stolen data lacks direct password information.

## Understanding the Logic <a href="#fd4e" id="fd4e"></a>

When tasked with generating a password of specific length and element combinations, your choice resides within the realm of all unique options adhering to those criteria — the “space” of possibilities. For instance, if you’re instructed to use six lowercase letters, like afzjxd, auntie, secret, wwwwww, you’re dealing with a space containing 26⁶ possibilities, totaling 308,915,776. Each letter choice is independent, resulting in a password space size derived from the product of these possibilities (26 x 26 x 26 x 26 x 26 x 26 = 26⁶).

Expanding to 12-character passwords that can include uppercase and lowercase letters, digits, and symbols (!, @, #, $, %, ^, &, ?, /, and +), you’re presented with 72 possibilities for each of the 12 characters. The possibility space balloons to 72¹², nearly 19 x 10²¹ possibilities, dwarfing the initial space by over 62 trillion times. The computational effort required to crack a 12-character password is staggeringly impractical compared to the simpler 6-character counterparts.

## Crunching the Numbers <a href="#id-19ad" id="id-19ad"></a>

Computing the size of these spaces entails counting the binary digits in the number of possibilities, represented as N in the formula 1 + integer(log2(N)). This formula strips away the decimal portion, rounding down to a whole number, giving you the bits of entropy — 29 bits for the 6-character space and 75 bits for the complex 12-character scenario.

## Striving for Security <a href="#id-2dfe" id="id-2dfe"></a>

Leading cybersecurity authorities like the French National Cybersecurity Agency (ANSSI) advocate for possibility spaces with a minimum of 100 bits for passwords or encryption system keys requiring absolute security. They suggest a 128-bit space to ensure security over several years, categorizing 64 bits as very weak, 64 to 80 bits as weak, and 80 to 100 bits as moderately strong. The influence of Moore’s Law, where computational power doubles approximately every two years, underscores the need for robust passwords that can withstand the test of time.

## The Quest for a Strong Password <a href="#id-0790" id="id-0790"></a>

A truly robust password, as defined by ANSSI, might involve a 16-character sequence drawn from a set of 200 characters, yielding a formidable 123-bit space. However, such passwords become challenging to memorize. Hence, stringent requirements are typically imposed on automatically generated passwords, while user-generated ones are more forgiving in terms of length.

## Additional Safeguards <a href="#id-4806" id="id-4806"></a>

Beyond password complexity, other measures come into play. The simplest is to block access after three failed attempts, a strategy familiar from credit card security. Alternatives, like exponentially increasing waiting times for successive failed attempts while allowing a reset after a long period, have been proposed but may prove ineffective in certain scenarios, especially when attackers remain undetected or system configurations hinder intervention after multiple failed attempts.

## The Duration of Password Cracking: A Mathematical Perspective <a href="#id-504d" id="id-504d"></a>

Creating a secure password is crucial to safeguarding your digital identity, and the effectiveness of a password’s security depends on the size of the possibility space it’s chosen from. This space, denoted as T, is determined by two key factors: the length of the list of valid characters in the password, A, and the number of characters in the password, N. The size of this space, T, can vary significantly. In this exploration, we’ll delve into several scenarios, each with its own values for A, N, and T, and calculate the time, D, it would take for hackers to exhaustively try every character permutation one by one. We’ll also consider how long it would take before the possibility space could be searched in under an hour, factoring in Moore’s law (the doubling of computing capacity every two years) and the assumption that a computer can explore a billion possibilities per second in 2019.

The Results:

1\. If A = 26 and N = 6, then T = 308,915,776

* D = 0.0000858 computing hour
* X = 0; it is already possible to crack all passwords in the space in under an hour

2\. If A = 26 and N = 12, then T = 9.5 × 10¹⁶

* D = 26,508 computing hours
* X = 29 years before passwords can be cracked

3\. If A = 100 and N = 10, then T = 10²⁰

* D = 27,777,777 computing hours
* X = 49 years before passwords can be cracked

4\. If A = 100 and N = 15, then T = 10³⁰

* D = 2.7 × 10¹⁷ computing hours
* X = 115 years before passwords can be cracked

5\. If A = 200 and N = 20, then T = 1.05 × 10⁴⁶

* D = 2.7 × 10³³ computing hours
* X = 222 years before passwords can be cracked

**Understanding the Vector of the Attack Surfaces**

When attackers gain access to encrypted passwords or password “fingerprints,” they often have a window of opportunity to crack the actual passwords, provided their intrusion goes undetected. To comprehend the intricacies involved in such attacks, let’s revisit the concept of the possibility space. While previous discussions assumed users choose passwords at random, the reality is quite different. People tend to select passwords they can remember, such as common words, surnames, first names, or short phrases, rather than arbitrary strings of characters. This behavior exposes passwords to vulnerability from dictionary attacks, where attackers systematically cycle through lists of frequently used passwords. These attacks are particularly effective due to the nonrandom selection of passwords, which significantly reduces the possibility space and, consequently, the number of attempts needed to crack a password.

Here are the first 12 entries from a commonly used password dictionary, ranked by frequency:

1\. 123456

2\. password

3\. 12345678

4\. qwerty

5\. 12345

6\. 123456789

7\. letmein

8\. 1234567

9\. football

10\. iloveyou

11\. admin

12\. welcome

These lists may vary by region and time. For four-digit passwords (e.g., smartphone PINs), common choices tend to be predictable, with 1234, 1111, and 0000 topping the list. Additionally, analyzing the frequency of letter usage or double letters in a language allows attackers to plan effective attacks. Some methods exploit password structures or combinations of simple strings, further accelerating the password detection process. It’s clear that understanding these vulnerabilities is crucial for enhancing password security.

## Safeguarding Passwords: The Power of Hash Functions <a href="#c4dd" id="c4dd"></a>

In the realm of online security, the protection of user passwords is paramount. Rather than storing the actual passwords of their clients, internet servers employ a clever technique involving “fingerprints,” which are sequences of characters derived from the passwords. These fingerprints prove to be invaluable in making it exceptionally challenging, if not impossible, for hackers to misuse stolen data.

The transformation from passwords to fingerprints is achieved through the use of cryptographic hash functions. These algorithms meticulously convert a data file, denoted as F, regardless of its length, into a unique sequence referred to as h(F), the fingerprint of F. For instance, the SHA256 hash function takes the phrase “Nice weather” and transforms it into a 64-character hexadecimal fingerprint:

_DB0436DB78280F3B45C2E09654522197D59EC98E7E64AEB967A2A19EF7C394A3 (equivalent to 256 bits)_

Notably, even a minor alteration in the file results in a completely different fingerprint. For example, changing the first character of “Nice weather” to lowercase (“nice weather”) generates a distinct SHA256 fingerprint:

_02C532E7418CD1B57961A1B090DB6EC37B3C58380AC0E6877F3B6155C974647E_

Robust hash functions produce fingerprints that resemble random sequences, making it practically impossible to reverse-engineer a data file from its fingerprint. These functions are designed in a way that finding a specific data file with a given fingerprint becomes a computationally infeasible task.

Over time, various generations of hash functions have emerged. While SHA0 and SHA1 are now considered obsolete and insecure, the SHA2 generation, which includes SHA256, is deemed secure.

## Key Takeaways for Consumers <a href="#id-29f8" id="id-29f8"></a>

For users, the key takeaway is the importance of selecting passwords randomly. While some software can generate random passwords, it’s essential to be cautious as some password generators may use inadequate pseudo-random algorithms.

To determine if any of your passwords have been compromised, you can use a web tool called \[Pwned Passwords]\(https://haveibeenpwned.com/Passwords), which includes a database of over 500 million passwords obtained from various security breaches. Surprisingly, even seemingly secure passwords may have been seen before. For example, “e=mc2e=mc2” was found 114 times in the database.

While it may be challenging, it’s still possible to create original passwords. The web tool may not recognize less common passwords, such as “eyahaled” (your name spelled backward), “bizzzzard,” “meaudepace,” “modeuxpass” (puns on the French word for “password”), “abcdef2019,” and “passwaurde.” However, it’s essential to remain vigilant as new passwords may be added to the database over time.

## Advice for System Admins <a href="#id-9a90" id="id-9a90"></a>

System administrators should follow certain best practices to enhance security. The National Institute of Standards and Technology recommends using dictionaries to filter user password choices.

One critical rule for web server designers is never to store plaintext lists of usernames and passwords on the server. Such lists could be accessed by hackers if the site’s security is compromised or if a zero-day flaw in the system or processor is exploited.

A more secure approach is to encrypt the passwords on the server using an encryption key, which transforms them into seemingly random character sequences. However, this method has drawbacks, including the inconvenience of decrypting passwords for authentication and the risk of the decryption key being detected.

A superior method is the use of hash functions to generate fingerprints. These functions are one-way, making it nearly impossible to reverse-engineer passwords from fingerprints. Instead of storing paired usernames and passwords, the server stores username/fingerprint pairs. During authentication, the server computes the fingerprint of the entered password and checks it against the stored username/fingerprint pairs. Even if hackers access the list, they cannot deduce user passwords.

For added security, a technique known as “salting” is employed. This involves adding a unique random string of characters to each password before hashing it. Salting prevents identical passwords from having the same fingerprint. The server’s database includes three components for each user: username, fingerprint (derived after adding salt), and the salt itself. Salting significantly complicates hackers’ attempts to exploit stolen lists of username/fingerprint pairs.

While no approach is entirely foolproof, these measures collectively bolster online security and reduce the risk of password breaches.

## Adaptation in the World of Hackers <a href="#e6b2" id="e6b2"></a>

In the ever-evolving landscape of cybersecurity, hackers constantly seek innovative methods to achieve their objectives. However, they face a dilemma: their options often require either substantial computing power or extensive memory resources, making them less than ideal. One compromise approach that hackers employ is known as the rainbow table method, a concept explained further below.

In the era of the Internet, supercomputers, and interconnected networks, the field of password security and cracking continues to undergo transformations. This unrelenting battle pits those striving to safeguard passwords against determined adversaries intent on pilfering and potentially exploiting them.

## The Rainbow Table Method: A Hacker’s Strategy <a href="#id-6310" id="id-6310"></a>

Imagine you are a hacker armed with a trove of username/fingerprint pairs and knowledge of the hash function, as discussed in “Making Hash of Hackers.” The password you seek exists within the possibility space of 12 lowercase letters, equating to 56 bits of information and a staggering 2⁶¹² possibilities (approximately 9.54 x 10¹⁶) for potential passwords.

As a hacker, you have at least two viable approaches:

**Method 1:** The brute-force approach involves systematically iterating through all possible passwords within the space. For each password, you compute its fingerprint, h(P), and check if it matches any entries in the stolen data. This method requires minimal memory since prior results are discarded with each new attempt. However, it is time-intensive. With a computer capable of running a billion tests per second, it would take roughly 1,104 days (or about three years) to complete the task. While not impossible, this approach becomes impractical when dealing with new sets of username/fingerprint pairs.

**Method 2:** This strategy entails precomputing and storing the fingerprints of all possible passwords in a large table. Then, when presented with a password fingerprint, you can rapidly identify the corresponding password in the stolen data. However, this method demands colossal memory resources, requiring approximately (9.54 x 10¹⁶) x (12 + 32) bytes, or 4.2 x 10¹⁸ bytes, equivalent to the storage capacity of 4.2 million one-terabyte hard disks. Clearly, this memory requirement renders Method 2 unfeasible.

Is there a middle ground that demands less computing power than Method 1 and requires less memory than Method 2? Indeed, there is. In 1980, Martin Hellman of Stanford University introduced an approach that saw refinements in 2003 by Philippe Oechslin of the Swiss Federal Institute of Technology in Lausanne. More recently, Gildas Avoine of the National Institute of Applied Sciences of Rennes (INSA Rennes) in France further enhanced this method. This approach strikes a balance, necessitating slightly more memory but significantly reducing the computing power required compared to Method 1.

## The Rainbow Table Vulnerability <a href="#id-4494" id="id-4494"></a>

The intricacies of cryptographic security are often epitomized by the elegant concept of rainbow tables, a method that intertwines ingenuity with computation to breach password protection. Our understanding of this method begins with a fundamental transformation, a function ‘R’, that converts a cryptographic fingerprint, h(P), into a new password, R(h(P)). This conversion facilitates the migration of data from the binary numeral system to a numeral system of K, corresponding to the number of permissible symbols in a password.

The creation of a rainbow table is a meticulous process of precomputation. Starting with a potential password, P0, its fingerprint, h(P0), is computed, followed by the generation of a new potential password, R(h(P0)), thus becoming P1. This iterative process continues, only storing the initial password, P0, and its corresponding end fingerprint, h(Pn), where h(Pn) uniquely features a starting sequence of 20 zeros. This rarity is grounded in probability, akin to a uniform random draw, where the likelihood of such an occurrence is approximately one in a million.

A vast number of these password/fingerprint pairs are computed and stored, representing an extensive sequence of passwords and their corresponding fingerprints. Notably, the storage requirement for a comprehensive database is significantly more efficient than other methods. With proper precomputation, the memory needed is a fraction of what would otherwise be required — a remarkable feat of efficiency and practicality.

In practical application, a stolen fingerprint, f0, can be traced back to its original password through a series of calculated steps. This involves repeatedly applying the functions R and h to generate a sequence of fingerprints until one matches the format of fm, which begins with 20 zeros. The corresponding original password, P0, is then identified from the table. Following this, the chain of fingerprints and passwords is recomputed until the original fingerprint, f0, is reached. The password preceding this fingerprint in the chain is the sought-after password.

**Transformation Function R and Hash Function h:**

_R_(_h_(_P_))

In this equation, _h_(_P_) represents the cryptographic fingerprint of the password _P_, and _R_ is the transformation function that converts this fingerprint into a new password.

Generation of a Data Point in a Rainbow Table; Initial password to first transformed password:

> _P_1​=_R_(_h_(_P_0​))

Subsequent transformations:

> _P_2​=_R_(_h_(_P_1​))
>
> ⋮
>
> _P_2​=_R_(_h_(_P_1​))

These equations represent the iterative process of transforming an initial password _P_o​ through its cryptographic fingerprint and subsequent passwords in the sequence.

Condition for Ending the Sequence; The sequence continues until the fingerprint ℎ(_Pn_​)begins with 20 zeros, represented as:

> _h_(_Pn_​)=00…0 (20 zeros)

Final Pair Stored in the Rainbow Table; The pair stored in the rainbow table is the initial password and the end fingerprint:

> \[_P_0​,_h_(_Pn_​)]

The pre-computation phase, albeit extensive, facilitates the rapid retrieval of any password associated with a known fingerprint. This is a testament to the efficacy of storing only the start and end points of each computational chain.

<figure><img src="https://miro.medium.com/v2/resize:fit:784/0*YpPiGUTMSt5SrPiG" alt="" height="240" width="585"><figcaption></figcaption></figure>

To elucidate, a hacker, armed with a stolen fingerprint (fingerprint X), would iterate through the R and h functions, creating a sequence of passwords and fingerprints. Upon reaching a fingerprint adorned with 20 leading zeros, the hacker consults the table to identify the corresponding starting password. The process is repeated from this identified password until a match with the stolen fingerprint is found. The password immediately preceding this matching fingerprint is the one linked to the stolen fingerprint.

In essence, rainbow tables represent a sophisticated balance between computational forethought and storage efficiency. By meticulously precomputing and storing key data points, it becomes feasible to decipher any password from its cryptographic fingerprint, unveiling the fragile balance between security measures and the perpetual advancements in cryptographic circumvention techniques.

**In this Discourse I covered:**

1. Password Strength Mathematics: We reveal why simple six-character passwords are insufficient, highlighting the importance of length and complexity in creating robust passwords.
2. Security Recommendations: I discuss advice from cybersecurity agencies, stressing the necessity of at least 100 bits of entropy for long-term password security and the benefits of longer, system-generated passwords.
3. Cracking a 128-Bit Password: I demonstrate the impracticality and enormous cost (about $12 million) of cracking a 16-character, uppercase-only password with 142.7 sextillion permutations using 229 NVIDIA A100 GPUs.
4. Expensive Endeavor: Emphasizes the futility and excessive cost of brute-forcing a 128-bit password, which is highly unrealistic and not a typical threat for the average person.
5. Guarding Against Cracking: We highlight additional security measures like account lockouts after multiple failed attempts to enhance protection against password cracking.
6. Predictable Password Dangers: We expose the risks of using common, weak passwords often found in dictionaries, underlining the importance of unpredictability in password selection.
7. Cryptographic Hash Functions: Explained the critical role of cryptographic hash functions in securing user data, focusing on one-way transformations for increased security.
8. User Recommendations and Tools: We offer practical advice for users on selecting random passwords and using tools like “Pwned Passwords” to check for compromised passwords, along with best practices for website security, such as not storing plaintext passwords and employing hash functions with salting.
