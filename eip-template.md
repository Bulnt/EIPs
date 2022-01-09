---
eip: <to be assigned>
title: Definition of message digestion on the Ethereum developer documents
description: Definition improvement on the message digest and signature description on the video page https://ethereum.org/en/developers/docs/accounts/
author: Bulnt
status: Draft
type: Standards Track
category:Core, Networking
created: 2022-01-09
requires 
---

This is the suggested template for new EIPs.

Note that an EIP number will be assigned by an editor. When opening a pull request to submit your EIP, please use an abbreviated title in the filename, `eip-draft_title_abbrev.md`.

The title should be 44 characters or less. It should not repeat the EIP number in title, irrespective of the category. 

## Abstract
Regarding line108: // Watch Austin walk you through hash functions, and key pairs in page https://ethereum.org/en/developers/docs/accounts/ 

## Motivation
Proposal 1:
Problem 1: In the stream of video tract at : 2:55 signature is described as "Signatures are basically taking the message and private key and signing something"
also in the video stream at 2:55 signing process is being described but in the output of SIGN function  message is shown as encrypted text. The process in reality is encrrption. 
Also according to reference stated below in the literature 
	the digital signature is technology that uses private key to Encrypt a hash value (=Message Digest). 
	DS= E[PRa, Hash (M)]
means that encryption by Pra is applied to the not message but hash of message. Message should not be encrypted because of digital signature is not the process of encryption of message. 
DS provides the integrity assurance instead of confidentiality (process of encryption input message)


Problem 2 : 
1.In the stream of video tract at : 4:31 function RECOVER is intented to describe Verification process of signature but in reality describing decrypion process of message.
Encryped message is being  used as input and decryped message as output.
2.The expression stated at streamn 5:19 "message plus signature equals signature. Signature plus message equals public key" conflicts with reference stated below. 

## Rationale
Solution for problem 1:
  1. In my opinion either RECOVER process should be replaced by DECRYPT function or message output of RECOVER should be open message and comparision of attached signature(hash of message encrypted by PRa ) by 
decryption of message hash by public key PUa. 
2. The expression stated at streamn 5:19 "message plus signature equals signature. Signature plus message equals public key" should be replaced by 
" encryption the hash of message by private equals signature.(DS= E[PRa, Hash (M)]). Signature decrption by public equals verification ( decrypt signature by public and take hash of message and compare the computed hash by sended hash as signature. DS= E[PUa, Hash (M)]) "
reference:Cryptography and Network Security: Principles and Practice 5th Edition,WILLIAM STALLINGS

Solution for problem 2:
1. In my opinion either SIGN process should be replaced by ENCRYPT function or message output of SIGN should be open message and attached signature(hash of message encrypted by PRa )
2. The expression stated in the video "Signatures are basically taking the message and private key and signing something" should be replaced by 
"Signatures are basically taking the message and private key and signing by encrypting the hash of message by private key"

  
  
## Backwards Compatibility

## Test Cases


## Reference Implementation


## Security Considerations


## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
