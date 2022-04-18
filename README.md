# rest-api-python-transaction
import json
print('loading function')
def lambda_handler(event) :
    #1. parse out query string params
    transactionId = event['querystringparameters']['transactionId']
    transactiontype = event['querystringparameters']['type']
    transactionamount =event['querystringpaameters']['amount']
    print('transactionId=' + transactionId)
    print('transactiontype=' + transactiontype)
    print('transactionamount=' + transactionamount)
    #construct the body of response object
    transactionresponse = {}
    transactionresponse['transactionId'] = transactionId
    transactionresponse['type'] = transactiontype
    transactionresponse['amount'] =transactionamount
    transactionresponse['message'] = 'hello from lambda'
    #construct http response ondject
    responseobject = {}
    responseobject['statuscode'] = 200
    responseobject['headers']
    responseobject['headers']['content-type'] = '"application/json'
    responseobject['body'] =json.dumps(transactionResponse)
    #4 return the response object
    return responseobject
