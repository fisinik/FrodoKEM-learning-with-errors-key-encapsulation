# FrodoKEM: Learning with Errors Key Encapsulation

FrodoKEM, an IND-CCA secure key encapsulation (KEM) protocol based on the well-studied Learning with Errors (LWE) problem, which in turn has close connections to conjectured-hard problems on generic,
"algebraically unstructured" lattices. **FrodoKEM** is conjectured to be secure against quantum computer attacks.

This variant, includes countermeasures against some multi-ciphertext attacks and, thus, allows for key reuse
(i.e., it is suitable for applications in which a large number of ciphertexts may be encrypted to a single public key).

This reference implementation is a line-by-line transcription of the pseudocode from the [FrodoKEM specification](https://frodokem.org) and includes extensive comments.
The file [`frodokem.py`](frodokem.py) contains a Python3 class implementing all 6 variants of FrodoKEM.
The file [`nist_kat.py`](nist_kat.py) contains a minimal Python port of the known answer test (KAT) code.

It can be run as follows:

```sh
pip3 install bitstring cryptography
cd python3
python3 nist_kat.py
```

**WARNING**: This Python3 implementation of FrodoKEM is not designed to be fast or secure, and may leak secret information via timing or other side channels; it should not be used in production environments.
