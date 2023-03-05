# Flutter Page Transition Package

This package gives you beautiful page transitions.
# Types of transitions

+ fade
+ rightToLeft
+ leftToRight
+ topToBottom
+ bottomToTop
+ scale (with alignment)
+ rotate (with alignment)
+ size (with alignment)
+ rightToLeftWithFade
+ leftToRightWithFade
+ leftToRightJoined
+ rightToLeftJoined
+ topToBottomJoined
+ bottomToTopJoined
+ leftToRightPop
+ rightToLeftPop
+ topToBottomPop
+ bottomToTopPop

# Usage for predefined routes

First, define the `onGenerateRoute` property in the `MaterialApp` widget like below and in `switch cases` you can transition to your new routes:
```dart   
onGenerateRoute: (settings) {
    switch (settings.name) {
      case '/second':
        return PageTransition(child: SecondPage(), type: PageTransitionType.scale);
        break;
      default:
        return null;
    }
  }
 ```
 After that you can use your new route like this:
 ```dart 
 Navigator.pushNamed(context, '/second');
 ```
 # Usage predefined routes with RouteSettings
 First, define the `onGenerateRoute` property in the `MaterialApp` widget like below and in `switch cases` you can transition to your new routes:
 ```dart 
    onGenerateRoute: (settings) {
        switch (settings.name) {
          case '/second':
            return PageTransition(
              child: SecondPage(),
              type: PageTransitionType.scale,
              settings: settings,
            );
            break;
          default:
            return null;
        }
      }
 ```
  After that you can use your new route like this:
 ```dart 
Navigator.pushNamed(context, '/second', arguments: "arguments data");
 ```
 
# Usage routes with Inherited Theme
set `ctx` with BuildContext. `ctx` mandatory when inheritTheme set to `true`
```dart
Navigator.push(
      context,
      PageTransition(
        type: PageTransitionType.rightToLeft,
        child: TargetPage(),
        inheritTheme: true,
        ctx: context),
);
```
# Do you want use theme transitions ?
set `type` to `PageTransitionType.theme` and you will use your own theme transitions.

```dart
Navigator.push(
      context,
      PageTransition(
        type: PageTransitionType.theme,
        child: TargetPage(),
       ),
);
```
### Usage routes with IOS Swipe Back
set `isIos` to `true`
```dart
Navigator.push(
      context,
      PageTransition(
        type: PageTransitionType.rightToLeft,
        child: TargetPage(),
        isIos: true,
       ),
);
```
Note: IOS swipe back can only use for rightToLeft and fade transition

```dart 
Navigator.push(context, PageTransition(type: PageTransitionType.fade, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.leftToRight, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.rightToLeft, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.rightToLeft, child: DetailScreen(), isIos: true));

Navigator.push(context, PageTransition(type: PageTransitionType.topToBottom, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.bottomToTop, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.scale, alignment: Alignment.bottomCenter, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.size, alignment: Alignment.bottomCenter, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.rotate, duration: Duration(second: 1), child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.rightToLeftWithFade, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.leftToRightWithFade, child: DetailScreen()));

Navigator.push(context, PageTransition(type: PageTransitionType.leftToRightJoined, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.rightToLeftJoined, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.topToBottomJoined, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.bottomToTopJoined, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.leftToRightPop, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.rightToLeftPop, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.topToBottomPop, child: DetailScreen(), childCurrent: this));

Navigator.push(context, PageTransition(type: PageTransitionType.bottomToTopPop, child: DetailScreen(), childCurrent: this));
```
