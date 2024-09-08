[![Build](https://github.com/swhitty/swift-timeout/actions/workflows/build.yml/badge.svg)](https://github.com/swhitty/swift-timeout/actions/workflows/build.yml)
[![Codecov](https://codecov.io/gh/swhitty/swift-timeout/graphs/badge.svg)](https://codecov.io/gh/swhitty/swift-timeout)
[![Platforms](https://img.shields.io/badge/platforms-iOS%20|%20Mac%20|%20tvOS%20|%20Linux%20|%20Windows-lightgray.svg)](https://github.com/swhitty/swift-timeout/blob/main/Package.swift)
[![Swift 6.0](https://img.shields.io/badge/swift-5.10%20–%206.0-red.svg?style=flat)](https://developer.apple.com/swift)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://opensource.org/licenses/MIT)
[![Twitter](https://img.shields.io/badge/twitter-@simonwhitty-blue.svg)](http://twitter.com/simonwhitty)

# Introduction

**swift-timeout** is a lightweight wrapper around [`Task`](https://developer.apple.com/documentation/swift/task) that executes a closure with a given timeout.

# Installation

Timeout can be installed by using Swift Package Manager.

 **Note:** Timeout requires Swift 5.10 on Xcode 15.4+. It runs on iOS 13+, tvOS 13+, macOS 10.15+, Linux and Windows.
To install using Swift Package Manager, add this to the `dependencies:` section in your Package.swift file:

```swift
.package(url: "https://github.com/swhitty/swift-timeout.git", .upToNextMajor(from: "0.2.0"))
```

# Usage

Usage is similar to using structured concurrency:

```swift
import Timeout

let val = try await withThrowingTimeout(seconds: 1.5) {
  try await perform()
}
```

If the timeout expires before a value is returned the task is cancelled and `TimeoutError` is thrown.

# Credits

Timeout is primarily the work of [Simon Whitty](https://github.com/swhitty).

([Full list of contributors](https://github.com/swhitty/swift-timeout/graphs/contributors))
