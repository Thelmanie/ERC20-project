// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
//main contract

import "./ER20interface.sol"; // we are importing our interface to the main contract using the function import
contract ER20 is IER20{// the interface is inherited with our interfvace name to become our new contract

uint public override totalsupply;//function total supply is a state variable that we used in the inferface and public makes us call or use function outside the contract
mapping (address => uint) public override balanceof; //mapping is used for balanceof indicating that the balance of the person is displayed and we will need an addrress => means the amount will be in numbers which is uint
mapping(address => mapping(address => uint)) public override allowance; //it contains two mapping ie nested mapping, the address of the sender and the address of the receiver which returns uint

string public name = "Tech4dev token"; //name of token created
string public symbol = "TDT"; //symbol of the token created
uint public decimal = 18; //the number of times our token is divisible by

function transfer(address recipient, uint amount)external override returns (bool) {
    balanceof[msg.sender] -=amount; //the deduction from the address of the sender
    balanceof[recipient] = balanceof[recipient]+ amount; // the balance of the perosn receiving the token that is why + is used
    emit Transfer(msg.sender, recipient, amount); // event created shows that the transaction has been carried out
    return true; //transaction was successful
}

function approve(address spender, uint amount) external override returns(bool){
    allowance[msg.sender][spender] =amount; //give permission  to the person that is to receive the money from the sebder
emit approved(msg.sender, spender, amount); //broadcasts approval of the event ie it has been carried out successful
    return true;//declares the transaction was successful
}

function transferfrom(address sender, address recipient, uint amount)external override returns (bool){
     allowance[msg.sender][sender] =amount; //the sender gives an allowance before an approval ie the contract ie the person calling the contract will have had an approved allowance that he can pull out from the address that is approved by the sender 
     balanceof[sender] -=amount; //the amount deducated from the sender address based on the receiver's action
     balanceof[recipient] +=amount; //the amount that receiver calls from the account that has been approved is added to the recipient address
     emit Transfer(msg.sender, recipient, amount); //broadcasts the address of the sender, spender and the amount transacted
     return true; //indicates transaction was successful     
 }

function mint(uint amount) public{//this input indicates the creation of tokens
    balanceof[msg.sender] += amount; //the tokens created is added to the address of the person callinf the function
    totalsupply = totalsupply + amount; //this is used to indicate that the new tokens should be added to the totalsupply and not only to msg.sender
    emit Transfer(address(0), msg.sender, amount); //broadcasts that though we do not know the particular address, the address of the sender and the amount is broadcasted
}

function burn(uint amount) public { //this input indicates the deleting of tokens
    balanceof[msg.sender] -=amount; //the tokens deleted is removed from the  address
    totalsupply -=amount; // the amount is removed from the totalsupply of tokens
    emit Transfer(msg.sender, address(0), amount);//boadcasts the address we are calling from , the unspecified address and the amount deducted
}
}