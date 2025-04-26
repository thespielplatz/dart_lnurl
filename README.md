# Dart LNURL 

This package was forked from https://github.com/bottlepay/dart_lnurl. Thank you for all your prework!

A Dart implementation of lnurl to decode bech32 lnurl strings. Currently supports the following tags:
- withdrawRequest
- payRequest
- channelRequest
- login

## Features

- ✅ Decode a bech32-encoded lnurl string.
- ✅ Handles LUD-17 non-bech32 lnurl string (lnurlw, lnurlp, lnurlc, keyauth).
- ✅ Make GET request to the decoded ln service and return the response.
- ✅ LUD-12: Comments in payRequest.

## Backlog

- Update tests to work without internet

Learn more about the lnurl spec here: https://github.com/lnurl/luds

# API Reference

`Future<LNURLParseResult> getParams(String encodedUrl)`
Use this to parse an encoded bech32 lnurl string, call the decoded URI, and return the parsed response from the lnurl service. The `encodedUrl` can either have `lightning:` in it or not.

`String decryptSuccessActionAesPayload({LNURLPaySuccessAction successAction, String preimage})`

When doing lnurl pay, the success action could contain an encrypted payload using the payment preimage. Use this function to decrypt that payload.