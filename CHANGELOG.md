Changelog
=========

Version 1.7.0 (02.02.2022)
--------------------------

- Fix issues with uploads of text files containing `--` symbols.([#31](https://github.com/pCloud/pcloud-sdk-java/issues/31))
- Add `ApiClient.getChecksums()` methods for obtaining remote file content checksums. ([#28](https://github.com/pCloud/pcloud-sdk-java/issues/28))
- Update to the latest OkHttp (4.9.3)
- Update to Kotlin 1.6.10

###**BREAKING CHANGES**: 
- `DataSource.contentLength()` can no longer return `-1L` as a valid value for cases where the data is not known beforehand. 
Due to compatibility reasons pCloud's API endpoints do not accept HTTP requests with unknown content length, 
thus making upload operations for such content largely slow & inefficient. 
Expect the issue to be solved in a later version of the SDK which shifts to use the binary protocol offered by pCloud API servers.([#30](https://github.com/pCloud/pcloud-sdk-java/issues/30))

Version 1.6.0 (16.12.2021)
--------------------------

- Bump the java source compatibility version to 1.8 (Java 8).
- Raise the minimum Android SDk to API21 (Android 5.0 Lollipop) for the Android-enabled artifacts.
- Update to the latest OkHttp (4.9.0)
 
Version 1.5.0 (16.12.2021)
--------------------------

- Add support for [custom tabs](https://developer.chrome.com/docs/android/custom-tabs/) in the `android` artifact solving issues with
Google Sign-in from WebViews. ([#21](https://github.com/pCloud/pcloud-sdk-java/issues/21))
- Add a Kotlin coroutines-enabled artifact with helper methods for suspending execution of `Call<T>` in coroutine contexts.
