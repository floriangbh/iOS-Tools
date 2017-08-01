# Tools

Quick note for iOS/macOS development tools :
* [Cocoapods](#cocoapods)
* [SwiftLint](#swiftlint)
* [Fastlane](#fastlane)
* [Carthage](#carthage)
* [Vapor](#vapor)

## Cocoapods  

### Manage dependency 

Install cocoapods : 

``` 
sudo gem install cocoapods
``` 

Pod declaration in `Podfile` :
```
pod '<pod_name>' 
pod '<pod_name>', :git => '<repo_url>.git', :branch => '<branch_name>' #specify branch 
pod '<pod_name>', :git => '<repo_url>.git', :commit => '<commit_tag>' #specify commit 
``` 
Install pods (based on `Podfile.lock`) :
```
pod install
``` 
Update all pods : 
```
pod update
``` 

### Publish new pod version 

Check project before push to cocoapods :
```
pod spec lint <my_pod_file>.podspec
``` 
If lint passing, push to cocoapods : 
```
pod trunk push <my_pod_file>.podspec
``` 

## Carthage 

Install [Carthage](https://github.com/Carthage/Carthage) : 

``` 
brew install carthage
``` 

Declaration in `Cartfile` (exemple) :
```
github "ashleymills/Reachability.swift" 
github "ashleymills/Reachability.swift" ~> 3.0
``` 

Install carthage (based on `Cartfile.resolved`) :
```
carthage bootstrap
``` 

Update all : 

```
carthage update 
```

## Vapor

Clean : 
```
vapor clean -y
```

Build : 
```
vapor build 
```

Generate Xcode project (to build with SPM dependency) : 
```
vapor xcode 
```

Deploy on heroku (after login with heroku toolbox) :
``` 
vapor heroku push 
```

## Swiftlint

[A tool to enforce Swift style and conventions.](https://github.com/realm/SwiftLint)

Installation : 
``` 
brew install swiftlint
```

Auto correction
``` 
swiftlint autocorrect
```

To add SwiftLint to xcodeproject just add a new "Run Script Phase" : 
```swift
if which swiftlint >/dev/null; then
  swiftlint
else
  echo "warning: SwiftLint not installed, download from https://github.com/realm/SwiftLint"
fi
```


## Fastlane

Todo
