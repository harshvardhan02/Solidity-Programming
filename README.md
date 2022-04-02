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

## Authors

- [Harshvardhan](https://instagram.com/hypersudo)


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://instagram.com/hypersudo)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/harshvardhan-singh-baghel-691b67a1/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/harshvardhan_02)
