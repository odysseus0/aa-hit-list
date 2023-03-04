# Road to ERC-4337 Mass Adoption

This is a collaborative effort to identify and overcome obstacles to the adoption of Account Abstraction (ERC-4337) on Ethereum.

ERC-4337 is a proposal that has the potential to improve the user experience of Ethereum. However, there are still several hurdles to overcome before ERC-4337 can be widely adopted.

This repository serves as a place to document these challenges and the progress made in overcoming them. We invite developers, researchers, and anyone interested in improving the Ethereum ecosystem to join us in this effort.

Our goal is to collectively solve the biggest challenges to ERC-4337 adoption and make Ethereum more user-friendly and accessible to everyone. Join us and let's work together to make it happen.

## How to get involved

Contributing is easy – simply make pull request to this repository and start collaborating! We encourage you to contribute your ideas, feedback, and expertise to help us achieve our shared goal.

Here are some ways you can get involved:

* Identify and document obstacles to ERC-4337 adoption
* Contribute code and documentation to help overcome these obstacles
* Provide feedback and suggestions to improve our collective efforts
* Spread the word about ERC-4337 and our collaborative efforts to promote it

## Work that need your support

https://github.com/ethers-io/ethers.js/pull/3803

This contribution by [Ivo Georgiev](https://github.com/Ivshti) adds a universal signature verification function to Ethers for verifying contract wallet signatures. Adoption of this function will address a majority of issues related to improper off-chain signature verification not following [ERC-1271](https://eips.ethereum.org/EIPS/eip-1271).

## How bad is it now

* [EIP-1271 incompatibilities](https://eip1271.io): An incomplete list of projects that do not follow ERC-1271 and would likely lead to Account Abstraction incompatibility.

### dApps which don't support EIP1271 (incomplete list)
**Recomemndation to their developers:** Implement EIP-1271 signature validation via [signature-validator](https://github.com/AmbireTech/signature-validator/).
* LooksRare
* Loopring
* dYdX
* ZKSpace
* Pangolin
* EPNS
* Unstoppable Domains
* Curve

### dApps thatblock contract accounts
Some dApps block contract accounts because of anti-pattern security measures such as "protection against bots" or "protection against MEV". Blocking contract calls does not protect from either of those things, but it does break support for contract accounts.

**Recommendation to their developers:** do not block contract calls

* Avalanche Bridge

### Other edge cases
Most exchanges do not detect deposit of native tokens from contract accounts. This is because they detect those deposits by looking at top-level transactions with `value` rather than internal calls.

Interestingly, Binance does not suffer from this issue on Ethereum, but it does for other EVM chains. The Binance team confirmed privately that they have a workaround on Ethereum.

This issue does not result in loss of funds but it results in temporarily stuck funds.


## License

This repository is licensed under the MIT License. By contributing to this repository, you agree to license your contributions under the same license.
