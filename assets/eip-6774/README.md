# Reference implementations of ERC-6774

## Contract

**ERC-6774 implementations:**

- [IERC6774.sol](./contracts/IERC6774.sol): interface of `ERC6774`
- [ERC6774.sol](./contracts/ERC6774.sol): a simple and minimal implementation for one-to-one barter type
- [ERC6774MultiBarter.sol](./contracts/extensions/ERC6774MultiBarter.sol): an extensions of `ERC6774.sol` for barter several tokens belonging to the same contract

**Mocks contracts:**

- [PermissionlessERC6774.sol](./contracts/mocks/PermissionlessERC6774.sol): an exemple of implementation of `ERC6774`
- [PermissionlessERC6774MultiBarter.sol](./contracts/mocks/PermissionlessERC6774MultiBarter.sol): an exemple of implementation of `ERC6774MultiBarter`

_These contracts are used in `test`_

## Tests

Tests are written using Foundry, here is the list of tests:

- Barter on same contract
- Cannot use an expired signature
- Enable barter on same contract is required
- Nonce prevent signature reuse
- One-to-one barter
- Revert if barters not allowed
- Multi barter
- Cannot barter empty array (multi barter)

## Building instruction

You can build a Foundry repo by running the following scripts:

```bash
forge init --force
forge install OpenZeppelin/openzeppelin-contracts
forge remappings > remappings.txt
rm -r src
rm test/Counter.t.sol
forge build
```

Run tests:

```bash
forge test -vvvv
```
