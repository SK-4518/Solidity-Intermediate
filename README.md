# Solidity-Intermediate Project

__**Aim of the program**__

Write a smart contract that implements the require(), assert() and revert() statements

**Basic concepts required in the program:**

1. Error- It is an exceptional condition that halts the normal execution of the program.
2. Error Handling- In solidity, the procedure of handling errors using various statements is known as error handling.

**   There are three methods that constitute the error-handling process in Solidity:
1. **Require**- It  is used in order to check particular condition before the execution of the function. It requires two parameters- a condition and a string message. If the condition returns to true then the execution of the program is passed to the next statement else if it returns to false then the function execution is terminated and the message passed as the second parameter of the require statement is displayed.
 
 Syntax-  require(condition to be validated, message to be displayed if the condition fails);
 
2. **Assert**- It is used to check the condition. If the condition fails then the program execution is terminated with an error message. It takes only one parameter i.e. the condition. If the condition returns to true then the execution jumps to the next statement.

 Syntax- assert(condition to be checked);
 
3. **Revert**- It is used to display the error and revert the current call. It causes the EVM to revert all the changes made to the state, and things return to the initial state or the state before the function call was made. Since the function execution stops after the revert() statement, the remaining gas is also returned back to the user. If you don't use the revert() statement and some error occurs, then the entire gas is lost. 

Syntax- revert();


**Program**-This program is run using the Remix online compiler- https://remix.ethereum.org

    //SPDX-License-Identifier: MIT

    pragma solidity 0.8.7;

    contract ErrorHandling{

    uint public num;
    
    function testRequire(uint num1) public pure{
    
        require(num1<10,"Number is greater than 10, please enter number smaller than 10");
        
    }
    
    function testAssert(uint num2) public pure {
    
        assert(num2<10);
        
    }
    
    function testRevert(uint num3) public{
    
        if(num3>10){
        
          revert("Number is greater than 10");
          
        }
        
        else{
        
            num=num3;
            
        }
        
        }
      }


**Code functionality:**

1. Open the Remix IDE.
   
2. Write the above code.
   
3. Compile the code using the solidity compiler at the left menu tab.
   
4. Deploy the code using deploy and run transactions at the left menu tab.
   
5. Put different values of  unsigned integer values and notice the working of the require, assert, and revert statements.
   
