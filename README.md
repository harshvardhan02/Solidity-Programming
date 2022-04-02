# Solidity Progamming

Solidity is an object-oriented, high-level language for implementing smart contracts. Smart contracts are programs which govern the behaviour of accounts within the Ethereum state.


![Logo](https://miro.medium.com/max/651/1*PZv6C_X671fktg1t7CZvcg.png)


## First Contract

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract {
    string public myString = "solidity";
}
```

## Unsigned Integers

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract {
    uint256 public myUint;   //<---- unsigned integers

    function setMyUint(uint _myUint) public {
        myUint = _myUint;
    }
}
```

## Boolean

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    bool public myName;    //<----- it will be default false always

    function setMyBool(bool _myBool) public {
        myName = _myBool;
    }
}
```

## uint8

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    uint8 public myUint8;    //<----- 0 to 255

    function incrementUint() public {
        myUint8++;
    }

    function decrementUint() public {
        myUint8--;
    }
}
```

## Variable - address

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    address public myAddress;   //<---- Holds 20 bytes value;

    function setAddress(address _newAddress) public {
        myAddress = _newAddress;
    }
}
```

## Member of address(balance)

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    address public myAddress;   //<---- Holds 20 bytes value;

    function setAddress(address _newAddress) public {
        myAddress = _newAddress;
    }

    function getBalaceAddress() public view returns (uint) {
        return myAddress.balance;  // balance is member of address
    }
}
```

| Unit | Wei Value     | Wei                |
| :-------- | :------- | :------------------------- |
| `wei` | `1 wei` | 1 |
| `Kwei(babbage)` | `1e3 wei` | 1,000 |
| `Mwei(lovelace)` | `1e6 wei` | 1,000,000 |
| `Gwei(shannon)` | `1e9 wei` | 1,000,000,000 |
| `Microether(szabo)` | `1e12 wei` | 1,000,000,000,000 |
| `Milliether(finney)` | `1e15 wei` | 1,000,000,000,000,000 |
| `ether` | `1e18 wei` | 1,000,000,000,000,000,000 |


## Variable: string

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    string public myName = "Harshvardhan";

    function setMyFullname(string memory _myFull) public {   //<-- this argument is saved in memory not in storage variable
        myName = _myFull;
    }
}
```


## Address, Accounts, Msg-Object

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{

    uint public balanceRecieved;
    
    function recieveMoney() public payable { // Solidity compiler know that this function going to recieve money
        balanceRecieved += msg.value;  // msg is global object in solidity
    }

    function getBalance() public view returns(uint) {
        return address(this).balance;
    }

    function withDrawMoney() public {
        address payable to = payable(msg.sender);
        to.transfer(this.getBalance()); 
    }

    function withDrawMoneyTo(address payable _to) public {
        _to.transfer(this.getBalance());
    }
}
```

## Start, Stop, Pause and Destroy Contract

```solidity
//SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.5.0 <0.9.0;

contract MyContract{
    address public owner;
    bool paused;

    constructor() {
        owner = msg.sender;
    }

    function sendMoney() public payable {

    }

    function setPaused(bool _paused) public {
        require(msg.sender == owner, "You cannot pause the cotract because you are not the owner");
        paused = _paused;
    }

    function withdrwaAllMoney(address payable _to) public {
        require(msg.sender == owner, "You are not the owner");
        require(!paused, "contract paused");
        _to.transfer(address(this).balance);
    }

    function destroySmartContract(address payable _to) public {
        require(msg.sender == owner, "You are not the owner");
        selfdestruct(_to);
    }
}
```

## Mapping

```solidity
  mapping (KeyType => ValueType) mappingName;
```
| Variable Type | Key Type | Value Type |
| :-------- | :------- | :------------- |
| `int/uint` | ✅ | ✅ |
| `string` | ✅ | ✅ |
| `byte/bytes` | ✅ | ✅ |
| `address` | ✅ | ✅ |
| `struct` | ❌ | ✅ |
| `mapping` | ❌ | ✅ |
| `enum` | ❌ | ✅ |
| `contract` | ❌ | ✅ |
| `fixes sized array` | ✅ | ✅ |
| `dynamic sized array` | ❌ | ✅ |
| `multi dimentional array` | ❌ | ✅ |
| `variable` | ❌ | ❌ |

## Authors

- [Harshvardhan](https://instagram.com/hypersudo)


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://instagram.com/hypersudo)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/harshvardhan-singh-baghel-691b67a1/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/harshvardhan_02)
