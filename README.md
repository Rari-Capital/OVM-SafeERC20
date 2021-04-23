# OVM-SafeERC20
OVM-safe version of OpenZepplin's SafeERC20.sol

### Changes:
- `OVM_SafeERC20.sol`:
  - Import `./OVM_Address.sol` instead of `@openzepplin/contracts/utils/Address.sol`
- `OVM_Address.sol`:
  - Remove all functions that deal with sending ETH (not possible in OVM currently).
  - Change `functionCall` implementation to run `target.call` itself instead of calling `functionCallWithValue` with `0`

