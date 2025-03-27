Error: Compiler run failed:
Error: Compiler error (/solidity/libyul/backends/evm/AsmCodeGen.cpp:67):Stack too deep. Try compiling with `--via-ir` (cli) or the equivalent `viaIR: true` (standard JSON) while enabling the optimizer. Otherwise, try removing local variables. When compiling inline assembly: Variable value0 is 2 slot(s) too deep inside the stack. Stack too deep. Try compiling with `--via-ir` (cli) or the equivalent `viaIR: true` (standard JSON) while enabling the optimizer. Otherwise, try removing local variables. ---intermediate interpretation


### On Ethereum

* We learned that account abstraction can allow us to have anything sign a contract.
* On Ethereum, the there are alt-mempools that take the signed data and send it to an `EntryPoint`.
* The `EntryPoint` can have two optional contracts.
  * signature aggregator
  * paymaster
* EntryPoint will then send your transaction to your account contract.
* Then it can be sent to the other dapps on the blockchain.
* We built our own `MinimalAccount.sol`.
* The most important function here we validateUserOp.
  * This took a `PackedUserOperation` struct, `userOpHash`, and `missingAccountFunds`.
* We added an `execute` function to execute commands.
* We also made some great scripts and tests.
* From parameter hold the node address or user sending the txn

### On ZKsync
* Native account abstraction
* Account Abstraction is natively built in.
* There aren't any alt-mempools.
* ZKsync has specific transaction types, ours is 113.
* There are two phases for transactions
  * validation and execution
* A lot is handled by their system contracts.
* The system contracts are governed by a bootloader.
* Also used a struct like on Ethereum, called Transaction.
* Wrote some nice tests.
* Wrote helper functions instead of scripts.
* From parameter hold the smart contract address sending the txn


