# @eth-optimism/contracts-bedrock

## 0.7.0

### Minor Changes

- e2faaa8b: Moves the L2ToL1MessagePasser to a new address and puts a LegacyMessagePasser at the old address.

### Patch Changes

- cb5fed67: Clarify intent with mintable token interfaces
- c427f0c0: Fixes to natspec docs
- d28ad592: Tweaks storage spacers to standardize names and use original types
- 76c8ee2d: Fix event names orderings for `OptimismMintableERC20Created`

## 0.6.3

### Patch Changes

- 88dde7c8: Uses assert rather than a require statements to check for conditions we believe are unreachable.This is more semantically explicit, and should enable us to more effectively use some advanced analysis methods in our testing.
- 7215f4ce: Bump ethers to 5.7.0 globally
- 249a8ed6: Fixed a backwards compatibility issue in which incorrect events were emitted during a failed deposit finalization on the L2 bridge.
- 7d7c4fdf: Makes spacers private and updates names to reflect slot, offset, and length.
- e164e22e: Makes finalizeWithdrawalTransaction not payable because it doesn't need to be and it was causing confusion throughout the codebase.
- 0bc1be45: Make the use of storage gaps consistent across contracts
- af3e56b1: Fix to Ensure the Oracle's owner and proposer accounts are unique
- 206f6033: Fix outdated references to 'withdrawal contract'
- 88dde7c8: Use assert statements for unreachable conditions.
- 8790156c: Simplifies the initialization function of the CrossDomainMessenger in Bedrock
- 515685f4: Update comments on GovernanceToken to match Seaport style.
- Updated dependencies [7215f4ce]
- Updated dependencies [206f6033]
  - @eth-optimism/core-utils@0.10.1

## 0.6.2

### Patch Changes

- 651a2883: Make spacer variables private in the Bridge and Messenger contracts so that they cannot be accessed in child contracts.

## 0.6.1

### Patch Changes

- 85232179: Add CrossDomainOwnable contracts
- 593f1cfb: Removes the blockedSystemMessages mapping in favor of a simpler approach to preventing messages from being sent to internal system addresses.
- f78eb056: Prevents v0 (legacy) messages from being relayed in the bedrock XDM.

## 0.6.0

### Minor Changes

- 7fdc490c: Removes initializer from StandardBridge in favor of immutables
- 3d228a0e: Updates the storage layout for the CrossDomainMessenger base contract to reduce diff with the existing system.

### Patch Changes

- 63ef1949: Delete hardhat genesis tasks
- Updated dependencies [dbfea116]
  - @eth-optimism/core-utils@0.10.0

## 0.5.4

### Patch Changes

- a095d544: Include latest devnet deployment artifacts
- cdf2163e: Bump oz packages to latest release
- 791f30bc: Migrate deploy config to json from ts
- 193befed: Fix nonce issue for parallel deployments
- 02420db0: Add missing predeploy to Predeploys.sol
- 94a8f287: Moves forge-std and ds-test to devDependencies to avoid breaking npm
- 7d03c5c0: Update the L2 genesis hardhat task to use the ProxyAdmin's deployed address as the admin of each predeploy
- fec22bfe: Fix legibility in the L2CrossDomainMessengerInitializer
- 9272253e: Make a library call internal
- c025f418: Add additional deployments of address manager and proxy admin
- 329d21b6: Use safecall that doesn't copy calldata
- 35eafed0: Deletes the L2 genesis creation hardhat task as its now replaced by go code
- 3cde9205: Update @foundry-rs/hardhat-forge to 0.1.17

## 0.5.3

### Patch Changes

- 056cb982: Fix slither script
- a32e68ac: Update genesis-l2 task to set immutables in the bytecode
- c648d55c: Fix build for smaller package
- d544f804: Use the same initializable across codebase
- ccbfe545: Update @foundry-rs/hardhat-forge@0.1.16
- c97ad241: Fix build on latest foundry
- 45541553: Emit an extra event when withdrawals are initiated to make chainops easier
- 3dd296e8: Fix portal deployment to have L2OutputOracle proxy address
- fe94b864: Add watch task
- 28649d64: Add harhdat forge contract verification support
- 898c7ac5: Update hardhat-forge dep, remove dead deps
- 51a1595b: bedrock-goerli-96f44f79 deployment
- 8ae39154: Update deposit transaction type
- af96563a: Fix typechain exports
- dac4a9f0: Updates the SDK to be compatible with Bedrock (via the "bedrock: true" constructor param). Updates the build pipeline for contracts-bedrock to export a properly formatted dist folder that matches our other packages.
- Updated dependencies [0df744f6]
- Updated dependencies [8ae39154]
- Updated dependencies [dac4a9f0]
  - @eth-optimism/core-utils@0.9.3

## 0.5.2

### Patch Changes

- 1a22e822: Standardizes revert strings globally
- 5e113137: Fixes a bug in the L2 Bedrock genesis script
- 177a9ea8: Cleans linting errors in MerkleTrie.sol
- 7d68f82f: Adds a new event SentMessageExtension1 to the CrossDomainMessenger contract. Includes additional data that's being attached to messages sent after the Bedrock upgrade.
- 90630336: Properly generates and exports ABI and artifact files that can be imported by client libraries
- 8bd7abde: Moves various legacy contracts into the legacy folder
- 7e6eb9b2: The output oracle's getL2Output function now reverts when no output is returned
- f243dacf: Bump to use solidity 0.8.15
- 8d26459b: Remove subversion byte from deposit tx
- fa9823f3: Naming improvements for functions and variables in the L2OutputOracle
- 0bf3b9b4: Update forge-std
- e764cbb7: Shortens library names
- 3a0271f8: Introduces Types.sol
- 5de373ea: Semver contract updated to include a getter for the full version string
- Updated dependencies [0bf3b9b4]
- Updated dependencies [8d26459b]
- Updated dependencies [4477fe9f]
  - @eth-optimism/core-utils@0.9.2

