# __bip39__
## Introduction
This package is an implementation of the __[BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)__ specifications in the __[Go programming language](https://go.dev/)__. You can read the documentation __[here](https://pkg.go.dev/github.com/augcos/bip39)__.

## Example
```go
package main

import (
    "fmt"

    "github.com/augcos/bip39"
)

func main() {
    // we generate the random entropy
    entropy, _ := bip39.GenEntropy(256)
    // we generate the mnemonic corresponding to that entropy
    mnemonic, _ := bip39.GetMnemonicFromEntropy(entropy)
    // finally, we generate the 512-bit seed from the mnemonic, plus a passphrase
    seed, _ := bip39.GetSeedFromMnemonic(mnemonic, "passphrase")
    
    fmt.Printf("Entropy: %x\n", entropy)
    fmt.Println("Mnemonic:", mnemonic)
    fmt.Printf("Seed: %x\n", seed)
}
```

## References
* [__BIP39 specifications__](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)
* [__Mastering Bitcoin__](https://github.com/bitcoinbook/bitcoinbook) by Andreas M. Antonopoulos: 
* Tyler Smith's __[BIP39 Go implementation](https://github.com/tyler-smith/go-bip39)__