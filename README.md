# Transition Demo

=========

## Transition Demo in Swift 5.

------------
Added Some screens here.

![](https://github.com/pawankv89/Transition-Demo/blob/master/images/screen_1.png)
![](https://github.com/pawankv89/Transition-Demo/blob/master/images/screen_2.png)

## Usage
------------

####  Transition Demo

```swift


import UIKit

class ViewController: UIViewController {

@IBOutlet weak var counterView: UIView!
@IBOutlet weak var counterPlusButton: UIButton!
@IBOutlet weak var counterMinusButton: UIButton!
@IBOutlet weak var counterLabel: UILabel!
var counter = 0

override func viewDidLoad() {
super.viewDidLoad()
// Do any additional setup after loading the view.

counterLabel.text = "0"

}

@IBAction func counterPlusButtonTap(_ sender: UIButton) {

counterLabel.layer.bottomAnimation(duration: 0.7)
counter = counter + 1
counterLabel.text = "\(counter)"
}

@IBAction func counterMinusButtonTap(_ sender: UIButton) {

if counter > 0 {
counterLabel.layer.topAnimation(duration: 0.7)
counter = counter - 1
counterLabel.text = "\(counter)"
}
}

}


//MARK:- Workng on Swift 5
extension CALayer {

func bottomAnimation(duration:CFTimeInterval) {
let animation = CATransition()
animation.timingFunction = CAMediaTimingFunction(name: CAMediaTimingFunctionName.easeInEaseOut)
animation.duration = duration
animation.type = CATransitionType.push
animation.subtype = CATransitionSubtype.fromTop
self.add(animation, forKey: CATransitionType.push.rawValue)
}

func topAnimation(duration:CFTimeInterval) {
let animation = CATransition()
animation.timingFunction = CAMediaTimingFunction(name: CAMediaTimingFunctionName.easeInEaseOut)
animation.duration = duration
animation.type = CATransitionType.push
animation.subtype = CATransitionSubtype.fromBottom
self.add(animation, forKey: CATransitionType.push.rawValue)
}
}

/*
//MARK:- Working on Swift 4
extension CALayer {

func bottomAnimation(duration:CFTimeInterval) {
let animation = CATransition()
animation.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionEaseInEaseOut)
animation.duration = duration
animation.type = kCATransitionPush
animation.subtype = kCATransitionFromTop
self.add(animation, forKey: kCATransitionPush)
}

func topAnimation(duration:CFTimeInterval) {
let animation = CATransition()
animation.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionEaseInEaseOut)
animation.duration = duration
animation.type = kCATransitionPush
animation.subtype = kCATransitionFromBottom
self.add(animation, forKey: kCATransitionPush)
}
}
*/


```




## License

This code is distributed under the terms and conditions of the [MIT license](LICENSE).

## Change-log

A brief summary of each this release can be found in the [CHANGELOG](CHANGELOG.mdown). 
