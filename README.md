# Flutter Widget Integration

For Flutter, you can integrate with our widget using the in-app browser package `flutter_web_browser`. Note that using the webviews will cause authentification issues with some of the wearable providers.

Below are integration steps

## Ressources
A demo project is available on https://github.com/tryterra/Terra-Flutter-Widget

## Installation
After setting up the flutter application, add the `flutter_web_browser` dependency to your `pubsec.yaml` and install using `flutter pub get`. More details about the package can be found [here](https://pub.dev/packages/flutter_web_browser#-readme-tab-).

## Generate Session ID
Before using the in-app browser, you must generate a Session ID to pass to your application from your backend [here](https://docs.tryterra.co/sessions-beta).

## Using the in-app browser

The following code snipet will open an in-app browser session and connect to a Terra session

```dart
openBrowserTab() async {
    FlutterWebBrowser.openWebPage(
      url: "https://widget.tryterra.co/session/xxxx-xxxx-xxxx-xxxx-xxxx",
      customTabsOptions: const CustomTabsOptions(
        colorScheme: CustomTabsColorScheme.dark,
        toolbarColor: Colors.deepPurple,
        secondaryToolbarColor: Colors.green,
        navigationBarColor: Colors.amber,
        shareState: CustomTabsShareState.on,
        instantAppsEnabled: true,
        showTitle: true,
        urlBarHidingEnabled: true,
      ),
      safariVCOptions: const SafariViewControllerOptions(
        barCollapsingEnabled: true,
        preferredBarTintColor: Colors.green,
        preferredControlTintColor: Colors.amber,
        dismissButtonStyle: SafariViewControllerDismissButtonStyle.close,
        modalPresentationCapturesStatusBarAppearance: true,
      ),
    );
}
```
## Videos

[iOS demo](media/android.mp4)

[Android demo](media/ios.mp4)