<h1 align="center">VRMKit</h1>

<h5 align="center">VRM loader and VRM renderer</h5>

<div align="center">
  <a href="https://github.com/Carthage/Carthage">
    <img src="https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat" alt="Carthage compatible" />
  </a>
  <a href="https://developer.apple.com/swift">
    <img src="https://img.shields.io/badge/Swift-4-F16D39.svg" alt="Swift Version" />
  </a>
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-green.svg?style=flat-square" alt="license:MIT" />
  </a>
</div>

<br />

<img src="https://github.com/tattn/VRMKit/raw/master/docs/demo.jpg" width="300px" alt="demo" />

## Features

- [x] Load VRM file
- [x] Render VRM models on SceneKit (experimental)

# Requirements

- Xcode 9.x
- Swift 4.x
- iOS 10.0+

# Installation

## Carthage

```ruby
github "tattn/VRMKit"
```

## CocoaPods

```ruby
pod 'VRMKit'
pod 'VRMSceneKit' # for rendering
```

# Usage

## Load VRM

```swift
import VRMKit

let vrm = try VRMLoader().load(named: "model.vrm")
// let vrm = try VRMLoader().load(withUrl: URL(string: "/path/to/model.vrm"))
// let vrm = try VRMLoader().load(withData: data)

// VRM meta data
vrm.meta.title
vrm.meta.author

// model data
vrm.gltf.jsonData.nodes[0].name
```

## Render VRM

```swift
import VRMKit
import VRMSceneKit

@IBOutlet weak var sceneView: SCNView!

let loader = try VRMSceneLoader(named: "model.vrm")
let scene: VRMScene = try loader.loadScene()

sceneView.scene = scene
```


# Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D


# ToDo
- [ ] CocoaPods support
- [ ] VRM shaders support
- [ ] Improve rendering quality
- [ ] Animation support
- [ ] VRM editing function


# License

VRMKit is released under the MIT license. See LICENSE for details.

