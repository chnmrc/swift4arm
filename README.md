<img src="images/SWIFT4ARM.png" alt="Swift4Arm" height="80" >

# Swift 4 Arm
> 1. ## Integration Major Problem ##
> 2. ## Brief Introduction ##
> 3. ## Memory managment ##
> 4. ## Patch Procedure ##

</br></br>


## Integration Major Problem
>	* Problem on: __/proc/cpu/aligment__ 
>	* Memory Managment
>	* ARCH build support

## Brief Introduction ##
All began on early 2018 and i was complaining on the fact that swift on arm32 was kinda on a holding status.</br></br>
And i though it's not possible we must do something before it is to late, at this moment we were on the early 
swift 4.1 pre release.</br></br>
At the beginning i tried all different compile setting and i made also some comparison with a x86 linux system
but this was only wasting time. </br></br>
Then i tried all possible llvm/cland version and the same result.</br></br>
After that i made the decision to scan completely the source code and it paid of, i learned so a lot of thinks 
my fortune was to find just at the early stage the solution for the _/proc/cpu/aligment_ problem that
gave me a lot confidence that we don’t take so long for resolving this arm32 issue
but at the end the must challenging part hast just began. </br></br>
## Memory managment ##
An impostant topic in this a kind of project.</br>
I started to look at the glibc  since
2.23 version and also here scanned the malloc part of the glibc was i rhink i well done
and realy stright forward and the same here a i learned a lot on the internaly memory menagment and i thougth why we must take care of memory alignment when we can deliver this to malloc
I know that here there is room for improvement and so i leased so and i hope we found together a beat solution

Then NIO come out and that got me the final motivation to keep fighting. <br/>
I know [**Norman Maurer**](https://github.com/normanmaurer) from the java community, and i thought if he does something like this it must be well done
and it is.</br> 
And what for a great opportunity for such a kind of arm32  devices so a lot of ideas comes in my mind
like a **NIO** based scalable MQTT broker.<br/>. Here i want to thank's both of  [**Norman Maurer**](https://github.com/normanmaurer) and
[**@helge**](https://github.com/helje5) for the quick integration of arm32 on **NIO**. <br/>
At the end i come to this patch release
what i think is not the ideal solution but the most important think we have now a working environment to work on.<br/>.
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

<br/>
<br/>
**_Post Scriptum_**
<br/>
<br/>
* Many Thanks to [**@hpux735**](https://github.com/hpux735) for the great support. <br/>
* And also to [@joe](http://dev.iachieved.it/iachievedit/) for initiating all this.


<br/>
<br/>

> For any challenging project swift related fell free to [**contact me**](http://mchini.com) <info@mchini.com>.

<br/>
<br/>

<sub><sup> <chnmrc>[**Marco Chini**](http://mchini.com)  <info@mchini.com></sup></sub>














