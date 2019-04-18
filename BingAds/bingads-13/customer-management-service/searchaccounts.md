---
title: SearchAccounts Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Searches for accounts that match a specified criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
> [!IMPORTANT]
> The Bing Ads API Version 13 preview documentation is subject to change. To view version 12 content, use the version selector near the table of contents at the top and left side of the page.

# SearchAccounts Service Operation - Customer Management
Searches for accounts that match a specified criteria.

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account.<br/><br/>This request element is optional. You can specify up to one *OrderBy* element in the array. Additional elements are not supported and will be ignored by the service.<br/><br/>For this service operation, the following values are supported in the *Field* element of a *OrderBy* object.<br/><br/>*Id* - The order is determined by the *Id*element of the returned [AdvertiserAccount](advertiseraccount.md).<br/><br/>*Name* - The order is determined by the *Name* element of the returned [AdvertiserAccount](advertiseraccount.md).<br/><br/>*Number* - The order is determined by the *Number* element of the returned [AdvertiserAccount](advertiseraccount.md).|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the request conditions. This operation's response will include accounts that match all of the specified predicates.<br/><br/>With the exception of AccountLifeCycleStatus, you must specify exactly one predicate. When using the AccountLifeCycleStatus predicate field you must specify one additional predicate, for example with the *Field* set to UserId.<br/><br/>For a list of supported *Field* and *Operator* elements of a [Predicate](predicate.md) object for this service operation, see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchAccountsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounts"></a>Accounts|A list of accounts that meet the specified criteria.|[AdvertiserAccount](advertiseraccount.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">SearchAccounts</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <Predicates xmlns:e160="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e160:Predicate>
          <e160:Field i:nil="false">ValueHere</e160:Field>
          <e160:Operator>ValueHere</e160:Operator>
          <e160:Value i:nil="false">ValueHere</e160:Value>
        </e160:Predicate>
      </Predicates>
      <Ordering xmlns:e161="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e161:OrderBy>
          <e161:Field>ValueHere</e161:Field>
          <e161:Order>ValueHere</e161:Order>
        </e161:OrderBy>
      </Ordering>
      <PageInfo xmlns:e162="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e162:Index>ValueHere</e162:Index>
        <e162:Size>ValueHere</e162:Size>
      </PageInfo>
    </SearchAccountsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SearchAccountsResponse xmlns="https://bingads.microsoft.com/Customer/v13">
      <Accounts xmlns:e163="https://bingads.microsoft.com/Customer/v13/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e163:AdvertiserAccount>
          <e163:BillToCustomerId d4p1:nil="false">ValueHere</e163:BillToCustomerId>
          <e163:CurrencyCode d4p1:nil="false">ValueHere</e163:CurrencyCode>
          <e163:AccountFinancialStatus d4p1:nil="false">ValueHere</e163:AccountFinancialStatus>
          <e163:Id d4p1:nil="false">ValueHere</e163:Id>
          <e163:Language d4p1:nil="false">ValueHere</e163:Language>
          <e163:LastModifiedByUserId d4p1:nil="false">ValueHere</e163:LastModifiedByUserId>
          <e163:LastModifiedTime d4p1:nil="false">ValueHere</e163:LastModifiedTime>
          <e163:Name d4p1:nil="false">ValueHere</e163:Name>
          <e163:Number d4p1:nil="false">ValueHere</e163:Number>
          <e163:ParentCustomerId>ValueHere</e163:ParentCustomerId>
          <e163:PaymentMethodId d4p1:nil="false">ValueHere</e163:PaymentMethodId>
          <e163:PaymentMethodType d4p1:nil="false">ValueHere</e163:PaymentMethodType>
          <e163:PrimaryUserId d4p1:nil="false">ValueHere</e163:PrimaryUserId>
          <e163:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e163:AccountLifeCycleStatus>
          <e163:TimeStamp d4p1:nil="false">ValueHere</e163:TimeStamp>
          <e163:TimeZone d4p1:nil="false">ValueHere</e163:TimeZone>
          <e163:PauseReason d4p1:nil="false">ValueHere</e163:PauseReason>
          <e163:ForwardCompatibilityMap xmlns:e164="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e164:KeyValuePairOfstringstring>
              <e164:key d4p1:nil="false">ValueHere</e164:key>
              <e164:value d4p1:nil="false">ValueHere</e164:value>
            </e164:KeyValuePairOfstringstring>
          </e163:ForwardCompatibilityMap>
          <e163:LinkedAgencies d4p1:nil="false">
            <e163:CustomerInfo>
              <e163:Id d4p1:nil="false">ValueHere</e163:Id>
              <e163:Name d4p1:nil="false">ValueHere</e163:Name>
            </e163:CustomerInfo>
          </e163:LinkedAgencies>
          <e163:SalesHouseCustomerId d4p1:nil="false">ValueHere</e163:SalesHouseCustomerId>
          <e163:TaxInformation xmlns:e165="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e165:KeyValuePairOfstringstring>
              <e165:key d4p1:nil="false">ValueHere</e165:key>
              <e165:value d4p1:nil="false">ValueHere</e165:value>
            </e165:KeyValuePairOfstringstring>
          </e163:TaxInformation>
          <e163:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e163:BackUpPaymentInstrumentId>
          <e163:BillingThresholdAmount d4p1:nil="false">ValueHere</e163:BillingThresholdAmount>
          <e163:BusinessAddress d4p1:nil="false">
            <e163:City d4p1:nil="false">ValueHere</e163:City>
            <e163:CountryCode d4p1:nil="false">ValueHere</e163:CountryCode>
            <e163:Id d4p1:nil="false">ValueHere</e163:Id>
            <e163:Line1 d4p1:nil="false">ValueHere</e163:Line1>
            <e163:Line2 d4p1:nil="false">ValueHere</e163:Line2>
            <e163:Line3 d4p1:nil="false">ValueHere</e163:Line3>
            <e163:Line4 d4p1:nil="false">ValueHere</e163:Line4>
            <e163:PostalCode d4p1:nil="false">ValueHere</e163:PostalCode>
            <e163:StateOrProvince d4p1:nil="false">ValueHere</e163:StateOrProvince>
            <e163:TimeStamp d4p1:nil="false">ValueHere</e163:TimeStamp>
            <e163:BusinessName d4p1:nil="false">ValueHere</e163:BusinessName>
          </e163:BusinessAddress>
          <e163:AutoTagType d4p1:nil="false">ValueHere</e163:AutoTagType>
          <e163:SoldToPaymentInstrumentId d4p1:nil="false">ValueHere</e163:SoldToPaymentInstrumentId>
        </e163:AdvertiserAccount>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SearchAccountsResponse> SearchAccountsAsync(
	IList<Predicate> predicates,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchAccountsRequest
	{
		Predicates = predicates,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchAccountsAsync(r), request));
}
```
```java
static SearchAccountsResponse searchAccounts(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchAccountsRequest request = new SearchAccountsRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagementService.getService().searchAccounts(request);
}
```
```php
static function SearchAccounts(
	$predicates,
	$ordering,
	$pageInfo)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchAccountsRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchAccounts($request);
}
```
```python
response=customermanagement_service.SearchAccounts(
	Predicates=Predicates,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  
