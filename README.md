# Routing

[![Build Status](https://travis-ci.org/jwalapr/Routing.svg?branch=master)](https://travis-ci.org/jwalapr/Routing)
[![Code coverage status](https://img.shields.io/codecov/c/github/jwalapr/Routing.svg?style=flat-square)](http://codecov.io/github/jwalapr/Routing)
[![Platform support](https://img.shields.io/badge/platform-ios-lightgrey.svg?style=flat-square)](https://github.com/ReSwift/ReSwift/blob/master/LICENSE.md) 
[![Carthage Compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)
[![License MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/ReSwift/ReSwift/blob/master/LICENSE.md)

# Table of Contents

- [About Routing](#about-routing)
- [Installation](#installation)
- [Testing](#testing)
- [Example](#example)
- [Collaboration](#collaboration)

# About Routing

Routing allows for mapping string patterns to an associated closure.

To map a route with a string pattern which will be executed in the event it is opened via <em>Routing().open(URL:)</em>. If two patterns match an opened URL, only the last closure to be mapped with be executed.

```swift
let router = Routing()
router.map("/route") { (parameters, completed) in
	...
	completed() // Must call completed or the router will halt!
}
```

To proxy a route with a string pattern which will be executed in the event it is opened via <em>Routing().open(URL:)</em>. Any number of proxies may be executed in the event of a matching pattern. Passing a non nil argument to <em>next(String?, Parameters?)</em> will discontinue any further proxies from being executed.

```swift
router.proxy("/route") { (var route, var parameters, next) in
	...
	next(route, parameters) // Must call next or the router will halt!
	// next(nil, nil) // Passing nil arguments will allow the next proxy to execute
}
```

To open a URL.

```swift
router.open(NSURL(string: "host://route/")!) // Will return true or false if there is an associated route
```



# Installation

# Testing

# Example

# Collaboration

