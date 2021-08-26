# [go back to main](https://github.com/c4arl0s/IntroducingSwiftUI#introducing-swiftui)

# [Creating And Combining Views - Content](https://github.com/c4arl0s/creatingandcombiningviews#go-back-to-main)

1. [x] [1. Create a New Project and Explore the Canvas](https://github.com/c4arl0s/creatingandcombiningviews#1-Create-a-New-Project-and-Explore-the-Canvas)
2. [x] [2. Customize the Text View](https://github.com/c4arl0s/creatingandcombiningviews#2-Customize-the-Text-View)
3. [ ] [3. Combine Views Using Stacks](https://github.com/c4arl0s/creatingandcombiningviews#3-Combine-Views-Using-Stacks)
4. [ ] [4. Create a Custom Image View](https://github.com/c4arl0s/creatingandcombiningviews#4-Create-a-Custom-Image-View)
5. [ ] [5. Use SwiftUI Views From Other Frameworks](https://github.com/c4arl0s/creatingandcombiningviews#5-Use-SwiftUI-Views-From-Other-Frameworks)
6. [ ] [6. Compose the Detail View](https://github.com/c4arl0s/creatingandcombiningviews#6-Compose-the-Detail-View)

# [Creating And Combining Views](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)

This tutorial guides you through building Landmarks - an app for discovering and sharing the places you love. You will start by building the view that shows a landmark's details. 

To lay out the views, Landmarks uses stacks to combine and layer the image and text view components. To add a map to the view, you will include a standard MapKit component. As you refine the view's design, Xcode provides real-time feedback so you can see how those changes translate into code.

Download the Project files to begin building this project, and follow the steps below.

# 1. [Create a New Project and Explore the Canvas](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)

Create a new Xcode project that uses SwiftUI. Explore the canvas, previews, and the SwiftUI template code.

To preview and interact with views from the canvas in Xcode, and to use all the latest features describe throughout the tutorials, ensure your mac is running macOS Big Suer or later. (duh!)

1. Open Xcode and either click "Create a new Xcode project" in Xcode's startup window, or choose File > New > Project.
2. In the template selector, select iOS as the platform, select the App template, and then Click Next.
3. Enter "Landmarks" as the product name, select "SwiftUI" for the interface and "SwiftUI App" for the life cycle, and click next. Choose a location to save the Landsmarks project on your mac.

![Screen Shot 2021-08-24 at 7 54 47](https://user-images.githubusercontent.com/24994818/130619954-995cdb21-4915-44bc-89b4-ef8c52bc988f.png)

4. In the Project Navigator, select LandmarksApp.swift. 

> An app that uses the SwiftUI app life cycle has a structure that conforms to the App protocol. The structure's body property returns one or more scenes, which in turn provide content for display. The `@main` attribute identifies the app's entry point.

```swift
import SwiftUI

@main
struct LandmarksApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

5. In the project navigator, select ContentView.swift.

> By default, SwiftUI views files declare two structures. The first structure conforms to the View protocol and describes the view's content and layout. The second structure declares a preview for that view.

```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        Text("Hello, world!")
            .padding()
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```

6. In the canvas, click Resume to display the preview.

> If the canvas is not visible, select Editor > Canvas to show it.

![Screen Shot 2021-08-24 at 8 05 40](https://user-images.githubusercontent.com/24994818/130621479-21b7bc67-212c-4527-8b49-8a70c9c26abe.png)

7. Inside the body property, change "Hello, World!" to a greeting for yourself.

> As you change the code in a view's body property, the preview updates to reflect your changes.

![Screen Recording 2021-08-24 at 8 07 38 2021-08-24 08_09_10](https://user-images.githubusercontent.com/24994818/130622045-baa8f362-1393-4403-836e-c4b8b99d8b44.gif)

# 2. [Customize the Text View](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)

You can customize a view's display by changing your code, or by using the inspector to discover what's available and to help you write code.

As you build the Landmarks app, you can use any combination of editors: the source editor, the canvas, or the inspectors. Your code stays updated, regardless of which tool you use.

![Screen Shot 2021-08-25 at 7 59 12](https://user-images.githubusercontent.com/24994818/130794861-c7232b51-6457-476f-8063-64994f17983d.png)

1. In the preview, Command-click the greeting to bring up the structured editing popover, and choose "Show SwiftUI inspector".

![Screen Shot 2021-08-25 at 8 01 42](https://user-images.githubusercontent.com/24994818/130795227-2f6df3af-e333-4235-a0fd-42254bd21623.png)

> the popover shows different attributes that you can customize, depending on the type of view you inspect.

![Screen Shot 2021-08-25 at 8 04 33](https://user-images.githubusercontent.com/24994818/130795662-e70baf67-2fab-49ad-8a2a-e9e4adc62f52.png)

2. Use the inspector to change the text to "Turtle Rock", the name of the first landmark you will show in your app.

![Screen Shot 2021-08-25 at 8 06 25](https://user-images.githubusercontent.com/24994818/130795894-182145e9-8d3c-495c-ba60-99a14975ada9.png)

![Screen Shot 2021-08-25 at 8 07 06](https://user-images.githubusercontent.com/24994818/130795998-faa24e88-d829-4149-b5e3-33c9d75c7a53.png)

3. Change the Font modifier to "Title"

> This applies the system font to the text so that it responds correctly to the user's preferred font sizes and settings.

![Screen Recording 2021-08-25 at 8 09 57 2021-08-25 08_11_47](https://user-images.githubusercontent.com/24994818/130796674-00293261-0769-48b0-a567-5896348f64af.gif)

To customize a SwiftUI view, you call methods called **modifiers**. Modifiers wrap a view to change its display or other properties. Each modifier returns a new view, so it's common to chain multiple modifiers, stacked vertically.

4. Edit the code by hand to change the `padding()` modifier to the `foregroundColor(.green)` modifier, this changes the text's color to green.

![Screen Shot 2021-08-25 at 8 16 13](https://user-images.githubusercontent.com/24994818/130797372-9b61e017-95d6-4cde-8b90-3a85b3e4fa4e.png)

> Your code is always the source of truth for the view. When you use the inspector to change or remove a modifier, Xcode updates your code immediately to match.

5. This time, open the inspector by Command-clicking on the Text declaration in the code editor, and then choose "Show SwiftUI inspector" from the popover. Click the Color pop-up menu and choose Inherited to change the text color to blue now)

![Screen Recording 2021-08-25 at 8 19 56 2021-08-25 08_21_19](https://user-images.githubusercontent.com/24994818/130798134-dfb4856b-7bd8-4b8a-a515-c337e3e01767.gif)

6. Notice that Xcode updates your code automatically to reflect the change, removing for `foregroundColor(.green)` modifier.

![Screen Shot 2021-08-25 at 8 25 19](https://user-images.githubusercontent.com/24994818/130798743-51642919-6480-428a-893e-015360553b31.png)
 
# 3. [Combine Views Using Stacks](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)
# 4. [Create a Custom Image View](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)
# 5. [Use SwiftUI Views From Other Frameworks](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)
# 6. [Compose the Detail View](https://github.com/c4arl0s/creatingandcombiningviews#creating-and-combining-views---content)
