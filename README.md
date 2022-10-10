# Azure API Management 
# Product Provision

## Introduction
Product is a collection of APIs which can be published 


## Add/Create products

![Create Product](./assets/apim-add-product-01.png)
<br/>
1. Login to console and navigate to the API management instance that already created (from previous topics)
2. Select `Products` from menu plane (left-hand side)
3. Click `+ Add` to create the new API `Product`
4. Fill in API product detail 

<br/>

![Create Product Detail](./assets/apim-add-product-02.png)

<br/>

- Name (name of product)
- ID (this value will be auto generated from name, but can be adjusted)
- Description
- Publish (Leave unchecked for this stage)
- Requires Subscription (Leave unchecked for this stage)
- Requires Approval (Leave it unchecked)
- Legal term (Optional)
- APIs (Leave it as default for this stage)
5. Click `Create` for creating the APIs `Products`



## Add API(s) to Product
Before add APIs to Product, you must have APIs created (or import) to Azure API Management instance first. (assume that this step is done in the previous topics)


1. Login to console and navigate to your API management instance, Product and select the product that you want to add APIs to
2. Select `Products` from menu plane (left-hand side)
3. Select `APIs` from the menu plane and then click `+ Add` to add APIs to Product
3. Select APIs from the list and then click `Select` to add APIs to Product

<br/>

![Add APIs to Product](./assets/apim-add-api-product-01.png)

<br/>
<br/>


## Configure Subscription
In the previous steps, we have created and configured Product with desired APIs. However, those API can be publicly access without any access control.

This section we will improve the security by configure Product to require `subscription` this technique can be use to control the access to product which we require it to be private APIs. Or can be used to allow some specific set of clients that can be access to this product.

In order to make APIs/Product requires subscription (to increase security), Need to configure both APIs level and Product level. (According to Azure official document)

```
When API Management receives an API request from a client without a subscription key, it handles the request according to these rules:

Check first for the existence of a product that includes the API but doesn't require a subscription (an open product). If the open product exists, handle the request in the context of the APIs, policies, and access rules configured for the product.
If an open product including the API isn't found, check whether the API requires a subscription. If a subscription isn't required, handle the request in the context of that API and operation.
If no configured product or API is found, then access is denied.
```
[Reference](https://learn.microsoft.com/en-us/azure/api-management/api-management-subscriptions)

### Enabled Subscription requirement (APIs)
1. Login to console and navigate to your target product in the Azure API Management
2. On the `Settings` tab, Section `Subscription`, click checkbox `Subscription Requires`
3. Click `Save` to save changes
<br/>

![Enable API Subscription](./assets/apim-api-subscription-01.png)

<br/>

### Enabled Subscription requirement (Products)
1. Login to console and navigate to your target APIs in the Azure API Management
2. Enable subscription by click checked the `Requires Subscription`
3. Click `Save` to apply the change

## Test consume private API(s) using subscription keys


## Increse security by add ip-filtering


