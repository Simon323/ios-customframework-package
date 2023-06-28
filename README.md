# CustomFramework

## Create Package proj

In Xcode
1. File -> New -> Package...

## Open-source

In `Package.swift` use `target` in targets array

```swift
let package = Package(
    name: "CustomFramework",
    platforms: [.macOS(.v12), .iOS(.v14)],
    products: [
        .library(
            name: "CustomFramework",
            targets: ["CustomFramework"]),
    ],
    dependencies: [],
    targets: [
        .target(
            name: "CustomFramework",
            dependencies: []),
        .testTarget(
            name: "CustomFrameworkTests",
            dependencies: ["CustomFramework"]),
    ]
)
```

## Binary target

In `Package.swift` use `binaryTarget` in targets array

```swift
let package = Package(
    name: "CustomFramework",
    platforms: [.macOS(.v12), .iOS(.v14)],
    products: [
        .library(
            name: "CustomFramework",
            targets: ["CustomFramework"]),
    ],
    dependencies: [],
    targets: [
        .binaryTarget(name: "CustomFramework", path: "./Sources/CustomFramework.xcframework")
    ]
)
```

## Packages versioning
Add git tag
```bash
$ git tag 0.0.1
```

Push git tags
```bash
$ git push --tags
```