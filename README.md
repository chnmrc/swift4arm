<img src="images/SWIFT4ARM.png" alt="Swift4Arm" height="80" >

# Swift 4 Arm




All began on early 2018 and i was complaining on the fact that swift on arm32 was kinda on a holding status
 and i though its not possible we must do something before it is to late at this moment we were on the early 
swift 4.1 pre release.\
at the beginning i tried all different compile setting and i made also some comparison with a x86 linux system
but this was only wasting time.
then i tried all possible llvm/cland version and the same result.
After that i made the decision to scan completely the source code and it paid of, i learned so a lot of thinks 
my fortune was to find just at the early stage the solution for the _/proc/cpu/aligment_ problem that
gave me a lot confidence that we don’t take so long for resolving this arm32 issue
but at the end the must challenging part hast just began.
###Memory managment###
the most impostant think in this a kind of project
i started to look at all glibc versin since
2.223 and alao here scanned the malloc part of the glibc was i rhink i well done
and realy stright forfard and the same here a i learned a lot on the intwrnaly memory menagmwnt and i thougth wy we must take care of memory aligment when can deliver this to malloc
I know that here there is room for imprivement and so i leased so and i hope we found together a beat solution

then NIO come out and that got me te final motivation to keep fighting.
I know norman maurer from the java community and i thout if he does something like this it must me well done
and it is and what for a hreat opportunity fot such a kind of arm32 bit devices so a lot of ideas come in my mind.
and so finaly i come to this patch release
what ithink is not the ideal solution but the most important think we have now a working enviroment
And finally this great [announcement](https://www.apple.com/stevejobs/) i was so surprised thank you @chnmrc and always
thank you [steve](https://www.apple.com/stevejobs/)




<sub><sup> <chnmrc> Marco Chini</sup></sub>














