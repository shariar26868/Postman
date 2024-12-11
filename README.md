![image](https://github.com/user-attachments/assets/50bc3df2-5c7d-4f55-b907-5074738ffccd)

# dMoney API Testing

This repository contains automated test cases for the **dMoney** REST API, including both positive and negative test cases. The test cases cover key functionality such as account creation, deposits, withdrawals, and transactions. The tests are implemented using **Postman** and run with **Newman** for reporting.

## Table of Contents

1. [Overview](#overview)
2. [Test Cases](#test-cases)
3. [Postman Collection](#postman-collection)
4. [Newman Report](#newman-report)
5. [API Documentation](#api-documentation)
6. [Bug Report](#bug-report)
7. [License](#license)

---

## Overview

The objective of this project is to automate the testing of key operations within the **dMoney** API. The tests cover the following scenarios:

1. **Admin Account Creation**: Admin creates an Agent, 2 Customers, and a Merchant.
2. **Money Deposits**: Deposits from the SYSTEM account to the Agent, and from the Agent to the Customer.
3. **Transactions**: Transfers of money between customers, as well as withdrawals and payments to merchants.
4. **Balance Checks**: Verifying balances and transaction statements for customers, agents, and merchants.

This repository also includes **negative test cases** to verify that the API handles edge cases and invalid input appropriately.

---

## Test Cases

### Positive Test Cases

1. **Admin creates an Agent**
   - **Steps**: Log in as admin, create an agent.
   - **Expected Result**: Agent is created successfully.

2. **Admin creates 2 random Customers**
   - **Steps**: Log in as admin, create two random customers.
   - **Expected Result**: Customers are created successfully.

3. **Admin creates a Merchant**
   - **Steps**: Log in as admin, create a merchant.
   - **Expected Result**: Merchant is created successfully.

4. **Deposit money from SYSTEM account to Agent**
   - **Steps**: Log in as SYSTEM, deposit money to Agent.
   - **Expected Result**: Money is successfully deposited into Agent’s account.

5. **Agent deposits money to a Customer**
   - **Steps**: Log in as Agent, deposit money to Customer.
   - **Expected Result**: Money is successfully deposited into Customer’s account.

6. **Check Agent's balance**
   - **Steps**: Log in as Agent, check balance.
   - **Expected Result**: Agent’s balance is updated correctly.

7. **Send money from one Customer to another**
   - **Steps**: Log in as Customer1, send money to Customer2.
   - **Expected Result**: Transfer is successful, and Customer2’s balance is updated.

8. **Withdraw money from a Customer to an Agent**
   - **Steps**: Log in as Customer, withdraw money to Agent.
   - **Expected Result**: Withdrawal is successful, and both accounts’ balances are updated.

9. **Check Customer's balance and transaction statement by trnxId**
   - **Steps**: Log in as Customer, check balance and transaction history.
   - **Expected Result**: Customer’s balance and transaction history are correct.

10. **Make payment from Customer to Merchant**
    - **Steps**: Log in as Customer2, make a payment to Merchant.
    - **Expected Result**: Payment is successful, Merchant’s balance is updated.

### Negative Test Cases

1. **Invalid authentication for Agent creation**
   - **Steps**: Use incorrect admin credentials to create an agent.
   - **Expected Result**: Error message about invalid credentials.

2. **Insufficient balance for transfer between Customers**
   - **Steps**: Attempt to send more money than available in the balance.
   - **Expected Result**: Error message indicating insufficient funds.

3. **Invalid transaction amount for withdrawal**
   - **Steps**: Attempt a withdrawal outside the allowed range.
   - **Expected Result**: Error message indicating invalid withdrawal amount.

4. **Invalid Merchant Payment**
   - **Steps**: Attempt a payment to a non-existing merchant.
   - **Expected Result**: Error message indicating invalid merchant.

---

## Postman Collection

The **Postman Collection** contains all the above test cases, both positive and negative. Follow these steps to use the collection:

1. **Import the Collection**:
   - Open Postman and click the `Import` button.
   - Select `Import File` and choose the `dMoney_Collection.json` file from this repository.
   
2. **Setup Environment**:
   - Import the environment file (e.g., `dMoney_Environment.json`) for managing dynamic variables such as `base_url`, `API_KEY`, etc.

3. **Run Tests**:
   - Click on the **Runner** button in Postman.
   - Select the **dMoney API Collection** and your **Environment**.
   - Click **Run** to execute the tests.

---

## Newman Report

Newman is used to run the Postman tests from the command line and generate a detailed report. To generate a Newman report:

1. Install **Newman**:
   ```bash
   npm install -g newman


Test Case for this project: [Test Case](https://drive.google.com/drive/folders/1Bl4Hxd0CzoDW_mLoFWJFMN-Ys9OZF6d1?usp=sharing)

Documentation for this project: [Documentation](https://l.facebook.com/l.php?u=https%3A%2F%2Fdocumenter.getpostman.com%2Fview%2F35578312%2F2sAXjRX9xo%3Ffbclid%3DIwZXh0bgNhZW0CMTAAAR1tMtfyQUy5FgChyh4CKSTyU99-6HmI7Sss4XpI_hOWgvrmiO8k07dT7EU_aem_z8RPVdnSU07vD-Lv0PSdvg&h=AT0XHSCp94-pIzNMxMhgMnEB_ILLbFdLGFC_KnWOW4V3FTgw5GOxLSqa2Ke6qabMajwGavvxFLAgvzR4yUEk1AYP50CeaSzfqBt-Qm4k9bXckia8MHd8McobWw61zQ_pvmdp9Q)
