Token Scan interface v1



== note：The current version interface does not support multiple requests，all requests are executed sequentially, temporarily no interface authentication, these features are about to be implemented in the v2 version， at that time, the v1 version calling interface will be closed==



> Interface address

https://lunaray.cc/api/v1/token-scan

> Request method

POST

> Request type

Accept: application/json

> Request body

| Parameter name | Parameter meaning                                            | Is it necessary to write |
| -------------- | ------------------------------------------------------------ | ------------------------ |
| chain_type     | The abbr of the chain where the Token is located，Current support ETH,BSC | Yes                      |
| address        | Token Contract address                                       | Yes                      |

> Response body type

content-type: application/json 

> Response body format

| Parameter name | Parameter meaning                                            | whether it exist or not |
| -------------- | ------------------------------------------------------------ | ----------------------- |
| code           | Whether the call is successful, 0 is success, any other value is failure | Yes                     |
| result         | Specific corresponding data, may be null                     | Yes                     |

> Response body example


```json
{
    "code": 0,
    "result": {
        "address": "0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82",
        "chainType": "BSC",
        "detect": {
            "risk": {
                "high": 0,
                "info": 2,
                "low": 3,
                "medium": 0
            },
            "vul_list": [
                {
                    "descreibe": "An integer variable can only have a certain range of numbers represented, and exceeding the range of values expressed by the variable type will result in an integer overflow vulnerability.",
                    "name": "No safemath library",
                    "risk": 2
                },
                {
                    "descreibe": "There are one or more methods in the contract that only the administrator can operate.",
                    "name": "Onlyowner",
                    "risk": 2
                },
                {
                    "descreibe": "There may be a risk of deflation if the same addresses are not identified at the time of transfer.",
                    "name": "Self transfer",
                    "risk": 2
                },
                {
                    "descreibe": "Failure to add method events may result in users or administrators being unable to determine the details of their actions.",
                    "name": "No events added",
                    "risk": 1
                },
                {
                    "descreibe": "There are unused internal methods in the contract, which may result in additional gas consumption.",
                    "name": "Redundant code",
                    "risk": 1
                },
                {
                    "descreibe": "Dangerous strict equivalence testing",
                    "name": "Dangerous strict equivalence",
                    "risk": 0
                },
                {
                    "descreibe": "The mild if/else-only judgment is a sloppy way of coding in sensitive function scenarios such as transfer, and will lead to false recharge vulnerabilities.",
                    "name": "Fake Recharge",
                    "risk": 0
                },
                {
                    "descreibe": "Unspecified constants that appear in the code can lead to problems such as poor readability of the code.",
                    "name": "Hard coding",
                    "risk": 0
                },
                {
                    "descreibe": "Incorrect modifier",
                    "name": "Incorrect modifier",
                    "risk": 0
                },
                {
                    "descreibe": "Public suicide function calls",
                    "name": "Public suicide function calls",
                    "risk": 0
                },
                {
                    "descreibe": "The attacker builds a contract containing malicious code at an external address in the [Fallback function].",
                    "name": "Re entrancy",
                    "risk": 0
                },
                {
                    "descreibe": "Timestamps may be manipulated by miners",
                    "name": "timestamp",
                    "risk": 0
                },
                {
                    "descreibe": "No judgement is made on the address passed in, if the address is a address(0), the address cannot be modified again",
                    "name": "Unchecked empty address",
                    "risk": 0
                },
                {
                    "descreibe": "Failure to check the method return value when sending tokens using the send or call.value methods in the contract code will lead to unexpected results.",
                    "name": "Unchecked transfer return",
                    "risk": 0
                },
                {
                    "descreibe": "The visibility of contract functions is public by default, so functions that do not specify any visibility can be called externally by the user.",
                    "name": "Unspecified method visibility",
                    "risk": 0
                },
                {
                    "descreibe": "Unused local variables",
                    "name": "Unused local variables",
                    "risk": 0
                },
                {
                    "descreibe": "The return value of an external call is not stored in a local or state variable",
                    "name": "Unused return values",
                    "risk": 0
                },
                {
                    "descreibe": "sha3 is not secure in solidity",
                    "name": "Using sha3",
                    "risk": 0
                },
                {
                    "descreibe": "Objects that have not changed their state, using storage to initialize variables will increase gas consumption, risking overrunning the limit and increasing the risk of memory overwriting.",
                    "name": "Wrong storage usage",
                    "risk": 0
                }
            ]
        },
        "name": "PancakeSwap Token",
        "tokenInfo": [
            {
                "descreibe": "This token contract is open source. The contract code can be viewed for detailed information.",
                "name": "Open source",
                "status": true
            },
            {
                "descreibe": "The owner address is 0x0f9399fc81dac77908a2dde54bb87ee2d17a3373",
                "name": "Owner address",
                "status": false
            },
            {
                "descreibe": "No whitelist function, if the contract exists whitelist function, some addresses may not be able to trade properly.",
                "name": "Whitelist functionality",
                "status": true
            },
            {
                "descreibe": "No blacklist function, if the contract exists blacklist function, some addresses may not be able to trade properly.",
                "name": "Blacklist functionality",
                "status": true
            },
            {
                "descreibe": "The mint function exists, and the mint function may increase the number of tokens in circulation and affect the price of the tokens.",
                "name": "Mint function",
                "status": false
            },
            {
                "descreibe": "No burn feature was found to exist, and contract funding may not be planned for reduction.",
                "name": "Burn function",
                "status": false
            }
        ],
        "top10": {
            "holders": "1,220,259",
            "list": [
                {
                    "address": "0x000000000000000000000000000000000000dead",
                    "addressAbridge": "0x000...0dead",
                    "amount": "487,745,318.8668",
                    "descreibe": "0x000...0dead",
                    "name": "0x000000000000000000000000000000000000dead",
                    "worth": 61.7414
                },
                {
                    "address": "0x45c54210128a065de780c4b0df3d16664f7f859e",
                    "addressAbridge": "0x45c...f859e",
                    "amount": "183,401,616.7404",
                    "descreibe": "0x45c...f859e",
                    "name": "0x45c54210128a065de780c4b0df3d16664f7f859e",
                    "worth": 23.216
                },
                {
                    "address": "0x73feaa1ee314f8c655e354234017be2193c9e24e",
                    "addressAbridge": "0x73f...9e24e",
                    "amount": "21,567,583.908",
                    "descreibe": "0x73f...9e24e",
                    "name": "0x73feaa1ee314f8c655e354234017be2193c9e24e",
                    "worth": 2.7301
                },
                {
                    "address": "0x0ed7e52944161450477ee417de9cd3a859b14fd0",
                    "addressAbridge": "0x0ed...14fd0",
                    "amount": "19,696,163.4179",
                    "descreibe": "0x0ed...14fd0 (DeFi: PancakeSwap. LP(Cake/WBNB))",
                    "name": "DeFi: PancakeSwap. LP(Cake/WBNB)",
                    "worth": 2.4932
                },
                {
                    "address": "0xf977814e90da44bfa03b6295a0616a897441acec",
                    "addressAbridge": "0xf97...1acec",
                    "amount": "13,950,000.0",
                    "descreibe": "0xf97...1acec",
                    "name": "0xf977814e90da44bfa03b6295a0616a897441acec",
                    "worth": 1.7659
                },
                {
                    "address": "0x5a52e96bacdabb82fd05763e25335261b270efcb",
                    "addressAbridge": "0x5a5...0efcb",
                    "amount": "6,000,000.0",
                    "descreibe": "0x5a5...0efcb (Exchange: Binance. User)",
                    "name": "Exchange: Binance. User",
                    "worth": 0.7595
                },
                {
                    "address": "0xa5d57c5dca083a7051797920c78fb2b19564176b",
                    "addressAbridge": "0xa5d...4176b",
                    "amount": "5,806,566.7329",
                    "descreibe": "0xa5d...4176b",
                    "name": "0xa5d57c5dca083a7051797920c78fb2b19564176b",
                    "worth": 0.735
                },
                {
                    "address": "0xa79d37ce9df9443ef4b6dec2e38a8ecd35303adc",
                    "addressAbridge": "0xa79...03adc",
                    "amount": "5,248,211.5352",
                    "descreibe": "0xa79...03adc",
                    "name": "0xa79d37ce9df9443ef4b6dec2e38a8ecd35303adc",
                    "worth": 0.6643
                },
                {
                    "address": "0x2d17ec6cd0af737b2ade40ea527d41ceeedc166f",
                    "addressAbridge": "0x2d1...c166f",
                    "amount": "4,426,305.2626",
                    "descreibe": "0x2d1...c166f",
                    "name": "0x2d17ec6cd0af737b2ade40ea527d41ceeedc166f",
                    "worth": 0.5603
                },
                {
                    "address": "0x0f96e19bdc787e767ba1e8f1add0f62cbdad87c8",
                    "addressAbridge": "0x0f9...d87c8",
                    "amount": "4,084,014.3222",
                    "descreibe": "0x0f9...d87c8",
                    "name": "0x0f96e19bdc787e767ba1e8f1add0f62cbdad87c8",
                    "worth": 0.517
                },
                {
                    "address": "Other",
                    "addressAbridge": "Other",
                    "amount": "38,054,866.965",
                    "descreibe": "Other",
                    "name": "Other",
                    "worth": 4.8172
                }
            ],
            "status": true,
            "supply": "789,980,647.751051201610995531 Cake"
        }
    }
}
```

