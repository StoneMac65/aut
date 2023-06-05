# v0.2.0

- Add subcommand `aut protocol contract-abi-path` to print the path of the bundled ABI for the Autonity contract
- Add subcommand `aut protocol contract-src` to print the URL to the source of the Autonity contract used to generate the bundled ABI
- Add subcommand `aut protocol contract-version` to print the git commit of the Autonity contract used to generate the bundled ABI
- Add subcommand `aut protocol contract-address` to print the address of the Autonity contract 
- Add support for python 3.11 (gh-107)
- Improve messaging when querying validator info for an address that is not in the validator committee (gh-113)
- Add support for complex types in contract calls (gh-120)

### Docs

- Add examples how to execute contract calls 
- Update the development explanation for contributors

### Chore

- Use hatch as python tool to manage builds  (gh-116)
- Update dependency to autonity.py v1.0.0

### BREAKING CHANGES

- Remove DEFAULT_CHAIN_ID constants

# v0.1.4

- Added `contract deploy` command
- Fixed output of `node info` while node is syncing

# v0.1.3

- Use the name `aut` (Autonity Utility Tool) for all references to this tool
- Support for contract calls (queries and tx creation)
- Fix support for reading private keys from stdin
- Remove support for Python 3.11 for now

# v0.1.2

- Added command to generate validator address from enode

# v0.1.1

- Fixes for path handling in configuration attributes.

# v0.1.0

- Support for new protocol contract methods in Autonity v0.10.0. (See `aut validator bond --help` and `aut protocol --help` for details.)
- `--key-file` changed to `--keyfile` (for consistency with `--keystore` and the `keyfile` and `keystore` config file entries).
- Commands that generate new keyfiles (i.e. `aut account new` and `aut account import-private-key`) now fall back to writing to geth-style file names (of the form `UTC--<timestamp>--<address>` if no keyfile is specified.

# v0.0.5

- Message signing and signature verification
- Fixes to help text and parameters specs
- Output chainId and networkId from `aut node info`
- Output ATN quantities as units of Auton (instead of Wei)

# v0.0.4

- New token command for queries and operations on ERC20 tokens (including Newton and Liquid Newton).
- Value is now specified in WHOLE TOKEN UNITS (Auton, Newton, etc) unless a unit suffix is given.  E.g.
  - For Auton: `1gwei` still represents 1 GWei, but `1` now refers to 1 Auton instead.  Decimals can still be used, so `1finney` is the same as `0.001`.
  - For tokens (including Newton), only decimals (e.g. 0.001) can be used.  Maximum precision is determined by the token, and can be queried with `aut token decimals`. See --help text for details.
- Token balances are now always output in units of whole tokens, with decimals used to represent fractional parts (e.g. 1.01).
- Auton balances are still output in Wei.  This inconsistency will be addressed in a future release.
- Support for `attoton` units.
- Entropy for new accounts can be given via a file.
- Show enode of the attached node in `aut node info`
- Small updates to command help text.

# v0.0.3

- Small fixes for command line parameters

# v0.0.2

- Cleaned up some parameter handling
- Improved start-up times
- Added `account import-private-key` command

# v0.0.1

- First revision of the tool with functionality covering most Autonity operations.
