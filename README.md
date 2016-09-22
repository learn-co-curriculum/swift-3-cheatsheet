# Swift 3 

![](http://img.deusm.com/informationweek/2015/09/1322066/Swift_logo.png)

## Function name changes


```
names.indexOf("Taylor")   //Swift 2.3
names.index(of: "Taylor") //Swift 3
```
```
"Taylor".writeToFile("filename", atomically: true, encoding: NSUTF8StringEncoding)
"Taylor".write(toFile: "somefile", atomically: true, encoding: String.Encoding.utf8)
```
```
SKAction.rotateByAngle(CGFloat(M_PI_2), duration: 10)
SKAction.rotate(byAngle: CGFloat(M_PI_2), duration: 10)
```
```
UIFont.preferredFontForTextStyle(UIFontTextStyleSubheadline)
UIFont.preferredFont(forTextStyle: UIFontTextStyle.subheadline)
```
```
override func numberOfSectionsInTableView(tableView: UITableView) -> Int
override func numberOfSections(in tableView: UITableView) -> Int
```
```
func viewForZoomingInScrollView(scrollView: UIScrollView) -> UIView?
func viewForZooming(in scrollView: UIScrollView) -> UIView?
```
```
NSTimer.scheduledTimerWithTimeInterval(0.35, target: self, selector: #selector(createEnemy), userInfo: nil, repeats: true)
Timer.scheduledTimer(timeInterval: 0.35, target: self, selector: #selector(createEnemy), userInfo: nil, repeats: true)
```

## Verbs vs Nouns

Swift 3  divides methods into two categories:

1. Methods that return a certain value - think of them as nouns
2. Methods that return a certain kind of action - think of them as nouns

Swift 2.3

```

for i in (1...10).reverse() {
  print(i)
}

```

Swift 3

Swift 3 treats this operation as a noun since it returns the original range in reverse order.

```

for i in (1...10).reversed() {
  print(i)
}

```

Swift 2.3

```
var array = [1, 5, 3, 2, 4]
for (index, value) in array.enumerate() {
  print("\(index + 1) \(value)")
}

```

Swift 3

```
var array = [1, 5, 3, 2, 4]
for (index, value) in array.enumerated() {
  print("\(index + 1) \(value)")
}



```

## ++ and -- 

Swift 2.3

```

i++
i--

```
Swift 3

```

i += 1
i -= 1

```

## Pi

Swift 2.3

```
let r =  3.0
let circumference = 2 * M_PI * r
let area = M_PI * r * r
```
Swift 3

```
//Float.pi
//Double.pi
//CGFloat.pi

let r = 3.0
let circumference = 2 * Double.pi * r
let area = Double.pi * r * r

//With type inference we can even do this 

let r = 3.0
let circumference = 2 * .pi * r
let area = .pi * r * r

```
#Simpler APIs

``XCPlaygroundPage.currentPage`` becomes ``PlaygroundPage.current``

``button.setTitle(forState)``becomes ``button.setTitle(for)``

``button.addTarget(action, forControlEvents)`` becomes ``button.addTarget(action, for)``

``NSBundle.mainBundle()`` becomes ``Bundle.main()``

``NSData(contentsOfURL)`` becomes ``URL(contentsOf)``

``NSJSONSerialization.JSONObjectWithData()`` becomes ``JSONSerialization.jsonObject(with)``


## Grand Central Dispatch

Swift 2.3

```
let queue = dispatch_queue_create("Swift 2.2", nil)
dispatch_async(queue) {
  print("Swift 2.2 queue")
}
```

Swift 3

```
let queue = DispatchQueue(label: "Swift 3")
queue.async {
  print("Swift 3 queue")
}

```






