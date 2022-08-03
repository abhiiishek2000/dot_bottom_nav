
# dot_bottom_nav

A flutter package that provides awesome bottom navigation bar with dot indicator. The features is:
1. Rounded bottom nav
2. Floating bottom nav
3. Dot indicator
4. Customizable according to need
## Installation 

1. Add the latest version of package to your pubspec.yaml (and run`dart pub get`):
```yaml
dependencies:
  dot_bottom_nav: ^0.0.1
```
2. Import the package and use it in your Flutter App.
```dart
import 'package:dot_bottom_nav/dot_bottom_nav.dart';
```

## Example

<img src="https://raw.githubusercontent.com/abhiiishek2000/dot_bottom_nav/master/screenshot/Screenshot_20220803-013110.png" width="300" height="600"></img>

```dart
SafeArea(
      child: Scaffold(
        extendBody: true, //  If you want to show body behind the navbar, it should be true
        body: ListView.builder(
            itemCount: 50,
            itemBuilder: (context, index) {
              return ListTile(
                leading: CircleAvatar(
                  backgroundColor: Colors.green,
                  child: Icon(Icons.account_circle),
                ),
                title: Text('Name $index'),
                subtitle: Text('Name $index'),
              );
            }),
        bottomNavigationBar: DotBottomBar(
          currentIndex: selectedIndex,
          selectedColor: Colors.indigo,
          unSelectedColor: Colors.black54,
          indicatorType: IndicatorType.bottom,
          dotIndicatorWidth: 8,
          enableDotIndicator: true,
          onTap: (value){
            setState(() {
              selectedIndex = value;
            });
          },
          navBarItems: [
            NavBarItems(icon: Icons.home, label: "Home"),
            NavBarItems(icon: Icons.email, label: "Email"),
            NavBarItems(icon: Icons.phone, label: "Phone"),
            NavBarItems(icon: Icons.settings, label: "Settings"),
          ],
        ),
      ),
    )
```

