# Reading Notes Class #14

<ol>

><li> Define the term “hashing”.

Hashing is a technique used in computer science and cryptography to convert an input (or 'message') of any length into a fixed-size string of characters or numbers. This fixed-size output is known as the hash value or hash code. The process of generating the hash value from the input is called "hashing."

Hashing functions are designed to be fast and efficient, ensuring that the transformation can be performed quickly. They are also deterministic, meaning that the same input will always produce the same hash value.

Hashing is commonly used for various purposes, including:

1) Data Integrity and Verification: Hashing is used to verify the integrity of data during transmission or storage. By generating a hash value before and after data transmission, one can ensure that the data has not been altered in transit.

2) Password Storage: Instead of storing plaintext passwords, systems store the hash of passwords. When a user tries to log in, the system hashes the entered password and compares it to the stored hash to authenticate the user.

3) Data Structures: Hashing is used in data structures like hash tables to efficiently retrieve and store data based on keys.

4) Digital Signatures: In cryptography, hashing is an essential component of digital signatures, ensuring data authenticity and non-repudiation.

5) Checksums: Hashing is used to generate checksums, which are small-sized values used to verify the integrity of larger data blocks.

It's important to note that while hash functions are designed to be one-way (i.e., given the hash value, it is computationally infeasible to reverse-engineer the original input), they are not encryption mechanisms. Hashing is primarily focused on creating unique, fixed-size representations of input data for various practical purposes.

</li>

><li> Explain to a non-technical friend what a hash function does to a password.

Imagine a hash function like a magic blender that takes your password as an ingredient and mixes it up to create a secret recipe. Once the password is mixed, it turns into a unique code, kind of like a secret fingerprint for your password.

Here's how it works:

1) Input Your Password: You provide your password as the ingredient to the magic blender.

2) The Mixing Process: The magic blender takes your password and mixes it up, transforming it into a completely different and scrambled version.

3) Unique Secret Code: The scrambled version becomes a secret code, just like a fingerprint that is unique to your password.

4) No Going Back: The amazing thing is that once the blender has mixed your password, there's no way to turn it back into the original password. It's like one-way magic!

5) Password Verification: Whenever you want to log in to a website or service, instead of storing your actual password, the website saves the secret code (the hash) created by the magic blender.

6) Logging In: When you enter your password to log in, the website uses the magic blender again to create the same secret code from your password. It then checks if the secret code matches the one it saved. If they match, you are granted access, and if not, you are denied access.

So, the magic of the hash function is that it keeps your real password safe and private. When you enter your password, it's transformed into a secret code that only the magic blender can understand. This helps keep your online accounts secure and protected!

</li>

><li> What does it mean to ‘salt’ a password?

To "salt" a password means to add an extra piece of random data, called a "salt," to the original password before hashing it. The salt is a random value that is different for each user and is generated for the purpose of making password hashes more secure.

Here's how salting works:

1) Generate a Salt: When a user creates an account or changes their password, a random salt value is generated specifically for that user. This salt is typically a random sequence of characters.

2) Combine with Password: The salt is then combined with the user's original password. For example, if the password is "password123" and the salt is "abc123," the result would be something like "password123abc123".

3) Hash the Salted Password: The combined salted password (password + salt) is then hashed using a cryptographic hash function, creating a unique and secure hash code.

4) Store Salt and Hash: The salt and the resulting hash code are both stored in the user's account record in the database.

5) Password Verification: When the user tries to log in, the same salt is retrieved from the user's account record. The entered password is combined with this stored salt, and the hash is computed again. The newly computed hash is then compared with the stored hash in the database. If they match, the password is correct, and the user is granted access.

By using a unique salt for each user, even if multiple users have the same password, their salted hashes will be different. This prevents attackers from using precomputed tables like "rainbow tables" to reverse-engineer passwords. Salting significantly improves password security and protects against common attacks like brute-force attacks.

Remember that salting is just one part of a comprehensive password security strategy. Other measures like using strong hashing algorithms (e.g., bcrypt, scrypt, or Argon2), enforcing password complexity, and implementing account lockout policies are also important to maintain robust security for user passwords.

</li>

><li> What piece of information would a hacker need to access in order to find the ‘salt’ string for your passwords?

The purpose of using a "salt" in password hashing is to add an extra layer of security to user passwords. The salt is generally considered to be public information and is typically stored alongside the hashed passwords in the database. Therefore, a hacker does not need to find the salt string separately because it is already available to them if they manage to access the hashed passwords in the database.

To elaborate:

1) Salt and Hash Storage: When a user creates an account or changes their password, the salt is generated, and the combined salted password is hashed using a cryptographic hash function. The salt and the resulting hash code are both stored in the user's account record in the database.

2) Database Breach: In the unfortunate event of a database breach or unauthorized access, if the hacker gains access to the user account records, they will have access to both the salt and the corresponding hashed passwords.

