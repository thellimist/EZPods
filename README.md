# EZPods
Easy CocoaPods checklist and tutorial

This method is not recommended for maintaining large repos. This method is adviced for small repo's like [SwiftRandom](https://github.com/thellimist/SwiftRandom), [EZAlertController](https://github.com/thellimist/EZAlertController).

- If this is your first time adding cocoapods check out [Steps In Detail](https://github.com/thellimist/EZPods#steps-in-detail).
- If you are familiar with pods check out the [Pods Creation CheckList](https://github.com/thellimist/EZPods#checklist)
- If you want to update a already added pod checkout [Pods Update CheckList](https://github.com/thellimist/EZPods#pods-update-checklist)

### Pods Creation 

#### CheckList

1. [New Repo](https://github.com/new)
2. "Initialize this repository with a README"
3. License "MIT"
4. `cd /your/path` & `mkdir MyRepo` & `cd MyRepo`
5. `git init` & `git remote add origin https://github.com/<username>/MyRepo.git` & `git pull`
6. `touch myrepo.podspec` & [example podspec](https://github.com/thellimist/SwiftRandom/blob/master/SwiftRandom.podspec)
7.  `pod lib lint MyRepo.podspec`. For errors `pod lib lint MyRepo.podspec --verbose`
8.  `git add .` & `git commit -m "Added pods"` & `git push`
9.  Create new [release](https://github.com/<username>/MyRepo/releases/new)
10. `pod trunk push MyRepo.podspec`

#### Steps In Detail

[Check here](https://github.com/thellimist/EZPods/blob/master/Pod%20Creation.md)

### Pods Update CheckList

1. Update your project with `git pull origin master
`
2. Update `s.version` inside `MyRepo.podspec`
3. Check local errors with `pod lib lint MyRepo.podspec`
4. `git add .` & `git commit -m "Update pods version"`
5. `git push`
6. Make a new [release](`https://github.com/<username>/MyRepo/releases)
7. `pod trunk push MyRepo.podspec`

  

  

  

