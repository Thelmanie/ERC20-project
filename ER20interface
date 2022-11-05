// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

 interface IER20{//an I must be added to the contract to be identified as an interface

 function totalsupply() external view returns(uint);// This is the total amount of money created in the person's wallet that he can send and it returns an amount which is uint 

function balanceof(address account) external view returns(uint);//The amount you have in your account which returns uint because your account number is in uint

function transfer(address receipent, uint amount ) external returns(bool);//The sending of money to another account which is set to return bool to know if the transaction was succesful

function allowance(address owner, address sender)external view returns(uint);//The acount number that is allowed to get money from the sender's account

function approve(address spender, uint amount)external returns(bool);//the approved amount the sender can approve the receipent to take from his account

function transferfrom(address sender, address receipent, uint amount)external returns(bool);//whoeve calls the contract to send money to the receipient

event Transfer(address indexed from, address indexed to, uint amount);//the emit that will occur in the event
event approved(address indexed owner, address indexed spender,uint amount);//approped ddress and the amount that was approved























 }