3) Attacker's Objective: The objective of the attacker is not to find the salt (as it is not a secret), but rather to obtain the hashed passwords. With access to the hashed passwords and the corresponding salts, attackers can attempt to use various techniques (such as brute-force attacks or dictionary attacks) to find the original passwords.

4) Importance of Secure Hashing Algorithms: The security of password hashing relies on the use of strong and computationally expensive hashing algorithms (e.g., bcrypt, scrypt, or Argon2). These algorithms make it extremely time-consuming and resource-intensive for attackers to crack the passwords, even with knowledge of the salt.

Remember, the salt itself is not meant to be a secret; its purpose is to add uniqueness to each user's password hash and prevent precomputed attacks (like rainbow tables). The real security lies in using a strong hashing algorithm and ensuring that passwords are long and complex enough to resist brute-force attacks. Additionally, protecting the database and implementing security measures, such as encryption and access controls, are crucial to prevent unauthorized access to sensitive user data.

</li>

><li> How does the Blowfish block cipher handle the increased computation speed of new computers?

The Blowfish block cipher, designed by Bruce Schneier in 1993, is a symmetric-key encryption algorithm that operates on fixed-size blocks of data (64 bits). It uses a variable-length key, ranging from 32 to 448 bits, making it suitable for a wide range of applications.

The Blowfish cipher was specifically designed to be computationally efficient, making use of a Feistel network structure and a combination of key-dependent S-boxes and P-boxes. This design allows Blowfish to take advantage of the increased computation speed of new computers without compromising its security.

Here's how Blowfish handles the increased computation speed of modern computers:

1) Feistel Network: Blowfish uses a Feistel network structure, which splits the input data into two halves and performs multiple rounds of encryption and decryption on these halves. Feistel networks are known for their simple, parallelizable structure, which allows for efficient implementation and better utilization of modern parallel processing capabilities.

2) Subkey Generation: Blowfish generates subkeys from the original user-provided key using a key expansion process. The subkey generation involves applying the key schedule multiple times, which adds complexity and diffusion to the encryption process. As computing power increases, Blowfish can increase the number of rounds or adjust the key schedule to maintain its resistance to attacks.

4) Variable Key Length: Blowfish supports key lengths ranging from 32 to 448 bits, making it adaptable to modern security requirements. Longer key lengths provide better security against brute-force attacks, but they might incur a slight computational overhead. The ability to choose the key length allows the algorithm to balance between security and performance based on the application's needs.

5) Efficient Operations: Blowfish employs simple bitwise operations and substitution-permutation networks (S-boxes and P-boxes) for its encryption and decryption processes. These operations are efficient to implement in hardware and are well-suited for modern computer architectures.

However, despite its efficiency, Blowfish is now considered a legacy encryption algorithm, and more modern encryption algorithms like AES (Advanced Encryption Standard) are widely recommended for new applications due to their stronger security properties and widespread industry adoption. AES has also been optimized for modern computer architectures and has been extensively analyzed and tested for security. If you are considering encryption for new applications, AES is generally a better choice than Blowfish.

</li>

 ><li>What are the issue with the two most common password hashes for Java (“Java password hash” and “Java password encryption”)?

The two most common approaches for password hashing in Java are:

1)Java Password Hashing with MessageDigest (e.g., MD5 or SHA-1):

* Issue: Using plain hashing algorithms like MD5 or SHA-1 for password hashing is no longer considered secure. These algorithms are fast and efficient, but they lack the required cryptographic properties to protect against modern attacks, such as brute-force attacks and rainbow table attacks. Moreover, due to their speed, they are vulnerable to GPU and ASIC-based attacks, where attackers can make use of specialized hardware to crack passwords quickly.

* Recommended: Instead of using MD5 or SHA-1, it is strongly recommended to use stronger cryptographic hashing algorithms like bcrypt, scrypt, or Argon2. These algorithms are purposely designed to be slow and computationally expensive, making them more resistant to brute-force attacks.

2) Java Password Encryption (e.g., using javax.crypto package):

* Issue: While using encryption might seem like a viable option for password storage, it is not the best practice. Encryption is a two-way operation, meaning that encrypted data can be decrypted back to its original form. Passwords should be stored in a one-way irreversible form to prevent unauthorized access even if the attacker gains access to the encrypted data.

* Recommended: The correct approach for password storage is to use a one-way cryptographic hash function designed for password hashing (e.g., bcrypt, scrypt, Argon2) along with a unique per-user salt. This way, even if the password hash is exposed, it will be computationally infeasible for an attacker to reverse-engineer the original password.
In summary, the issues with the two most common password hashing approaches in Java are mainly related to their security vulnerabilities. Using plain hashing algorithms (like MD5 or SHA-1) makes passwords susceptible to various attacks, and encryption should not be used for password storage due to its reversible nature. Instead, it is crucial to use slow, salted cryptographic hashing algorithms designed explicitly for password hashing to ensure strong security for user passwords.

</li>

<ol>

[HOME](../README.md)
