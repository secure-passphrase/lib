# lib
Libraries for converting cryptographic keys from/to passphrases and generating secure random passphrases.

Allows for easier memorization and paper storage.  Uses methods similar to those described in RFC1751.

The default dictionary included is an 8K common short english word extraction of Alan Beale's "2 of 12" public domain dictionary.

Currently implemented is a javscript library (<code>js/passphrase011.js</code>).

Tools (these run in browser):<br/>
  - <a href="http://secure-passphrase.github.io/tools/bitcoin.html">Convert bitcoin keys from/to passphrases</a><br/>
  - <a href="http://secure-passphrase.github.io/tools/dictionary.html">Create custom dictionaries</a><br/>
  - <a href="http://secure-passphrase.github.io/tools/test.html">Test the javascript library</a><br/>

Numeric key to passphrase:<br/>
  - <code>pass = Passphrase.fromKey(key [, dictionary])</code>

Passphrase to numeric key:<br/>
  - <code>key = Passphrase.toKey(pass [, keylen [, dictionary]])</code>

Random generators:<br/>
  - <code>key = Passphrase.randomKey([keylen])</code><br/>
  - <code>pass = Passphrase.random([keylen [, dictionary]])</code>

Parameters:<br/>
  - <code>pass</code>: string of words from dictionary<br/>
  - <code>key</code>: a numeric byte array<br/>
  - <code>keylen</code>: # bytes in key, defaults to 32 bytes (256 bits)<br/>
  - <code>dictionary</code>: defaults to included 8K word dictionary

For example, a 32 byte key and 8K (8192) word dictionary produces 20 word passphrase (13 bits per word).

128 bit (16 byte) keys are considered secure for symmetric cryptography (encrypting files) and 256 bit keys are considered secure for elliptic curve cryptography (producing signatures).

For additional documentation, see <code>js/passphrase011.js</code>


