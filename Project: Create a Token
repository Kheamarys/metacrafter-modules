// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    
Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
Your contract will have a mapping of addresses to balances (address => uint)
You will have a mint function that takes two parameters: an address and a value. 
The function then increases the total supply by that number and increases the balance 
of the “sender” address by that amount
Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
and from the balance of the “sender”.
Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
to the amount that is supposed to be burned.
*/

contract MyToken {
    // public variables here
    string public name;  
    string public symbol; 
    uint256 public totalSupply; 
    // mapping variable here
    mapping(address => uint256) public balances;

    constructor(string memory _name, string memory _symbol, uint256 _initialSupply) {
        name = _name;
        symbol = _symbol;
        totalSupply = _initialSupply;
        balances[msg.sender] = _initialSupply;
    }

    // mint function
    function mint(address _recipient, uint256 _value) public {
        totalSupply += _value;
        balances[_recipient] += _value;
    }
    // burn function
    function burn(address _owner, uint256 _value) public {
        require(balances[_owner] >= _value, "Insufficient balance");
        require(totalSupply >= _value, "Insufficient total supply");
        
        totalSupply -= _value;
        balances[_owner] -= _value;
    }
}
