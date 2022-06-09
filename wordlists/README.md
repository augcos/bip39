# __wordlists__
## Introduction
This is an auxliary library to the __[bip39 package](https://github.com/augcos/bip39)__. The wordlists package includes the wordlists for all languages provided in the __[BIP39 specifications](https://github.com/bitcoin/bips/blob/master/bip-0039/bip-0039-wordlists.md)__. The code is heavily inspired by __[Tyler Smith's wordlists](https://github.com/tyler-smith/go-bip39/tree/master/wordlists)__ package, but without any hash check.

## Example
```go
package main

import (
    "fmt"

    "github.com/augcos/bip39"
    "github.com/augcos/bip39/wordlists"
)

func main() {
    // we change the language to Portuguese
    bip39.SetWordList(wordlists.Portuguese)

    // we generate the random entropy
    entropy, _ := bip39.GenEntropy(256)
    // we generate the mnemonic corresponding to that entropy
    mnemonic, _ := bip39.GetMnemonicFromEntropy(entropy)
    
    fmt.Printf("Entropy: %x\n", entropy)
    fmt.Println("Mnemonic:", mnemonic)
}
```

## References
* [__BIP39 specifications__](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)
* [__Mastering Bitcoin__](https://github.com/bitcoinbook/bitcoinbook) by Andreas M. Antonopoulos: 
* Tyler Smith's __[BIP39 Go implementation](https://github.com/tyler-smith/go-bip39)__