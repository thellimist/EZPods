#### Pod Creation

##### - Open Repo

1. Create [new repo](https://github.com/new) (My advice first add pods on a temporary repo before adding to your original project)
2. Fill Repository name with your repo name. I'll use "myrepo" for this tutorial and will use "<" and ">" symbols for the parts you should change to your own.
3. Click "Initialize this repository with a README"
5. Add a license. I'll use "MIT" for this tutorial.

##### - Pull Your Repo to Local

1. Open Terminal. 
2. Go where your repo is `cd </your/path/<myrepo>` or create it with `cd </your/path>`. `mkdir <myrepo>`. `cd <myrepo>`
3. Add git to your folder with `git init` 
4. Link your repo with `git remote add origin https://github.com/<username>/<myrepo>.git`. (You can check if its working with `git remote -v` (Not git remove -v))
5. Pull your repo from github with `git pull`
6. Type: git pull origin master
7. Type git commit

##### - Add Cocoapods

1. Install cocoapods: `sudo gem install cocoapods`. Write `pod --help` to check if it's working. (Skip if you already have cocoapods)
2. Create `<myrepo>.podspec` with `touch <myrepo>.podspec`
3. Open `<myrepo>.podspec` with an editor. Use Xcode or Sublime Text.
4. Paste the following. You can checkout this [example](https://github.com/thellimist/SwiftRandom/blob/master/SwiftRandom.podspec). For details check the [documentation](https://guides.cocoapods.org/syntax/podspec.html#specification)
  ```
  Pod::Spec.new do |s|
  s.name             = "<myrepo>"
  s.version          = "0.1"
  s.summary          = "<My summary>"
  s.description      = "<MUST BE LONGER THAN SUMMARY>"
  s.homepage         = "https://github.com/<username>/<myrepo>"
  s.license          = 'MIT'
  s.author           = { "<username>" => "<useremail>" }
  s.source           = { :git => "https://github.com/<username>/<myrepo>.git", :tag => s.version.to_s }
  s.platform     = :ios, '8.0'
  s.requires_arc = true
  
  # If more than one source file: https://guides.cocoapods.org/syntax/podspec.html#source_files
  s.source_files = '<myrepo>.swift' 
  
  end
  ```
4. Write `pod lib lint <myrepo>.podspec` to the terminal. If you have any errors write `pod lib lint <myrepo>.podspec --verbose`. Solve your errors (solving your errors could take some time can't help here). 
5. Add newly changes to git with `git add .` then commit with `git commit -m "Added pods"`
6. Push your changes to your remote repo with `git push`
7. Create new release https://github.com/<username>/<myrepo> Click Releases -> Click New Version
8. Write "0.1" to Tag Version. (Optional you can fill the "Release Title"). Make sure the version is identical with the `s.version` inside `<myrepo>.podspec`
9. Write `pod trunk register name@example.org 'Your Name' --description='macbook pro'`
10. After your new release open terminal and write `pod trunk push <myrepo>.podspec`. This will change the [CocoaPods Specs](https://github.com/CocoaPods/Specs) which will enable you to write `pod  '<myrepo>'` inside your `podfile`
