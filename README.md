# ssh-keygen-pro

SSH keygen helper script to generate professional-quality keys.

Syntax:

   ssh-keygen-pro [user_identifier] [system_identifier] [unique_identifier]


Example that prompts you step by step:

    ssh-keygen-pro

The output is two keys:

  * A key with a passphrase
  * A key without a passphrase, suitable for automation

Each key has a public key file and private key file.


## Install

Option 1: download the file to wherever you want, then make it executable.

    cd /usr/local/bin/
    sudo curl -O https://raw.githubusercontent.com/SixArm/ssh-keygen-pro/master/ssh-keygen-pro
    sudo chmod +x ssh-keygen-pro

Option 2: clone the repo to anywhere you want, then add it to your path.

    cd /anywhere/you/want
    git clone https://github.com/SixArm/ssh-keygen-pro
    export PATH="$PATH:/anywhere/you/want/ssh-keygen-pro"

If you would like to help us by writing a package for any popular package manager, such as apt, yum, brew, etc., we wecome help.


## Details

Typical usage:

  * The user identifer is your email address e.g. "alice@example.com"
  * The system identifier is your host name e.g. "demo.example.com"
  * The unique identifer is a ZID e.g. "8af247255f409533f43c14cae2c07b97"

Example with args:

    ssh-keygen-pro alice@example.com host.example.com 8af247255f409533f43c14cae2c07b97

Output file naming convention:

  * user_identifer=system_identifer=unique_identifer=automation=id_rsa
  * user_identifer=system_identifer=unique_identifer=automation=id_rsa.pub
  * user_identifer=system_identifer=unique_identifer=passphrase=id_rsa
  * user_identifer=system_identifer=unique_identifer=passphrase=id_rsa.pub

Output file examples:

  * alice@example.com=host.example.com=8af247255f409533f43c14cae2c07b97=automation=id_rsa
  * alice@example.com=host.example.com=8af247255f409533f43c14cae2c07b97=automation=id_rsa.pub
  * alice@example.com=host.example.com=8af247255f409533f43c14cae2c07b97=passphrase=id_rsa
  * alice@example.com=host.example.com=8af247255f409533f43c14cae2c07b97=passphrase=id_rsa.pub


## Reasoning

SSH options:

  * Type: use the RSA algorithm because it's the widest used.
  * Bits: use 4096 because it's stronger than default 2048.
  * Generate two keys, one for automation and one with a passphrase.
  
Inputs:

  * Use the email address, so a user's keys sort together.
  * Use the host identifier, so a user's machine keys sort together.
  * Generate an ZID, akin to a UUID4 with only letters and numbers.

Output file name convention:

  * Separate items by using an equal sign, because it's not in email adddresses.


## Tracking

  * Command: ssh-keygen-pro
  * Version: 3.1.1
  * Created: 2015-12-20 or earlier
  * Updated: 2018-08-31
  * License: GPL
  * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
