---
layout: post
title:  "Karabiner, XCode and Logitech Mice: Back/Forward Buttons"
date:   2015-05-28 14:46:55 -0800
categories: workflow
---
Finally got around to understanding Karabiner’s private.xml reference guide. This was the result.

There are three items, mapping buttons 4 and 5 to the keyboard command to "go back" or "go forward" Terminal, Chrome and all other applications, and home/end keys to the keyboard commands specific for Chrome Remote Desktop.

{% highlight xml %}
<?xml version="1.0"?>
<root>
  <appdef>
    <appname>XCODE</appname>
    <equal>com.apple.dt.Xcode</equal>
  </appdef>
  <appdef>
    <appname>TERMINAL</appname>
    <equal>com.apple.Terminal</equal>
  </appdef>
  <windownamedef>
    <name>GOOGLECRD</name>
    <regex>- Chrome Remote Desktop</regex>
  </winownamedef>
  <windownamedef>
    <name>GOOGLEMAIL</name>
    <regex>Inbox</regex>
  </windownamedef>
 
  <item>
    <name>Shinko's Custom</name>
    <item>
      <name>Use Button4/Button5 as Back/Forward except XCode</name>
      <identifier>private.back_forward_with_exceptions</identifier>
      <block>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON4,
          KeyCode::BRACKET_LEFT, ModifierFlag::COMMAND_L</autogen>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON5,
          KeyCode::BRACKET_RIGHT, ModifierFlag::COMMAND_L</autogen>
        <not>XCODE</not>
        <windowname_not>GOOGLECRD</windowname_not>
      </block>
      <block>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON4,
          KeyCode::CURSOR_LEFT, ModifierFlag::COMMAND_L | ModifierFlag::CONTROL_L</autogen>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON5,
          KeyCode::CURSOR_RIGHT, ModifierFlag::COMMAND_L | ModifierFlag::CONTROL_L</autogen>
        <only>XCODE</only>
      </block>
      <block>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON4,
          KeyCode::CURSOR_LEFT, ModifierFlag::OPTION_L</autogen>
        <autogen>__PointingButtonToKey__ PointingButton::BUTTON5,
          KeyCode::CURSOR_RIGHT, ModifierFlag::OPTION_L</autogen>
        <windowname_only>GOOGLECRD</windowname_only>
      </block>
    </item>
    <item>
      <name>Replace home/end keys with command-left/command-right</name>
      <identifier>private.home_end_with_exceptions</identifier>
      <block>
        <autogen>__KeyToKey__ KeyCode::HOME, KeyCode::CURSOR_LEFT | ModifierFlag::COMMAND_L</autogen>
        <autogen>__KeyToKey__ KeyCode::END, KeyCode::CURSOR_RIGHT | ModifierFlag::COMMAND_L</autogen>
        <windowname_not>GOOGLECRD</windowname_not>
        <not>TERMINAL</not>
      </block>
    </item>
    <item>
        <name>Use cmd and ctrl synonymously in Chrome Remote Desktop</name>
        <identifier>private.cmd_ctr_synonyms</identifier>
    <autogen>__KeyToKey__ KeyCode::SPACE | ModifierFlag::COMMAND_L, KeyCode::SPACE, ModifierFlag::COMMAND_L</autogen>
        <autogen>__KeyToKey__ KeyCode::COMMAND_L, KeyCode::CONTROL_L</autogen>
    <windowname_only>GOOGLECRD</windowname_only>
    </item>
  </item>
</root>
{% endhighlight %}

