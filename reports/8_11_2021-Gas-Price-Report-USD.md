# Gas Price Report for Deploy on the Ethereum Network:


Table of contents
=================

<!--ts-->
* [Table of contents](#table-of-contents)
* [Smart Contract ](#smart-contract-debugging-methods)
* [Gas Table USD](#gas-table-usd)
* [Gas Table EUR](#gas-table-eur)
<!--te-->


## Smart Contract Debugging Methods

```
ethereum@ubuntu:~/Desktop/frosty-contracts/smart-contracts$ npx buidler test
All contracts have already been compiled, skipping compilation.

  Contract: FrostyAccessControls
    MINTER_ROLE
      ✓ should allow admin to add minters
      ✓ should allow admin to remove minters
      ✓ should revert if not admin
      ✓ should revert even if minter is adding already a minter
      ✓ should revert if does not have the correct role
    SMART_CONTRACT_ROLE
      ✓ should allow admin to add smart contracts
      ✓ should allow admin to remove contracts
      ✓ should revert if not admin when adding
      ✓ should revert even if smart_contract is adding already a smart_contract
      ✓ should revert if not admin when removing
    DEFAULT_ADMIN_ROLE
      ✓ should allow admin to add admin
      ✓ should allow admin to remove admin
      ✓ should revert if already has minter role
      ✓ should revert if does not have the correct role

  Contract: FrostyAuction
    Admin functions
      Auction resulting

        1) "before each" hook for "Successfully results the auction"

  Contract: Core ERC721 tests for FrostyGarmentNFT
    Contract interface
      ERC165
        ERC165's supportsInterface(bytes4)

          2) "before each" hook for "uses less than 30k gas"

  Contract: Core ERC721 tests for FrostyGarmentNFT
    Reverts
      Minting

        3) "before each" hook for "When sender does not have a MINTER or SMART_CONTRACT role"

  Contract: Core ERC721 behaviour tests for FrostyGenesisNFT
    Contract interface
      ERC165
        ERC165's supportsInterface(bytes4)
          ✓ uses less than 30k gas
          ✓ claims support
        supportsInterface(bytes4)
          ✓ has to be implemented
      ERC721
        ERC165's supportsInterface(bytes4)
          ✓ uses less than 30k gas
          ✓ claims support
        balanceOf(address)
          ✓ has to be implemented
        ownerOf(uint256)
          ✓ has to be implemented
        approve(address,uint256)
          ✓ has to be implemented
        getApproved(uint256)
          ✓ has to be implemented
        setApprovalForAll(address,bool)
          ✓ has to be implemented
        isApprovedForAll(address,address)
          ✓ has to be implemented
        transferFrom(address,address,uint256)
          ✓ has to be implemented
        safeTransferFrom(address,address,uint256)
          ✓ has to be implemented
        safeTransferFrom(address,address,uint256,bytes)
          ✓ has to be implemented
      ERC721Enumerable
        ERC165's supportsInterface(bytes4)
          ✓ uses less than 30k gas
          ✓ claims support
        totalSupply()
          ✓ has to be implemented
        tokenOfOwnerByIndex(address,uint256)
          ✓ has to be implemented
        tokenByIndex(uint256)
          ✓ has to be implemented
      ERC721Metadata
        ERC165's supportsInterface(bytes4)
          ✓ uses less than 30k gas
          ✓ claims support
        name()
          ✓ has to be implemented
        symbol()
          ✓ has to be implemented
        tokenURI(uint256)
          ✓ has to be implemented
    metadata
      ✓ has a name
      ✓ has a symbol
      token URI
        ✓ reverts when queried for non existent token id
        ✓ can be queried for an example token
        ✓ can be queried for all tokens
    with minted tokens
      balanceOf
        when the given address owns some tokens
          ✓ returns the amount of tokens owned by the given address
        when the given address does not own any tokens
          ✓ returns 0
        when querying the zero address
          ✓ throws
      ownerOf
        when the given token ID was tracked by this token
          ✓ returns the owner of the given token ID
        when the given token ID was not tracked by this token
          ✓ reverts
      transfers
        via transferFrom
          when called by the owner
            ✓ transfers the ownership of the given token ID to the given address
            ✓ emits a Transfer event
(node:44024) DeprecationWarning: expectEvent.inLogs() is deprecated. Use expectEvent() instead.
            ✓ clears the approval for the token ID
            ✓ emits an Approval event
            ✓ adjusts owners balances
            ✓ adjusts owners tokens by index
          when called by the approved individual
            ✓ transfers the ownership of the given token ID to the given address
            ✓ emits a Transfer event
            ✓ clears the approval for the token ID
            ✓ emits an Approval event
            ✓ adjusts owners balances
            ✓ adjusts owners tokens by index
          when called by the operator
            ✓ transfers the ownership of the given token ID to the given address
            ✓ emits a Transfer event
            ✓ clears the approval for the token ID
            ✓ emits an Approval event
            ✓ adjusts owners balances
            ✓ adjusts owners tokens by index
          when called by the owner without an approved user
            ✓ transfers the ownership of the given token ID to the given address
            ✓ emits a Transfer event
            ✓ clears the approval for the token ID
            ✓ emits an Approval event
            ✓ adjusts owners balances
            ✓ adjusts owners tokens by index
          when sent to the owner
            ✓ keeps ownership of the token
            ✓ clears the approval for the token ID
            ✓ emits only a transfer event
            ✓ keeps the owner balance
            ✓ keeps same tokens by index
          when the address of the previous owner is incorrect
            ✓ reverts
          when the sender is not authorized for the token id
            ✓ reverts
          when the given token ID does not exist
            ✓ reverts
          when the address to transfer the token to is the zero address
            ✓ reverts
        via safeTransferFrom
          with data
            to a user account
              when called by the owner
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the approved individual
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the operator
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the owner without an approved user
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when sent to the owner
                ✓ keeps ownership of the token
                ✓ clears the approval for the token ID
                ✓ emits only a transfer event
                ✓ keeps the owner balance
                ✓ keeps same tokens by index
              when the address of the previous owner is incorrect
                ✓ reverts
              when the sender is not authorized for the token id
                ✓ reverts
              when the given token ID does not exist
                ✓ reverts
              when the address to transfer the token to is the zero address
                ✓ reverts
            to a valid receiver contract
              ✓ calls onERC721Received
              ✓ calls onERC721Received from approved
              when called by the owner
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the approved individual
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the operator
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the owner without an approved user
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when sent to the owner
                ✓ keeps ownership of the token
                ✓ clears the approval for the token ID
                ✓ emits only a transfer event
                ✓ keeps the owner balance
                ✓ keeps same tokens by index
              when the address of the previous owner is incorrect
                ✓ reverts
              when the sender is not authorized for the token id
                ✓ reverts
              when the given token ID does not exist
                ✓ reverts
              when the address to transfer the token to is the zero address
                ✓ reverts
              with an invalid token id
                ✓ reverts
          without data
            to a user account
              when called by the owner
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the approved individual
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the operator
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the owner without an approved user
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when sent to the owner
                ✓ keeps ownership of the token
                ✓ clears the approval for the token ID
                ✓ emits only a transfer event
                ✓ keeps the owner balance
                ✓ keeps same tokens by index
              when the address of the previous owner is incorrect
                ✓ reverts
              when the sender is not authorized for the token id
                ✓ reverts
              when the given token ID does not exist
                ✓ reverts
              when the address to transfer the token to is the zero address
                ✓ reverts
            to a valid receiver contract
              ✓ calls onERC721Received
              ✓ calls onERC721Received from approved
              when called by the owner
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the approved individual
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the operator
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when called by the owner without an approved user
                ✓ transfers the ownership of the given token ID to the given address
                ✓ emits a Transfer event
                ✓ clears the approval for the token ID
                ✓ emits an Approval event
                ✓ adjusts owners balances
                ✓ adjusts owners tokens by index
              when sent to the owner
                ✓ keeps ownership of the token
                ✓ clears the approval for the token ID
                ✓ emits only a transfer event
                ✓ keeps the owner balance
                ✓ keeps same tokens by index
              when the address of the previous owner is incorrect
                ✓ reverts
              when the sender is not authorized for the token id
                ✓ reverts
              when the given token ID does not exist
                ✓ reverts
              when the address to transfer the token to is the zero address
                ✓ reverts
              with an invalid token id
                ✓ reverts
          to a receiver contract returning unexpected value
            ✓ reverts
          to a receiver contract that throws
            ✓ reverts
          to a contract that does not implement the required function
            ✓ reverts
      approve
        when clearing approval
          when there was no prior approval
            ✓ clears approval for the token
            ✓ emits an approval event
          when there was a prior approval
            ✓ clears approval for the token
            ✓ emits an approval event
        when approving a non-zero address
          when there was no prior approval
            ✓ sets the approval for the target address
            ✓ emits an approval event
          when there was a prior approval to the same address
            ✓ sets the approval for the target address
            ✓ emits an approval event
          when there was a prior approval to a different address
            ✓ sets the approval for the target address
            ✓ emits an approval event
        when the address that receives the approval is the owner
          ✓ reverts
        when the sender does not own the given token ID
          ✓ reverts
        when the sender is approved for the given token ID
          ✓ reverts
        when the sender is an operator
          ✓ sets the approval for the target address
          ✓ emits an approval event
        when the given token ID does not exist
          ✓ reverts
      setApprovalForAll
        when the operator willing to approve is not the owner
          when there is no operator approval set by the sender
            ✓ approves the operator
            ✓ emits an approval event
          when the operator was set as not approved
            ✓ approves the operator
            ✓ emits an approval event
            ✓ can unset the operator approval
          when the operator was already approved
            ✓ keeps the approval to the given address
            ✓ emits an approval event
        when the operator is the owner
          ✓ reverts
      getApproved
        when token is not minted
          ✓ reverts
        when token has been minted 
          ✓ should return the zero address
          when account has been approved
            ✓ returns approved account
      totalSupply
        ✓ returns total token supply
      tokenOfOwnerByIndex
        when the given index is lower than the amount of tokens owned by the given address
          ✓ returns the token ID placed at the given index
        when the index is greater than or equal to the total tokens owned by the given address
          ✓ reverts
        when the given address does not own any token
          ✓ reverts
        after transferring all tokens to another user
          ✓ returns correct token IDs for target
          ✓ returns empty collection for original owner
      tokenByIndex
        ✓ returns all tokens
        ✓ reverts if index is greater than supply
    _mint(address, uint256)
      with minted token
        ✓ emits a Transfer event
        ✓ creates the token
        ✓ adjusts owner tokens by index
        ✓ adjusts all tokens list

  Contract: Core NFT tests for FrostyGenesisNFT
    Transfers
      ✓ Reverts when trying to transfer before the end of the genesis
    buy()
      ✓ Successfully buys a genesis NFT
      ✓ cannot buy() more than max total genesis contribution NFTs
      ✓ total contributions are correct for multiple buyers
      ✓ Reverts when trying to contribute more than the maximum permitted
      ✓ Reverts when transfer to multisig fails
      ✓ Reverts when the buyer has already purchased a genesis NFT
      ✓ Reverts when the contribution is lower than the minimum contribution amount
      ✓ Reverts when attempting to buy a genesis outside of the genesis window
    adminBuy()
      ✓ Can successfully buy a genesis as an admin without contribution
      ✓ Reverts when caller is not admin
      ✓ Reverts when beneficiary is address zero
      ✓ Reverts when beneficiary already owns a genesis NFT
    increaseContribution()
      ✓ Successfully increases a previous contribution after buy()
      ✓ Successfully increases the total contribution after a buy and a previous contribution
      ✓ Reverts when trying to contribute more than the maximum permitted
      ✓ Reverts when transfer to multisig fails
      ✓ Reverts when the sender does not own a genesis
      ✓ Reverts when trying to increase a contribution outside of the genesis window
    buyOrIncreaseContribution()
      ✓ Buys a genesis when the user does not own one
      ✓ Increases contribution when user already owns a Genesis
    updateGenesisEnd()
      ✓ Successfully updates end
      ✓ Reverts when not admin
      ✓ Reverts when being changed for a second time
      ✓ Reverts when end time already passed and trying to reopen
    updateAccessControls()
      ✓ Successfully updates access controls as admin
      ✓ Reverts when sender is not admin
      ✓ Reverts when updating to address zero

  Contract: FrostyMaterials 1155 behaviour tests
    like an ERC1155
      balanceOf
        ✓ reverts when queried about the zero address
        when accounts don't own tokens
          ✓ returns zero for given addresses
        when accounts own some tokens

          4) "before each" hook for "returns the amount of tokens owned by the given addresses"
      balanceOfBatch
        ✓ reverts when input arrays don't match up
        ✓ reverts when one of the addresses is the zero address
        when accounts don't own tokens
          ✓ returns zeros for each account
        when accounts own some tokens

          5) "before each" hook for "returns amounts owned by each account in order passed"
      setApprovalForAll
        ✓ sets approval status which can be queried via isApprovedForAll
        ✓ emits an ApprovalForAll log
        ✓ can unset approval for an operator
        ✓ reverts if attempting to approve self as an operator
      safeTransferFrom

        6) "before each" hook for "reverts when transferring more than balance"
      safeBatchTransferFrom

        7) "before each" hook for "reverts when transferring amount more than any of balances"
      Contract interface
        ERC165
          ERC165's supportsInterface(bytes4)
            ✓ uses less than 30k gas
            ✓ claims support
          supportsInterface(bytes4)
            ✓ has to be implemented
        ERC1155
          ERC165's supportsInterface(bytes4)
            ✓ uses less than 30k gas
            ✓ claims support
          balanceOf(address,uint256)
            ✓ has to be implemented
          balanceOfBatch(address[],uint256[])
            ✓ has to be implemented
          setApprovalForAll(address,bool)
            ✓ has to be implemented
          isApprovedForAll(address,address)
            ✓ has to be implemented
          safeTransferFrom(address,address,uint256,uint256,bytes)
            ✓ has to be implemented
          safeBatchTransferFrom(address,address,uint256[],uint256[],bytes)
            ✓ has to be implemented
    internal functions
      _mint

        8) reverts with a zero destination address
        with minted tokens

          9) "before each" hook for "emits a TransferSingle event"
      _mintBatch

        10) "before each" hook for "reverts with a zero destination address"
    ERC1155MetadataURI

      11) sets the first token URI correctly

      12) sets the first and second token URI correctly

  Contract: FrostyMaterials 1155 behaviour tests
    createStrand()

      13) Reverts when sender is not minter

      14) Reverts when zero supply specified

      15) Reverts when empty uri specified
    batchCreateStrands()

      16) Reverts when sender is not minter

      17) Reverts when array lengths differ

      18) Reverts when arrays are empty

      19) Reverts when any elem in the _initialSupplies is zero

      20) Reverts when any elem in the _uris is empty
    mintStrand()

      21) "before each" hook for "Can successfully mint"
    batchMintStrands()

      22) Reverts when sender is not a minter

      23) Reverts when any strand does not exist

      24) Reverts when any amount is zero

      25) Reverts when array lengths are inconsistent

      26) Reverts when arrays are empty
    updateAccessControls()
      ✓ Successfully updates access controls as admin
      ✓ Reverts when sender does not have admin role
      ✓ Reverts when setting access controls to ZERO address

```

## Gas Table USD


```

·--------------------------------------------------------------------|---------------------------|-------------|----------------------------·
|                        Solc version: 0.6.12                        ·  Optimizer enabled: true  ·  Runs: 200  ·  Block limit: 9500000 gas  │
·····································································|···························|·············|·····························
|  Methods                                                           ·               50 gwei/gas               ·      3236.12 usd/eth       │
·······································|·····························|·············|·············|·············|··············|··············
|  Contract                            ·  Method                     ·  Min        ·  Max        ·  Avg        ·  # calls     ·  usd (avg)  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC1155                             ·  setApprovalForAll          ·      25715  ·      44927  ·      44314  ·         188  ·       7.17  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC721WithSameTokenURIForAllTokens  ·  safeTransferFrom           ·      46557  ·      97718  ·      78511  ·          62  ·      12.70  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC721WithSameTokenURIForAllTokens  ·  safeTransferFrom           ·      47213  ·      99094  ·      79491  ·          62  ·      12.86  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addAdminRole               ·          -  ·          -  ·      75296  ·           4  ·      12.18  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addMinterRole              ·      75351  ·      90351  ·      85110  ·          83  ·      13.77  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addSmartContractRole       ·      90273  ·      90285  ·      90283  ·           6  ·      14.61  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeAdminRole            ·          -  ·          -  ·      24421  ·           2  ·       3.95  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeMinterRole           ·          -  ·          -  ·      24416  ·           2  ·       3.95  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeSmartContractRole    ·          -  ·          -  ·      24394  ·           1  ·       3.95  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAuction                       ·  updateAccessControls       ·          -  ·          -  ·      32678  ·           1  ·       5.29  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  adminBuy                   ·          -  ·          -  ·     200464  ·           2  ·      32.44  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  buy                        ·     200369  ·     230369  ·     229983  ·         233  ·      37.21  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  buyOrIncreaseContribution  ·      49392  ·     231327  ·     140360  ·           2  ·      22.71  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  increaseContribution       ·          -  ·          -  ·      48379  ·           3  ·       7.83  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  updateGenesisEnd           ·          -  ·          -  ·      55996  ·           2  ·       9.06  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyMaterials                     ·  setApprovalForAll          ·      15113  ·      45125  ·      39123  ·           5  ·       6.33  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyMaterials                     ·  updateAccessControls       ·          -  ·          -  ·      31705  ·           1  ·       5.13  │
·······································|·····························|·············|·············|·············|··············|··············
|  WethToken                           ·  approve                    ·      20404  ·      51684  ·      45817  ·         224  ·       7.41  │
·······································|·····························|·············|·············|·············|··············|··············
|  WethToken                           ·  transferFrom               ·      45561  ·      88764  ·      74554  ·          31  ·      12.06  │
·······································|·····························|·············|·············|·············|··············|··············
|  Deployments                                                       ·                                         ·  % of limit  ·             │
·····································································|·············|·············|·············|··············|··············
|  FrostyAccessControls                                              ·          -  ·          -  ·     782814  ·       8.2 %  ·     126.66  │
·····································································|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                                                  ·          -  ·          -  ·    2757860  ·        29 %  ·     446.24  │
·····································································|·············|·············|·············|··············|··············
|  FrostyMaterials                                                   ·    2758304  ·    2758316  ·    2758315  ·        29 %  ·     446.31  │
·--------------------------------------------------------------------|-------------|-------------|-------------|--------------|-------------·

  312 passing (2m)
  26 failing

```




## Gas Table EUR


```
·--------------------------------------------------------------------|---------------------------|-------------|----------------------------·
|                        Solc version: 0.6.12                        ·  Optimizer enabled: true  ·  Runs: 200  ·  Block limit: 9500000 gas  │
·····································································|···························|·············|·····························
|  Methods                                                           ·               50 gwei/gas               ·      2760.06 eur/eth       │
·······································|·····························|·············|·············|·············|··············|··············
|  Contract                            ·  Method                     ·  Min        ·  Max        ·  Avg        ·  # calls     ·  eur (avg)  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC1155                             ·  setApprovalForAll          ·      25715  ·      44927  ·      44314  ·         188  ·       6.12  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC721WithSameTokenURIForAllTokens  ·  safeTransferFrom           ·      46557  ·      97718  ·      78511  ·          62  ·      10.83  │
·······································|·····························|·············|·············|·············|··············|··············
|  ERC721WithSameTokenURIForAllTokens  ·  safeTransferFrom           ·      47213  ·      99094  ·      79491  ·          62  ·      10.97  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addAdminRole               ·          -  ·          -  ·      75296  ·           4  ·      10.39  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addMinterRole              ·      75351  ·      90351  ·      85110  ·          83  ·      11.75  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  addSmartContractRole       ·      90273  ·      90285  ·      90283  ·           6  ·      12.46  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeAdminRole            ·          -  ·          -  ·      24421  ·           2  ·       3.37  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeMinterRole           ·          -  ·          -  ·      24416  ·           2  ·       3.37  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAccessControls                ·  removeSmartContractRole    ·          -  ·          -  ·      24394  ·           1  ·       3.37  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyAuction                       ·  updateAccessControls       ·          -  ·          -  ·      32678  ·           1  ·       4.51  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  adminBuy                   ·          -  ·          -  ·     200464  ·           2  ·      27.66  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  buy                        ·     200369  ·     230369  ·     229983  ·         233  ·      31.74  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  buyOrIncreaseContribution  ·      49392  ·     231327  ·     140360  ·           2  ·      19.37  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  increaseContribution       ·          -  ·          -  ·      48379  ·           3  ·       6.68  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                    ·  updateGenesisEnd           ·          -  ·          -  ·      55996  ·           2  ·       7.73  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyMaterials                     ·  setApprovalForAll          ·      15113  ·      45125  ·      39123  ·           5  ·       5.40  │
·······································|·····························|·············|·············|·············|··············|··············
|  FrostyMaterials                     ·  updateAccessControls       ·          -  ·          -  ·      31705  ·           1  ·       4.38  │
·······································|·····························|·············|·············|·············|··············|··············
|  WethToken                           ·  approve                    ·      20404  ·      51684  ·      45817  ·         224  ·       6.32  │
·······································|·····························|·············|·············|·············|··············|··············
|  WethToken                           ·  transferFrom               ·      45561  ·      88764  ·      74554  ·          31  ·      10.29  │
·······································|·····························|·············|·············|·············|··············|··············
|  Deployments                                                       ·                                         ·  % of limit  ·             │
·····································································|·············|·············|·············|··············|··············
|  FrostyAccessControls                                              ·          -  ·          -  ·     782814  ·       8.2 %  ·     108.03  │
·····································································|·············|·············|·············|··············|··············
|  FrostyGenesisNFT                                                  ·          -  ·          -  ·    2757860  ·        29 %  ·     380.59  │
·····································································|·············|·············|·············|··············|··············
|  FrostyMaterials                                                   ·    2758304  ·    2758316  ·    2758315  ·        29 %  ·     380.66  │
·--------------------------------------------------------------------|-------------|-------------|-------------|--------------|-------------·

```
