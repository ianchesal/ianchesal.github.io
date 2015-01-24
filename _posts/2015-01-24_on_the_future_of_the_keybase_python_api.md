---
layout: post
title: On the future of the Keybase Python API
---

I wrapped up the [discover](https://github.com/ianchesal/keybase-python/blob/develop/keybase/keybase.py#L43) feature on the development branch of the [Keybase Python API](https://github.com/ianchesal/keybase-python) last night. It's a pretty neat feature. It lets you look up Keybase users by other things: their Twitter handle, a Github username, a PGP key fingerprint, etc. See:

    >>> from keybase import keybase
    >>> kusers = keybase.discover(keybase.TWITTER, ['ircri']
    >>> kusers[0].name
    u'Ian Chesal'
    >>> primary_key = kusers[0].get_public_key()
    >>> primary_key.kid
    u'0101f56ecf27564e5bec1c50250d09efe963cad3138d4dc7f4646c77f6008c1e23cf0a'

And, the more I've thought about it today, the more I think it might be the last thing _I_ add to the API for a while. Granted, it's been a while since I've added anything at all, but from a public-key fetch-and-use standpoint the Python library has been pretty much feature complete for a half a year now. The `keybase.discover` method makes it geewhizneat now. The next step would be to implement user account editing and, this is where I might tap out, private key use and manipulation.

So why stop here?

While I like what [Keybase.io](https://keybase.io) is trying to do for PGP key discoverability we part ways when it comes to ideology around how they've implemented some things.

The first place where they and I diverge is on whether the command line tools and local APIs should be manipulating your local keyright and keys. Their [keybase command lne client](https://keybase.io/docs/command_line) does manipulate both _your_ personal, private keys and your existing `~/.gpg`-located keyring. The Keybase Python API in comparison does not. I think it's very wrong to let random command line tools in to this part of your private world. In particular, it's very dangerous to let tools do things with your private keys where you might be prompted for the password to use this key. I like to keep it to just the bare essentials: `gpg` and `gpg2` to be safe here. Yes, the code is availalbe and audit-able, but I'd just rather not play around in that particular sandbox. The Python API creates and destroys temporary keyrings that hold _only_ the Keybase-fetched public keys for users you are trying to work with. It never touches your primary keyring. Ever.

The second place where I diverge from the Keybase.io ideology is on where you private keys should be stored. The Keybase.io team would like you to trust them with your private keys. They'd like you to keep private keys on their servers. And while this enables nifty features in their command line tool and their web tool like signing things and decrypting things from one command interface, it's _highly dangerous to trust them with this information_. It's hard enough leaving it on your own computer, let alone their computers.

These two divergences put me at sort of an impasse. I don't ever want to download private keys from their servers because I don't think they should be there in the first place. And I don't want to much around in your default keyring where you keep your private keys on disk.

Maybe I'll figure out a safe way to interact with a default keyring, but for now I'm just not willing to go there. You have all you need to encrypt, decrypt and sign messages with your private key using the [GPG Toolkit](https://www.gnupg.org/). And there's already the _excellent_ [python-gnupg library](https://github.com/isislovecruft/python-gnupg) from Isis Lovecruft if you want a wrapper around your private keyring and GPG. I don't want to put more code between those layers and your private keys.

That means, for now, the Keybase Python API is pretty much done. It has all the interface it can have for working with public keys from the Keybase.io servers.

Look for the `1.0.0` release of the Keybase Python API to drop some time this weekend.

Go forth and sign all the things!
