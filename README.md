Bitcoin Core integration/staging tree
=====================================

This version of bitcoind has a built-in bruteforce attack for wallet master keys.
Start bitcoind as rpc server and connect with bitcoin-cli like this:

bitcoin-cli -rpcport=8888 -rpcuser=user -rpcpassword=pass crackpw

This command will block until the master key was found. Bitcoind will also not response as it is trapped into an endless loop until the master key was found. The master key is then announced to stdout in hex and written to a file (binary) 'master_key' in the working directory. The wallet is then opened and is not closing automatically.
