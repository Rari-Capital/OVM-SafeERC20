# OVM-SafeERC20
OVM-safe version of OpenZepplin's SafeERC20.sol

### Changes:
- `OVM_SafeERC20.sol`:
  - Import `./OVM_Address.sol` instead of `@openzepplin/contracts/utils/Address.sol`
- `OVM_Address.sol`:
  - Remove all functions that deal with sending ETH (not possible in OVM currently).
  - Change `functionCall` implementation to run `target.call` itself instead of calling `functionCallWithValue` with `0`

### Usage:

```solidity
// SPDX-License-Identifier: AGPL-3.0-only
pragma solidity 0.7.6;

import "ovm-safeerc20/OVM_SafeERC20.sol";

import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

contract L2_NovaRegistry is ReentrancyGuard, OVM_CrossDomainEnabled {
    using OVM_SafeERC20 for IERC20;

    ... your contract here ...
}   
```
