# Rust fixme 2
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html

## Solución
Con la terminal de Kali linux
```
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ wget 'https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz'
--2025-04-11 20:34:48--  https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 2600:9000:20d1:800:e:c945:f180:93a1, 2600:9000:20d1:ca00:e:c945:f180:93a1, 2600:9000:20d1:9c00:e:c945:f180:93a1, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|2600:9000:20d1:800:e:c945:f180:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1585 (1.5K) [application/octet-stream]
Saving to: ‘fixme2.tar.gz’

fixme2.tar.gz                             100%[====================================================================================>]   1.55K  --.-KB/s    in 0s      

2025-04-11 20:34:49 (14.6 MB/s) - ‘fixme2.tar.gz’ saved [1585/1585]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ tar -xvf fixme2.tar.gz 
fixme2/
fixme2/Cargo.toml
fixme2/Cargo.lock
fixme2/src/
fixme2/src/main.rs
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ cd fixme2 
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo build    
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme2)
error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
 --> src/main.rs:9:5
  |
9 |     borrowed_string.push_str("PARTY FOUL! Here is your flag: ");
  |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable                                                
  |
help: consider changing this to be a mutable reference
  |
3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
  |                                                        +++

error[E0596]: cannot borrow `*borrowed_string` as mutable, as it is behind a `&` reference
  --> src/main.rs:20:5
   |
20 |     borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
   |     ^^^^^^^^^^^^^^^ `borrowed_string` is a `&` reference, so the data it refers to cannot be borrowed as mutable                                               
   |
help: consider changing this to be a mutable reference
   |
3  | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
   |                                                        +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `rust_proj` (bin "rust_proj") due to 2 previous errors
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo build
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme2)
error: expected one of `:`, `@`, or `|`, found `)`
 --> src/main.rs:3:67
  |
3 | ...tring: &mutt String){ // How do we pass values to a function that we wan...
  |                       ^ expected one of `:`, `@`, or `|`
  |
  = note: anonymous parameters are removed in the 2018 edition (see RFC 1685)
help: if this is a parameter name, give it a type
  |
3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mutt String: TypeName){ // How do we pass values to a function that we want to change?
  |                                                                   ++++++++++
help: if this is a type, explicitly ignore the parameter name
  |
3 | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mutt _: String){ // How do we pass values to a function that we want to change?
  |                                                             ++

error: expected one of `!`, `(`, `)`, `,`, `::`, or `<`, found `String`
 --> src/main.rs:3:61
  |
3 | ...: &mutt String){ // How do we pass values to a function that we want to ...
  |            ^^^^^^ expected one of `!`, `(`, `)`, `,`, `::`, or `<`
  |
help: there is a keyword `mut` with a similar name
  |
3 - fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mutt String){ // How do we pass values to a function that we want to change?
3 + fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
  |

error[E0412]: cannot find type `mutt` in this scope
 --> src/main.rs:3:56
  |
3 | ...8>, borrowed_string: &mutt String){ // How do we pass values to a functi...
  |                          ^^^^ not found in this scope

error[E0061]: this function takes 3 arguments but 2 arguments were supplied
  --> src/main.rs:35:5
   |
35 |     decrypt(encrypted_buffer, &party_foul); // Is this the correct way to ...
   |     ^^^^^^^------------------------------- argument #3 is missing
   |
note: function defined here
  --> src/main.rs:3:4
   |
3  | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mutt String){ // Ho...
   |    ^^^^^^^                                                  ------
help: provide the argument
   |
35 -     decrypt(encrypted_buffer, &party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
35 +     decrypt(encrypted_buffer, &party_foul, /* String */); // Is this the correct way to pass a value to a function so that it can be changed?
   |

Some errors have detailed explanations: E0061, E0412.
For more information about an error, try `rustc --explain E0061`.
error: could not compile `rust_proj` (bin "rust_proj") due to 4 previous errors
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo build
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme2)
error[E0308]: mismatched types
  --> src/main.rs:35:31
   |
35 |     decrypt(encrypted_buffer, &party_foul); // Is this the correct way to ...
   |     -------                   ^^^^^^^^^^^ types differ in mutability
   |     |
   |     arguments to this function are incorrect
   |
   = note: expected mutable reference `&mut String`
                      found reference `&String`
note: function defined here
  --> src/main.rs:3:4
   |
3  | fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How...
   |    ^^^^^^^                           ----------------------------

For more information about this error, try `rustc --explain E0308`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo build
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme2)
error[E0596]: cannot borrow `party_foul` as mutable, as it is not declared as mutable
  --> src/main.rs:35:31
   |
35 |     decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way...
   |                               ^^^^^^^^^^^^^^^ cannot borrow as mutable
   |
help: consider changing this to be mutable
   |
34 |     let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
   |         +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo build
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.61s
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.02s
     Running `target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme2]
└─$ #Codigo corregido
cat src/main.rs
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}


fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12", "a0", "18", "03", "51", "03", "36", "05", "0e", "f9", "42", "5b"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}

```