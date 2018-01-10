# iOS

## 依赖管理

1. [Cocoapods](./Cocoapods.md)

2. Carthage

3. Swift Packge

## 构建的自动化工具

1. xcodebuild

2. fir

3. fastlane
 
## unlock-keychain shell script

``` 
#!/bin/bash

export GEM_HOME=$HOME/.rvm/gems/ruby-x.x.x
export PATH=$PATH:/usr/local/bin:$GEM_HOME/bin
echo $PATH

keychain=$HOME/Library/Keychains/login.keychain
security unlock-keychain -p "xxxxxx" ${keychain} &>/dev/null
if [ $? -ne 0 ];then
    echo "Cannot open keychain ${keychain}"
    exit 1
fi

fir build_ipa ...
```