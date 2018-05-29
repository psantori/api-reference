# Hub changelog

---


### Version 1.52.0 (2018/05/22)

- **New features**
    * the possibility to read the configuration names with TRUSTED_TOKEN
    * the functionality cascading delete of event has been added. Now, when a customer profile is delated, all the events related to his profile are canceled


### Version 1.51.0 (2018/05/17)

- **New features**
    * Due to the GDPR every change in the consents section will be stored in a register where all the variations are always available. In this way it is possible to rebuild the consents history of every single customer. The register is available only from users with a DPO role. 


### Version 1.49.0 (2018/05/09)

- **New features**
    * Web events (viewedPage, clickedLink, loggedIn, loggedOut, searched) are now exported from Contacthub to Contactplan 


### Version 1.48.0 (2018/05/03)

- **New features**
    * ServiceSubscribed and serviceUnsubscribed are now exported from Contacthub to Contactplan 


### Version 1.47.0 (2018/04/26)

- **New features**
    * The main improvement is about the availability of a new resource in the API called “Updates”. Here all the changes of the customer base (customers and events) are reported. Every application can read from this resource the changes intercurred and be updated about what happens in Contacthub.


### Version 1.42.0 (2018/03/28)

- **New features**
    * Automation: ability to use contextInfo properties as a condition for trigger automations


### Version 1.39.0 (2018/03/16)

- **New features**
    * Consents: added a new section of customer dedicated to contents' storage. This customer section has a predefined structure. The structure's model is consultable here: http://developer.contactlab.com/documentation/contacthub/schemas/customer.consents.html
    * Automation: now it's possible to use the identifier (id) of the event in all the automations.
    * Source token: with a trusted source token now an application can read the properties base/extended structure


### Version 1.36.0 (2018/02/27)

- **New features**
    * Source Contactsend & Contactplan: limitations in the configuration have been added. They are are necessary to ensure the integrity/consistency of data in all Contactlab products. To maintain this data consistency the limitations are based on the principle: "one source: one node: one userdb".


### Version 1.31.0 (2018/01/17)

- **New features**
    * In the customer resource section are now available new info about the sources which create and update the resource
    * The properties of customer resource: base, extended, extra have now a limit of 64Kb each
    * The properties of event resource: properties, contextInfo have now a limit of 64Kb each


## Version: 1.29.0 (2018/01/08)

- **New features**
    * The audit resource is no longer available (Ref: GET /workspaces/{workspaceId}/audit) 


## Version: 1.27.0 (2018/01/03)

- **New features**
    * Event resource: the constraint with the customer ID has been removed. Now you can display all the events of one or more nodes

- **Minor fix and improvements**
    * Various bug fixes


## Version: 1.24.0 (2017/12/15)

- **New features**
    * Automation trigger: in send email action it is now possible to use the contextInfo properties

- **Minor fix and improvements**
    * Various bug fixes


## Version: 1.21.2 (2017/12/05)

- **New features**
    * Source Contactsend: fix of bug about subscriptions patch

- **Minor fix and improvements**
    * Various bug fixes 


## Version: 1.21.1 (2017/12/04)

- **New features**
    * Source Contactplan: now the properties "vendor", "weight" and "itemQty" of completedOrder events are synchronized with Contactpan and all product category are synchronized into "product_classification_1"

- **Minor fix and improvements**
    * Various bug fixes


## Version: 1.13.0 (2017/10/05)

- **New features**
    * Now, you can also manage the Customer Base within the UI and, for example, insert, modify or delete profiles and events, directly in the interface.
    * The number of Completed Order event ‘classification’ properties that can be synchronized with Contactplan, has been increased to 15. You can now configure ten text and five data classifications.


## Version: 1.12.0 (2017/09/20)

- **New features**
    * During synchronization with Contactplan, you can now select up to 10 categories to be updated. This enables you to synchronize 10 additional fields, on top of the basic structure of the Completed Order event. (Note: All the fields are formatted as strings.) 


## Version: 1.11.0 (2017/09/13)

- **New features**
    * Adding events: The response that is received when a new event is added, is no longer an empty field, but is now the unique ID assigned to the event (the insertion is still asynchronous)
    * Event search: When a user applies, for example, an event or a contest filter, it is now possible to search for a list of values
    * The initial dashboard displays the last 30 days of data


## Version: 1.10.0 (2017/08/10)

- **New features**
    * Automation (_tag_): the extra properties of event may now be used


## Version: 1.9.0 (2017/07/17)

- **New features**
    * Introduced capabilty to modify events
    * Contactsend feedbacks are now automatically available in Contacthub
    * The new _region_ property has been added to the customer base properties
    * New _weight_, _itemQuantity_, _vendor_ properties have been added to the abandonedCart, completedOrder, addedCompare, removedCompare, addedProduct, removedProduct, addedWishlist, removedWishlist, viewedProduct events
    * New _unitOfMeasure_ property has been added to the completedOrder, abandonedCart, addedProduct, removedProduct events
 

## Version: 1.8.0 (2017/05/31)

- **New features**
    * Feedbacks generated by an mail sent as a result of an automation are now available
    * Implemented the retry in Contactsend synchronization to prevent failures in case the destination database is locked
 

## Version: 1.7.0 (2017/05/16)

- **New features**
    * Added _orderLineId_ property in completedOrder and abandonedCart events
    * Automation can now be triggered after a predefined delay


## Version: 1.6.0 (2017/05/02)

- **New features**
    * Automation (_webhook_, _email_): the extra properties of event may now be used
 

## Version: 1.5.0 (2017/04/19)

- **New features**
    * New sources available: Contactsend subscription management system (ClientSection), Contactsend Facebook/Instagram LeadAds module. 
 

## Version: 1.4.0 (2017/04/04)

- **New features**
    * Matching policy: case sentiveness may be set according to specific needs.
    * Automation (_webhook_, _email_): customer data can now be used


## Version: 1.3.0 (2017/03/21)

- **New features**
    * Synchronize ecommerce event with Contactplan


## Version: 1.2.0 (2017/03/08)

- **New features**
    * Added parameters of google analytics tracking in the event collection
    * Added events data model in the event collection


## Version: 1.1.0 (2017/02/17)

- **New features**
    * Added mobile device structure in the customer properties base


## Version: 1.0.0 (2017/02/14)

- **New features**
    * Hello Hub!