## 0.5.1

### Patch Changes

- e4693481: Clean up BytesUtils
- b7b77d6c: Updates CrossDomainMessenger.baseGas to more accurately reflect gas costs
- 9d435aec: Cleans up natspec in MerkleTrie and SecureMerkleTrie contracts
- 87f745b5: Cleans up various compiler warnings
- 8a3074ab: Minor cleanups to initialization and semver for L1 contracts
- e1501bc0: Clears most contract linting warnings

## 0.5.0

### Minor Changes

- 42a4cc30: Remove Lib* and OVM* prefixes from all contracts

### Patch Changes

- 0cb3929e: Move encoding and hashing into Encoding and Hashing libraries
- 28bd76ae: Cleans up hashing and encoding library natspec and function names
- 4279647f: Port RLPWriter tests
- ce6cb121: Use external version of ExcessivelySafeCall
- 8986f165: Fix solc warnings in ProxyAdmin
- 69ee689f: Remove unnecessary DefaultValues library
- 2e89f634: Fixes a bug that caused L2 timestamps to be computed incorrectly
- 49d33b08: Standardizes comments, errors, and events for contracts in the /universal package
- 821907e2: Bump typechain to 8.1.0
- 91b31168: Clean up comments and errors for legacy contracts
- 3c5726d4: Cleaned up enums, should be CapitalCase enums and UPPER_CASE values
- eb11a5bb: Add comments to RLP libraries
- 092b0901: Update to new L2 tx hash style for deposits
- 4ea33e13: Standardizes initialization logic for L1 contracts
- 297af083: Move contracts written by external parties into a vendor folder
- 71800503: Reduce the number of compiler warnings
- 611d93a1: Remove storage slot buffer in xdomain messengers
- 75089d0a: Cleans up initialization logic everywhere
- b9a90f32: Rename OptimismMintableTokenFactory to OptimismMintableERC20Factory
- 50e20ea1: Fix initialization logic
- 6f74ca9f: Clean up the PredeployAddresses library
- c031ec95: Tests for RLPReader
- 9c8b1f00: Bump forge-std to 62caef29b0f87a2c6aaaf634b2ca4c09b6867c92
- 89d01f2e: Add semver to L2 contracts
- 7d9820b6: Resolve compiler warnings in Proxy.sol
- f9fee446: Move the `DepositTx` type to `core-utils`. This way it can be more easily used across projects
- 5050e0fb: Remove "not implemented" errors in virtual functions
- 78d7c2ec: Update typechain pipeline
- 89d01f2e: Update dev deps
- Updated dependencies [f9fee446]
  - @eth-optimism/core-utils@0.9.1

## 0.4.1

### Patch Changes

- 5c3b4bfa: Enable hardhat style buildinfo
- ef29d8a5: Make the Portal upgradeable
- 5bb6f2c7: Add `OptimismPortal.isOutputFinalized`
- 79f31007: correct l33t sp34k in toCodeAddrr
- 5a12c635: Add deployer docker image
- 8460865f: Optimize buildinfo support, only build through hardhat interface

## 0.4.0

### Minor Changes

- a828da9f: Add separate sequencer role to Oracle

### Patch Changes

- a828da9f: Separate the owner and sequencer roles in the OutputOracle
- 347fd37c: Fix bug in bedrock deploy scripts
- 700dcbb0: Add genesis script
- 931e517b: Fix order of args to L2OO constructor
- 93e2f750: Fix for incorrect constructor args in deploy config
- ddf515cb: Make the output oracle upgradeable.
- Updated dependencies [700dcbb0]
  - @eth-optimism/core-utils@0.9.0

## 0.3.0

### Minor Changes

- 35757456: Replaces L2 timestamps with block numbers as the key in mapping(uint => OutputProposal).

### Patch Changes

- f23bae0b: bedrock: ProxyAdmin rename OpenZeppelin proxy to ERC1967
- fadb1a93: OZ Audit fixes with a Low or informational severity:

  - Hardcode constant values
  - Require that msg.value == \_amount on ETH withdrawals
  - use \_from in place of msg.sender when applicable in internal functions

- f23bae0b: bedrock: Simplify ProxyAdmin static calls
- 650ca6d4: Fixes to medium severity OZ findings

  - Disallow reentrant withdrawals
  - remove donateEth
  - Correct ordering of \_from and \_to arguments on refunds of failed deposits

- 9aa8049c: Have contracts-bedrock properly include contract sources in npm package

## 0.2.0

### Minor Changes

- 04884132: Corrects the ordering of token addresses when a finalizeBridgeERC20 call fails

### Patch Changes

- 0a5ca8bf: Deployment for bedrock contracts on goerli
- 2f3fae0e: Fix hh artifact schema
- a96cbe7c: Fix style for L2 contracts to match L1 contracts
- 29ff7462: Revert es target back to 2017
- 14dd80f3: Add proxy contract
- Updated dependencies [29ff7462]
  - @eth-optimism/core-utils@0.8.7

## 0.1.3

### Patch Changes

- c258acd4: Update comments and style for L1 contracts

## 0.1.2

### Patch Changes

- 07a84aed: Move core-utils to deps instead of devdeps

## 0.1.1

### Patch Changes

- 1aca58c4: Initial release
