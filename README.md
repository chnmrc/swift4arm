<img src="images/SWIFT4ARM.png" alt="Swift4Arm" height="80" >

# Swift 4 Arm
> 1. ## Integration Major Problem ##
> 2. ## Brief Introduction ##
> 3. ## Memory managment ##
> 4. ## Patch Procedure ##
> 5. ## Download binary ##

</br></br>


## Integration Major Problem
>	* Problem on: __/proc/cpu/alignment__ 
>	* Memory Managment
>	* ARCH build support

## Brief Introduction ##
All began on early 2018 and i was complaining on the fact that swift on arm32 was kind on a frozen status.</br></br>
And i thought it's not possible we must do something before it is to late, at this moment we were on the early 
swift 4.1 pre release and then swift on arm32 was exactly one major release behind.</br></br>
At the beginning i tried all different compile setting and i made also some comparison with a x86 linux system
but this was only wasting time. </br></br>
Then i tried all possible llvm/clang version and the same result.</br></br>
After that i made the decision to scan completely the source code and it paid off.</br></br>
I found just at the early stage the solution for the _/proc/cpu/alignment_ problem that
gave me a lot confidence that we don’t take so long for resolving this arm32 issue
but at the end the must challenging part has to come. </br></br>
## Memory managment ##
An important topic in this a kind of project.</br>
I started to look at the glibc in particular on the malloc.c and here i tried different version but since glibc in the last releases
is very solid i switched back to version 2.23.<br/> 
My feeling is that malloc is very robust. <br/>
After this i made the decision to let malloc to do the alignment.
Then NIO come out and that got me the final motivation to keep fighting. <br/>
I know [**Norman Maurer**](https://github.com/normanmaurer) from the java community, and i thought if he does something like this it must be well done and it is.</br>
And what for a great opportunity for such a kind of arm32  devices so a lot of ideas comes in my mind
like a **NIO** based scalable MQTT broker.<br/> Here i want to thank's both of  [**@normanmaurer**](https://github.com/normanmaurer) and
[**@helge**](https://github.com/helje5) for the quick integration of arm32 on **NIO**. <br/> <bt/>
At the end i come to this patch release what i think is not the ideal solution but the most important thing is we have now a working environment to work on.<br/>
And finally this great [announcement](https://swift.org/blog/swift-community-hosted-ci/) i was so surprised thank you [**apple**](https://github.com/apple) and always thank you [steve](https://www.apple.com/stevejobs/)

## Patch Procedure ##

* Follow also the Instruction of  [**@uraimo**](https://github.com/uraimo/buildSwiftOnARM) on his github repository but without his patch procedure
* git checkout  __git clone https://github.com/apple/swift__
* git checkout of all depency swift packages __./swift/utils/update-checkout --clone__
* git checkout __swift-4.1-RELEASE__ branch on all modules 
* apply the patch on the starting directory -> **patch -p4 < swift4arm.patch**
* Now you are ready for the building procedure
* For a Docker installation i advice to follow the work of [**@helge**](https://github.com/helje5)
* For __Swift on arm64__  follow the work of [**@futurejones**](https://github.com/futurejones) 
* For further question please contact the [**swift arm slack group**](https://swift-arm.slack.com/)


## Download binary ##
Here you can download the [**complete binary tar**](http://mchini.com/swift/swift-4.1-RELEASE-ARMv7.tgz). <br/>
I tested it against several projects : [**Kitura**](https://github.com/IBM-Swift/Kitura), [**SwiftNIO**](https://github.com/apple/swift-nio) etc.
feel free to report any issue.

<br/>
<br/>

> For any challenging project swift related feel free to [**contact me**](http://mchini.com) <info@mchini.com>.

<br/>
<br/>

<sub><sup> <chnmrc>[**Marco Chini**](http://mchini.com)  <info@mchini.com></sup></sub>














