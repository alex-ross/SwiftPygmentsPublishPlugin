# SwiftPygments Plugin for Publish

A Pygments plugin for [Publish](https://github.com/johnsundell/publish) to highlight code. 

[Pygments](https://pygments.org) is a syntax highlighting tool made in Python that supports many languages. 

## Requirements

- `Python`
- `Pygments`: [https://pygments.org](https://pygments.org)
- `Swift 5`
- Pygments color scheme in your .css file

SwiftPygments uses `PythonKit` to interact with Pygments.

## Installation
1. Install `Python` if you don't have it on your system.
2. Install `Pygments` if you don't have it on your system. 
``` zsh
$ pip3 install pygments
```
3. Add `SwiftPygmentsPublishPlugin` to your package. 

```swift
let package = Package(
    ...
    dependencies: [
    .package(url: "https://github.com/Ze0nC/SwiftPygmentsPublishPlugin", .branch("master"))
    ],
    targets: [
        .target(
            ...
            dependencies: [
                ...
                "SwiftPygmentsPublishPlugin"
            ]
        )
    ]
    ...
)
```

## Usage

1. Add `.pygments()` to your build pipeline.
```swift
import SwiftPygmentsPublishPlugin
...
try MyWebsite().publish(using: [
    .installPlugin(.pygments()),
    ...
    .addMarkdownFiles(),
    ...
])
```
2. Add a pygments color scheme in your `css` file. You can find many on internet. 

3. Write highlighted codes!

In your markdown file, specify language after ``` to get correct highlight. 
````markdown
```swift
let str = "This is Swift code."
print(str)
```
````

Specify code as `python`
````markdown
```python
str = "This is also Swift code."
print(str)
```
````


If no language is specified, `swift` syntax will be used as default. 
````markdown
```
let str = "This is also Swift code."
print(str)
```
````




## Note 
This plugin will highlight all code block but not inline codes.

Enjoy your highlighted sites!

## Acknowledgement

Thanks to John Sundell (@johnsundell) for creating [Publish](https://github.com/johnsundell/publish) and SplashPublishPlugin

## License
MIT License
