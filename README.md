# ErrorHandling
A program to handle errors that might occur in the contract.

##Description
This is a simple solidity contract to handle errors that might cause problem in execution.The checkA function in the Example contract verifies that the state variable a remains greater than 1 using an assert statement. Testing involves setting a to different values and observing if checkA behaves correctly by either passing or triggering an assertion failure when a is 1 or less.


##Getting Started

###Program Execution

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension.Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract Example {
    uint public a;

    // Function to set the value of 'a' with a check using 'require'
    function setA(uint _a) public {
        require(_a > 1, "The given value of 'a' should be greater than one.");
        a = _a;
    }

    // Function to check an invariant using 'assert'
    function checkA() public view {
        assert(a > 1); // This should always be true if setA is used correctly
    }

    // Function to check voting age using 'revert'
    function votingAge(uint _age) public pure  {
        if (_age < 18) {
            revert("You are not eligible for voting as you are less than 18 years old.");
        }
       
    }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile methods.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the contract from the dropdown menu, and then click on the "Deploy" button.




