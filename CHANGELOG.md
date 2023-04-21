#  Native Checkout iOS SDK Release Notes

## 0.112.0 (2023-04-19)
- *Breaking Changes*
  - Increased minimum supported iOS version to 13.0
  - Increased minimum supported Xcode version to 14.1
  - Increased Swift language version to 5.7.1
  - Updated the definition of `ShippingChangeAddress` to align with the Android implementation, and to remove the `fullName` from the interface, as this is considered protected end user information
    - Removed `ShippingChangeAddress.fullName`
    - Removed `ShippingChangeAddress.adminArea3`
    - Removed `ShippingChangeAddress.adminArea4`

- *Feature Updates*
  - Added the ability for users to add an initial payment method to their PayPal account
  - Updated the UI of the native add-card flow to include complete address input
 
- *Non-Breaking Changes*
  - Removed the default exit survey, deprecating `Checkout.showsExitSurvey`
  - Fixed a broken web redirect for non-US locales
  - Resolved layout and display issues related to Billing Agreement flows
  - Added support for programmatic logout by calling `Checkout.logoutUser()`
  - UI updates to provide more accessible experience
  - Localization updates
  - Added the ability to force a web fallback 
    - Can be seen via setting `yourCheckoutConfig.showWebCheckout = true` 
  - Additional bugfixes and layout adjustments

## 0.109.0 (2022-10-10)
- Adding a new interface to get details about an order through Approval.actions. This interface only supports orders created with the orders/v2 API, and integrating with this interface may look something like this:
```swift
// Wherever you define the `onApprove` callback
      ... , 
      onApprove: { approval in
        approval.actions.getOrderDetails { details, error in
          // record the details of your order here
        }
      },
      ...
```      
The `details` object will give you insight into the `Payer`, the array of `PurchaseUnits`, and a raw JSON that includes other fields that do not have types added yet.
- Accessibility Improvements
- Bug fixes

## 0.108.0 (2022-09-29)
- Bugfixes and performance improvements
- Accessibility updates
- Localization updates

## 0.106.0 (2022-09-06)
- Full EU support with 3DS support for contingency resolution
  - For more information on how to enable 3DS support, see the README.md for instructions on installing the `CardinalMobile.xcframework`
- Bug fixes and improved localizations
- Improved accessibility support

## 0.104.0 (2022-09-01)
- Fixes an issue with app validation when submitting to the store.

## 0.103.0 (2022-08-29)
- Fixes an issue related to dependency resource bundle and framework path during app validation
  while submitting to the store.

## 0.102.0 (2022-08-22)
- OTP
- Bug Fixes

## 0.101.0 (2022-07-28)
- Fixed an issue where users quickly launching and exiting SDK sessions could be given a very poor user experience
- Resolved some occasionally broken constraints
- Updated translations
- Bug fixes and security updates

## 0.100.0 (2022-07-15)
- Added native support for billing agreement flows
- Updated localizations
- Several performance, constraint, and security improvements

