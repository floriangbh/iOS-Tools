# Tools

Quick note for iOS/macOS development tools :
* [Cocoapods](#cocoapods)
* [SwiftLint](#swiftlint)
* [Fastlane](#fastlane)
* [Carthage](#carthage)
* [Vapor](#vapor)
* [Jazzy](#jazzy)

## Cocoapods 

[Link to the repository.](https://github.com/CocoaPods/CocoaPods)

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

[Link to the repository.](https://github.com/Carthage/Carthage)

Install [Carthage](https://github.com/Carthage/Carthage#installing-carthage) : 

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
carthage bootstrap --platform iOS
``` 

Update all : 

```
carthage update --platform iOS
```

## Vapor 

[Link to the repository.](https://github.com/vapor/vapor)

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

[Link to the repository.](https://github.com/realm/SwiftLint)

[A tool to enforce Swift style and conventions.](https://github.com/realm/SwiftLint#presentation)

Installation : 
``` 
brew install swiftlint
```

Auto correction : 
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

[Link to the repository.](https://github.com/fastlane/fastlane)

Install: 
```
brew cask install fastlane
```

Update Fastlane : 
```
fastlane update_fastlane
```

## Jazzy 

[Link to the repository.](https://github.com/realm/jazzy)

Install : 
```
sudo gem install jazzy -n /usr/local/bin
```

Generate doc for all files : 
```
jazzy --no-download-badge --min-acl private fileprivate internal
```
