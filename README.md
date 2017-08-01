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

## SwiftLint  


## Fastlane  
