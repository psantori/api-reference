# One changelog
---

### Version 1.21.0 (2018/05/18)

- **New features**
    *  GDPR : it is possible to delete all conversations and customers' data that invoked the right to be forgotten
    *  Total email sent and date of last email sent are displayed in the customer list for each customer
    *  History of sent emails is displayed for each customers
    *  Sending an IM to a customer, creates a campaignSent event in Hub associated to that customer
    *  New endpoint /images/<URL> 
    *  New endpoint to delete Customers

- **Minor fix and improvements**
    *  Improved loading time of customer list 
    *  Fixed DND policy for WeChat


### Version 1.19.0 (2018/04/20)

- **New features**
    * The ability to configure more than one store for a Contactone workspace.
    * The ability to configure the email sender as the Store or the Sales Associate.
    * Added DELETE for endpoint /applications/{applicationId}.
    * Changed endpoint /users.

- **Minor fix and improvements**
    * mediaUrl for inbound image.


### Version 1.18.0 (2018/09/03)

- **New features**
    * It is now possible to receive IM messages with images.
    * The management of incoming multiple messages with images has been corrected.
    * Incoming messages can now contain Emoji. 
    * It is now possible to send a complex smartObject on the WeChat channel.

- **Minor fix and improvements**
    * No changes.


### Version 1.17 (2018/02/23)

- **New features**
    * Changes in the object returned by the to/posts call. 

- **Minor fix and improvements**
    * Added an endpoint to modify media (communication channels) that is enabled in the workspace.
    * Added an endpoint to modify the media supported by a template asset.
    * [Bugfix] The data order of threads returned by the call to workspaces/{workspaceId}/conversations/customers has been corrected.
    * [Bugfix] The error that is generated when the company doesn't set the logo has been corrected.


### Version 1.16.0 (2018/02/12)

- **New features**
    * A new adapter allows a generic JSON file to be passed, which will be transformed into a SmartObject.
    * Following the appropriate set up, it is now possible to use Contactone with an external authentication system. 

- **Minor fix and improvements**
    * The object returned by the /post endpoint now has a more usable and understandable schema.
    * Added support for Chinese, Arabic and Japanese characters. 


### Version 1.15.0 (2018/01/26) 

- **New features**
    * Sales Associate Out of Office automatic response. When a sales associate is offline, an automatic response is sent to the customer if they try to make contact.
    * The last message in a thread is now returned when retrieving a customer’s conversation. /workspaces/{workspaceId}/conversations/customers.

- **Minor fix and improvements**
    * The automatic Out of Office response can be customized for every workspace.
    * Every IM message that is sent when the sales associate is offline, is now tagged with a specific value. 
    * Every IM message that is automatically sent by the BOT, is now tagged with a specific value.
    * The Sales Associate profile can be updated with an Online or Offline status.


### Version 1.14.0 (2018/29/01)

- **New features**
    * Ability to change the IM platform for each chat. For example, from LINE to Facebook Messenger.
    * You can now configure the PrimaryLabel popularity order in the workspace.
    * You can now configure the SecondaryLabel popularity in the workspace. 

- **Minor fix and improvements**
    * Links and QR Codes now have an expiry date. 
    * Customer ExtendedData must only contain assignedToUserId.


# Version 1.13 (2017/18/12)

- **New features**
    * It is now possible to search a customer in the customer list page.
    * When creating a customer profile, PrimaryLabel and SecondayLabel are populted by default with firstName and lastName from the customer model.
    * We can now generate QRCode invites for Line, Messenger and WeChat.
    * /workspaces/<workspaceId>/chatroomInvitations returns a list of QRCodes and links to invite a customer in a chat conversation.

- **Minor fix and improvements**
    * Once a customer is created or updated the changes appears immediatly in the customers list.
    * Optimization of the customer list respose time.


### Version 1.12.0 (2017/28/11)

- **New features**
    * Store Managers are now able to change the association between customers and Sales Assistants from the Backend application.
    * Store Managers can filter customers by the associated Sales Assistant.
    * In the Customer list customers are now ordered by last name.
    * It is possible to decide if is possible to create and modify customers in a given workspace.
    * New endpoint /configurations/workspaces/{workspaceId}/permissions with GET and PATCH method to modify the ability to create or update customers on the given workspace.
    * Adding expand=user when calling GET /customers endpoint will return additional information on the user associated with the customer.

- **Minor fix and improvements**
    * In customer profile data are now ordered based on a new filed in the customer model.
    * Errors generated during customer creation or update have now a code that can be mapped by frontend applications.
    * During a new provisiong a Contacthub workspace dedicated to the Sales Assistant is no longer created.


### Version 1.11.0 (2017/10/11)

- **New features**
    * An existing Contacthub workspace can now be used with Contactone, while the fields that represent a Sales Assistant and those that belong to a store, can also be specified. If fields do not exist, they can be created. 
    * A user with the appropriate permissions can now create new customers directly in the Contactone interface. 
    * Before creating a customer, a user can check if they already exist in the workspace. 
    * GET /workspaces/<workspaceId>/configuration allows a check to be carried out for whether a user can create or modify a customer profile.

- **Minor fix and improvements**
    * [BUG]An error that occurred while uploading an image has been corrected. 
    * [BUG] POST /customers now accepts null values.  
    * [BUG] An error that occurred while trying to retrieve templates from the user interface has been corrected. 
    * A check for the date value format has been added. 
    * A Store Manager user can now retrieve all the customers associated with the store.


### Version 1.10 (2017/25/10)

- **New features**
    *, During provisioning, it is now possible to specify an existing Contacthub workspace for Contactone to connect with.
    * /customers POST and /customers/{id} PATCH endpoints are no longer under /configuration.
    * POST /customers body payload has been changed.
    * GET /customers/{id} now returns customerFields as a map. 

- **Minor fix and improvements**
    * Trying to upload an invalid image now provides the user with meaningful error messages. 
    * It is now possible to use templates with both custom text and images.
    * [BUG] While creating a customer, the customerFields can now be set to null.
    * The Contactone frontend and backend now use a new authentication token.
    * A JavaScript integration to log viewedPage events in Contacthub is now available. 
