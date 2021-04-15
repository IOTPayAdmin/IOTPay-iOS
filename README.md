# IOTPay-iOS
###### IOTPay Framework for iOS
<br />    


IOTPay-iOS is a smiple to use yet powerful Framework helps you with the online payment for iOS apps.

<br />      

## Step 1: Install 
Intall IOTPay-iOS form pod/github.

For Pod reference and how-to, please follow this link:
https://guides.cocoapods.org/using/the-podfile.html



<br />      

## Step 2: Setup View
Declare the view before viewDidLoad. This is not mandatory for display the view, but you will need it for the send request event in step 3.
```
var cardInfoView: IOTCardInfoViewSingleLine!
```

Add following code in ViewController after viewDidLoad

```
cardInfoView = IOTCardInfoViewSingleLine(action: .addUser, style: .roundRect)
view.addSubview(cardInfoView)
```
This will start the interface for user to fillin the card info.



<br />      

## Step 3: Send the Request
After user filling the card info, sending the request by:
```
IOTNetworkManager.shared.sendRequest(secureId: "your secureId", cardInfoPrivder: cardInfoView)
```
That's all we need for basic setup to add a card!
(You will need to set up a button for sendRequest after user filling the info)
For sample example, please check sampleExample. 
- SimpleDemo 

For more usage, such as delegate to let you know user filling the vliad info and complete, or more style/layout settings, please check the other examples:
- TripleLineDemo (NOT yet)
- DelegateDemo (NOT yet)
- StylingDemo (NOT yet)




<br />      

## Quick Data reference:
#action: 
```
enum IOTNetworkRequestAction {
	case addCard           // add card, you will receive desensitizated card info after the network request.
	case oneTimePurchase   // one time payment, without saving user's payment method
}
```


#style: 
```
enum IOTCardInfoViewStyle {
	case roundRect
	case infoLight
	case infoDark   // for nightmode
}
```

#cardInfoPrivder: 
```
IOTCardInfoView
```
Should fill in the name/pointer of the view that user filling in the info, this is required for sending the request.

#secureId:<br />   

This was generated by IOTPay server, you need to register an IOTPay account first, then following the steps to host a merchandise server.
For more detials about account, secureId and merchandise server, please visit:
https://develop.iotpay.ca


