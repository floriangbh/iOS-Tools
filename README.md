# Tools

Quick note for iOS development tools. 

## Cocoapods  

### Manage dependency 

Pod declaration in `Podfile` :
```
pod '<pod_name>' 
pod '<pod_name>', :git => '<repo_url>.git', :branch => '<branch_name>' #specify branch 
pod '<pod_name>', :git => '<repo_url>.git', :commit => '<commit_tag>' #specify commit 
``` 
Install pods (from `Podfile.lock`) :
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
