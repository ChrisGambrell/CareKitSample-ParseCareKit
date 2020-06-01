# CareKitSample+ParseCareKit

An example application of [CareKit](https://github.com/carekit-apple/CareKit)'s OCKSample synchronizing with [ParseCareKit](https://github.com/netreconlab/ParseCareKit). 

**Use at your own risk. There is no promise that this is HIPAA compliant and we are not responsible for any mishandling of your data**

## Setup Your Parse Server
You can setup your parse-server locally to test using [parse-postgres](https://github.com/netreconlab/parse-postgres). Simply type the following to get your parse-server running with postgres locally:

1. Fork [parse-posrgres](https://github.com/netreconlab/parse-postgres)
2. `cd parse-postgres`
3.  `docker-compose -f docker-compose.hipaa.yml up` - this will take a couple of minutes to setup as it needs to initialize postgres, but as soon as you see `parse-server running on port 1337.`, it's ready to go. See [here](https://github.com/netreconlab/parse-postgres#getting-started) for details.

## Clone this repo to ger the modified OCKSample app. 

1. Fork [CareKitSample-ParseCareKit](https://github.com/netreconlab/ParseCareKit)
2. Open `OCKSample.xcworkspace` in Xcode
3. You may need to configure your "Team" and "Bundle Identifier" in "Signing and Capabilities"
4. Build the project. If you get any errors, type "pod update" in the project director in Terminal
5. Run the app and data will synchronize with parse-postgres via "http://localhost:1337/parse" automatically

## View your data in Parse Dashboard
Parse Dashboard is the easiest way to view your data in the Cloud (or local machine in this example) and comes with [parse-postgres](https://github.com/netreconlab/parse-postgres). To access:
1. Open your browser and go to `http://localhost:4040/`
2. Username: `parse`
3. Password: `1234`

Note that CareKit data is extremely sensitive and you are responsible for ensuring your parse-server meets HIPAA compliance.
