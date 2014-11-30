---
layout: post
title: "RubyMotion form elements"
description: ""
category: rubymotion
tags: []
image: "/img/posts/rubymotion_review/rubymotion.png"
desc: "I have elburate how can we create form element in RubyMotion"
---

In this post I have elburate how can we create form element in [RubyMotion](http://www.rubymotion.com/). These example is just a cheat code to start basic form element. For detail options refer [apple documentation](http://developer.apple.com/library/ios/navigation/) . 


###Label- UILabel
The `UILabel` class implements a read-only static text. We can create a lable to view by follwing code:

    @label = UILabel.new
    @label.text = 'Some Foo text'
    @label.frame = [[50,50],[150,50]]

To add the element to view use `addSubview` method: 

    view.addSubview(@label)


###Textbox - UITextField
A `UITextField` object will create a texbox in the view:

   
    @customTextbox = UITextField.alloc.initWithFrame([[50,50],[150,30]])
    @customTextbox.borderStyle = UITextBorderStyleRoundedRect
    @customTextbox.text = "Type.."
    @customTextbox.textAlignment = UITextAlignmentCenter
    view.addSubview(@customTextbox)



###Radiobutton Switch - UISwitch
This code will create a Switch/ Radio Button to your view :

    @switch = UISwitch.alloc.initWithFrame([[100, 100], [0, 0]])
    @switch.addTarget(self,action:'switchIsChanged', forControlEvents:UIControlEventValueChanged)

To add the Switch to view: 

    view.addSubview(@switch)  

when switch is change `switchIsChanged` will be called:   

    def switchIsChanged
    if @switch.on?
      #Some code 
    else
     #some code
    end
    end


###Slider - UISlider

A `UISlider` object is a visual control used to select a single value from a continuous range of values. Sliders are always displayed as horizontal bars.

    @customSlider = UISlider.alloc.initWithFrame([[0, 0],[200, 23]])
    @customSlider.center = view.center
   
    #Setting the minimum value of slider 
    @customSlider.minimumValue = 0
   
    #Setting the maximum value of slider 
    @customSlider.maximumValue = 1000
   
    #Setting the default value of slider 
    @customSlider.value = @customSlider.maximumValue/2 
   
    #Setting the action value of slider to sliderValueChanged 
    @customSlider.addTarget(self, action:'sliderValueChanged', forControlEvents:UIControlEventValueChanged)
    view.addSubview(@customSlider)

If slider is change `sliderValueChanged` will be called:

    def sliderValueChanged
    # do some action
    end


###Button - UIButton
`UIButton` class implements a button on the touch screen

    @normalButton = UIButton.buttonWithType(UIButtonTypeRoundedRect)
    @normalButton.frame = [[80,150],[180,37]]
    @normalButton.setTitle("Click Me", forState:UIControlStateNormal)
    @normalButton.setTitle("You have clicked me", forState:UIControlStateHighlighted)
    @normalButton.setTitle(self, action:'buttonIsPressed', forControlEvents:UIControlEventTouchDown)
    view.addSubview(@normalButton)






