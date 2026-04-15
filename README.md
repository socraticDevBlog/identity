# identity

what if someone gets in touch with you and say they are `socratic.dev`

how would you validate that claim?

## using cryptography and `gpg`

### 1. download that [public-key.asc](https://github.com/socraticDevBlog/identity/blob/main/public-key.asc) file

### 2. import it to your gpg keychain 

`gpg --import public-key.asc`

### 3. validate that it has been properly imported to your gpg keychain

`gpg --fingerprint`

#### expect

```
pub   rsa3072 2025-09-24 [SC] [expires: 2026-09-24]
      CAC5 6323 864C 10F2 E043  E1FD D29B 5195 73AA DDD8
uid           [ unknown] socraticDev <hello@socratic.dev>
sub   rsa3072 2025-09-24 [E] [expires: 2026-09-24]
```

### 4. ask me to send you a signed message

only a signed message will prove that you really are talking to `socratic.dev`

I will send you a signed message like the one in this repository (<message.asc>)

### 5. verify the signature with gpg

`gpg --verify message.asc`

#### expect

```
gpg: Signature made Wed Apr 15 19:00:29 2026 EDT
gpg:                using RSA key CAC56323864C10F2E043E1FDD29B519573AADDD8
gpg: Good signature from "socraticDev <hello@socratic.dev>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: CAC5 6323 864C 10F2 E043  E1FD D29B 5195 73AA DDD8
```
