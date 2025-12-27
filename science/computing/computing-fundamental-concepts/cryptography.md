# cryptography

## encryption  
## hashing
- string of any length $\longrightarrow$ fixed length output
  - unsymmetric
    - easy to calculate
    - near impossible to reverse
  - susceptible to avalanche effect
    - small change in input causing drastically different output
  - collision-resistant
    - hard to find two different inputs leading to same hash
  - used in
    - authentification
      - password storage
    - data integrity verification
      - digital signatures
- security implications
  - hashed passwords : less sensitive
  - hashed password table still sensitive
    - brute force try and compare
      - hash common passwords and search for matching username
        - cracks common passwords like "password" rapidly
## digital signatures  
## secure communication  
## password protection
- <a href="#hashing" target="_blank">hasing</a>
- password strength
  - $N_{possibilities}$ $\longrightarrow$ brute-force resistance
    - <img src="https://img.ronzz.org/img/brilliant-graphics/cryptography/password-strength.gif" alt="password strength" style="width: 300px;">
      - 4-digit PIN is insecure !
      - mitigation strategy : limit on attempts
      - why your bank locks your card after a certain number of wrong PIN entries 
    - <img src="https://img.ronzz.org/img/brilliant-graphics/cryptography/password-strength-alphanumeric.gif" alt="password-strength-alphanumeric" style="width: 300px;">
    - <img src="https://img.ronzz.org/img/brilliant-graphics/cryptography/capture_25-12-2025-09-24-47.png" alt="log graph" style="width: 300px;">
    - numeric : $N_{possibilities}=10^n
    - alphanumeric : $N_{possibilities}=62^n$
  - caveats
    - non-random guess strategies
      - `excellent1`
        - 1 of 20 000 common English words
        - +1 digit
        - $N_{possibilities}=20000\cdot 10 = 200000$
        - roughly equivalent to 5-digit numeric password
        - ~ 1 sec to guess 
    - reused passwords
      - reused on an unsecure site
        - stolen or intentionally leaked by site owner
        - used as candidate for non-random guess brute force attack elsewhere
  - balance between memorability and security : 4 word passphrase
    - <img src="https://img.ronzz.org/img/brilliant-graphics/cryptography/password-strength-passphrase.gif" alt="passphrase strength" style="width: 300px;">
## authentication  

