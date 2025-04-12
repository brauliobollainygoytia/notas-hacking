# Rust fixme 1
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
[println!](https://doc.rust-lang.org/std/macro.println.html)
Rust has some pretty great compiler error messages. Read them maybe?

## Solución
Con la terminal de Kali Linux y Rust
```
──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ wget 'https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz'
--2025-04-11 20:17:39--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 2600:9000:20d1:e200:e:c945:f180:93a1, 2600:9000:20d1:f000:e:c945:f180:93a1, 2600:9000:20d1:3200:e:c945:f180:93a1, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|2600:9000:20d1:e200:e:c945:f180:93a1|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz                             100%[====================================================================================>]   1.38K  --.-KB/s    in 0s      

2025-04-11 20:17:39 (34.6 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ tar -xvf fixme1.tar.gz  
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills]
└─$ cd fixme1          
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme1]
└─$ cargo build    
    Updating crates.io index
  Downloaded xor_cryptor v1.2.3
  Downloaded either v1.13.0
  Downloaded crossbeam-utils v0.8.20
  Downloaded crossbeam-deque v0.8.5
  Downloaded rayon-core v1.12.1
  Downloaded crossbeam-epoch v0.9.18
  Downloaded rayon v1.10.0
  Downloaded 7 crates (388.2 KB) in 1.14s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme1)
error: expected `;`, found keyword `let`
 --> src/main.rs:5:37
  |
5 |     let key = String::from("CSUCKS") // How do we end statements in Rust?
  |                                     ^ help: add `;` here
...
8 |     let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", ...
  |     --- unexpected token

error: argument never used
  --> src/main.rs:26:9
   |
25 |         ":?", // How do we print out a variable in the println function? 
   |         ---- formatting specifier missing
26 |         String::from_utf8_lossy(&decrypted_buffer)
   |         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ argument never used

error[E0425]: cannot find value `ret` in this scope
  --> src/main.rs:18:9
   |
18 |         ret; // How do we return in rust?
   |         ^^^ help: a local variable with a similar name exists: `res`

For more information about this error, try `rustc --explain E0425`.
error: could not compile `rust_proj` (bin "rust_proj") due to 3 previous errors
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme1]
└─$ nano src/main.rs                      
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme1]
└─$ cargo build     
   Compiling rust_proj v0.1.0 (/home/kali/Documents/srss/GeneralSkills/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.60s
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme1]
└─$ cargo run  
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.01s
     Running `target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}:?
                                                                                  
┌──(kali㉿kali)-[~/Documents/srss/GeneralSkills/fixme1]
└─$ #Codigo corregido 
cat src/main.rs       
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        "{}:?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}

```