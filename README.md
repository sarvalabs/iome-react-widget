# IOMe Widget
[joinSlack]: https://join.slack.com/t/iomeai/shared_invite/zt-20s1w9jxg-unzBomKqMBrrq~DlYNpQHQ
[connectOnTwitter]: https://twitter.com/iome_ai
[documentation]: https://dev.iome.ai/docs/widget

[![npm version](https://badge.fury.io/js/@iome%2Freact-widget.svg)](https://badge.fury.io/js/@iome%2Freact-widget)
[![Chat on Slack](https://img.shields.io/badge/Slack-Dev%20community-blue)][joinSlack]
[![docs](https://img.shields.io/badge/Widget-Documentation-orange)][documentation]
[![Follow us on Twitter](https://img.shields.io/badge/Twitter-Follow%20Us-blue?style=social&logo=twitter)][connectOnTwitter]
## Overview

The IOMe widget offers an extensive collection of UI components and specialized modules for developers, applications, and users. Additionally, the Utils module provides a wide range of utility functions, including a wallet library, encoding and cryptography tools etc. This comprehensive approach guarantees that IOMe effectively addresses the diverse requirements of your web or mobile application.

Moreover, this npm package is specifically crafted to seamlessly integrate with both ReactJS and NextJS frontend frameworks.

## Installation
> npm install @iome/react-widget

## Pre-requisites
Before you begin, ensure you have your `DeveloperID` and `AppSecret` ready. You can find instructions on how to obtain them by visiting this [link](https://dev.iome.ai/docs/devportal).
## Usage
```jsx
// Import
import { IOMe, Connect, Utils } from "@iome/react-widget"
let iomeObj = new IOMe("<developerID>","<AppSecret>");

// Init
useEffect(() => {
	async function __initIome() {
		try {
			await iomeObj.InitDev();
			await iomeObj.InitApp();
		}catch(e) {
			// handle error
		}
	}
	__initIOMe();
},[])


```
### Connect Widget
```jsx
<Connect
	onSuccess={// handle success event}
	iome={iomeObj}
/>
```

This Connect component is responsible for managing both _**current users**_ of the applications and _**onboarding of new users**_.
### App and user modules
- **App** <br />
	To initialize the App module, simply use the following code: 
	```js
	const iome = new IOMe(DeveloperID, AppSecret)
	iome.InitDev()
	iome.InitApp()
	```

	To learn more about the functions under the app module. Visit [this](https://dev.iome.ai/docs/widget) page.

- **User** <br />
	To initialize the User module, you must connect the widget to your application as detailed in the [Connect Widget](#connect-widget) section.

	Once a user logs in using their IOMe credentials, the User module will be automatically initialized. This allows you to access any function under it. For instance, to generate a user session token, you can make the following call:

	#### Generate User Auth Token

	```js
	// iome.user.getAuthToken(DAT Token Type, message)
	iome.user.getAuthToken("SESSION", <timestamp>)
	```

	Please ensure that the user has successfully logged in before using this function.

### Utils module
**enc** <br />
The _Utils.enc_ class is created with the intent of simplifying the encoding and decoding of both general strings like Usernames and Attribute names, as well as specific `IOMe namespaces` like _App names, Account names and Avatar names_.
- `Utils.enc.mEncode(<string>)`
- `Utils.enc.mDecode(<encodedstring>, <isNamespace>)`, pass isNamespace=true if encoded string is IOMe namespace.

**zk** <br />
The _Utils.zk_ class is intended to assist in the generation and verification of Zero-Knowledge Proofs (ZK Proofs) that are created during interactions in IOMe.

## Support
If you need more clarifications, feel free to join our [Slack community][joinSlack]. You can also refer to our [Widget docs][documentation].

## License
This project is licensed under either of
- [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0) ([`LICENSE-APACHE`](LICENSE-APACHE))
- [MIT license](https://opensource.org/licenses/MIT) ([`LICENSE-MIT`](LICENSE-MIT))

at your option.

The [SPDX](https://spdx.dev) license identifier for this project is `MIT` or `Apache-2.0`.
