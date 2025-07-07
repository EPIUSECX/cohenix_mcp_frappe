# Python Module Analysis: `/workspace/cohenix-bench/apps/payments/payments/payment_gateways/doctype/mpesa_settings/mpesa_connector.py`

## Classes

### `MpesaConnector`


**Docstring:**
```

```

**Methods:**
| Name | Arguments | Decorators | Docstring |
|---|---|---|---|
| `__init__` | `self, env, app_key, app_secret, sandbox_url, live_url` | `` | Setup configuration for Mpesa connector and generate new access token. |
| `authenticate` | `self` | `` | This method is used to fetch the access token required by Mpesa.

Returns:
        access_token (str): This token is to be used with the Bearer header for further API calls to Mpesa. |
| `get_balance` | `self, initiator, security_credential, party_a, identifier_type, remarks, queue_timeout_url, result_url` | `` | This method uses Mpesa's Account Balance API to to enquire the balance on a M-Pesa BuyGoods (Till Number).

Args:
        initiator (str): Username used to authenticate the transaction.
        security_credential (str): Generate from developer portal.
        command_id (str): AccountBalance.
        party_a (int): Till number being queried.
        identifier_type (int): Type of organization receiving the transaction. (MSISDN/Till Number/Organization short code)
        remarks (str): Comments that are sent along with the transaction(maximum 100 characters).
        queue_timeout_url (str): The url that handles information of timed out transactions.
        result_url (str): The url that receives results from M-Pesa api call.

Returns:
        OriginatorConverstionID (str): The unique request ID for tracking a transaction.
        ConversationID (str): The unique request ID returned by mpesa for each request made
        ResponseDescription (str): Response Description message |
| `stk_push` | `self, business_shortcode, passcode, amount, callback_url, reference_code, phone_number, description` | `` | This method uses Mpesa's Express API to initiate online payment on behalf of a customer.

Args:
        business_shortcode (int): The short code of the organization.
        passcode (str): Get from developer portal
        amount (int): The amount being transacted
        callback_url (str): A CallBack URL is a valid secure URL that is used to receive notifications from M-Pesa API.
        reference_code(str): Account Reference: This is an Alpha-Numeric parameter that is defined by your system as an Identifier of the transaction for CustomerPayBillOnline transaction type.
        phone_number(int): The Mobile Number to receive the STK Pin Prompt.
        description(str): This is any additional information/comment that can be sent along with the request from your system. MAX 13 characters

Success Response:
        CustomerMessage(str): Messages that customers can understand.
        CheckoutRequestID(str): This is a global unique identifier of the processed checkout transaction request.
        ResponseDescription(str): Describes Success or failure
        MerchantRequestID(str): This is a global unique Identifier for any submitted payment request.
        ResponseCode(int): 0 means success all others are error codes. e.g.404.001.03

Error Reponse:
        requestId(str): This is a unique requestID for the payment request
        errorCode(str): This is a predefined code that indicates the reason for request failure.
        errorMessage(str): This is a predefined code that indicates the reason for request failure. |





## Functions

No top-level functions found in this file.
