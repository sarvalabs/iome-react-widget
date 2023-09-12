# IOMe Widget
[joinSlack]: https://join.slack.com/t/iomeai/shared_invite/zt-20s1w9jxg-unzBomKqMBrrq~DlYNpQHQ
[connectOnTwitter]: https://twitter.com/iome_ai
[documentation]: https://dev.iome.ai/docs/widget

[![npm version](https://badge.fury.io/js/@iome%2Freact-widget.svg)](https://badge.fury.io/js/@iome%2Freact-widget)
[![Chat on Slack](https://img.shields.io/badge/Slack-Dev%20community-blue)][joinSlack]
[![docs](https://img.shields.io/badge/Widget-Documentation-orange)][documentation]
[![Follow us on Twitter](https://img.shields.io/badge/Twitter-Follow%20Us-blue?style=social&logo=twitter)][connectOnTwitter]
## Overview

IOMe widget facilitates a comprehensive assortment of UI components. Alongside, the IOMe library introduces dedicated modules for developers, applications, and users. Furthermore, the Utils library presents an array of utility functions, encompassing a wallet library, encoding and cryptography functions, and an array of other practical utilities. This holistic approach ensures that IOMe optimally caters to the multifaceted needs of your web application.
To find information about the IOMe widget and its prerequisites, please visit this [link](https://dev.iome.ai/docs/widget).

This package is designed to work seamlessly with both ReactJS and NextJS frontend frameworks.

## Installation
> npm install @iome/react-widget
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

This Connect Component is responsible for managing both _current users of the applications and onboarding of new ones_.

### Utils
**enc** <br />
The _Utils.enc_ class is created with the intent of simplifying the encoding and decoding of both general strings like Usernames and Attribute names, as well as specific `IOMe namespaces` like _App names, Account names and Avatar names_.
- `Utils.enc.mEncode(<string>)`
- `Utils.enc.mDecode(<encodedstring>, <isNamespace>)`, pass isNamespace=true if encoded string is IOMe namespace.

**zk** <br />
The _Utils.zk_ class is intended to assist in the generation and verification of Zero-Knowledge Proofs (ZK Proofs) that are created during interactions in IOMe.

## Support
If you need more clarifications, feel free to join our [Slack community][joinSlack]. You can also refer to our [Widget docs][documentation].

## License
UNLICENSED
