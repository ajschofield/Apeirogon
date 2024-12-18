# Apeirogon

A client-server program with customisable functionality through modules - the 'do-everything solution'.

# Abstract

Apeirogon is a proof-of-concept stateless engine capable of extensible
functionality, added through user-created modules that follow a
standardised format. A lot of big words, but it's designed to be the
'do-everything' computing solution. This can be as simple as basic
addition, or something more complicated such as one-hot encoding.

# Architecture

## Client

In its simplest form, a Rust client designed to send POST requests
to the server, and receive the response.

```
{
    "module": "one_hot_encode",
    "data": "agtatattggaggtgcgctttcctaaaacgag",
    "metadata": {
        "authToken": "ab43-k49g-k294"
    }
}
```

This is subject to change and just for illustrative purposes only.

## Server

The server uses Rust and dynamically loaded Lua-based 'modules'. Modules
are added by users, and clients can only execute scripts that have been
added in the plugins folder.
