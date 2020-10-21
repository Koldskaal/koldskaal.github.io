---
layout: post
title: Fixing WSL not starting.
---

So here I was trying to solve a problem for myself. Bash on widows was not starting it was just hanging with nothing.



I should have taken a picture. 



First I went to [superuser.com](https://superuser.com/questions/1275505/wsl-bash-doesnt-start) and found following tip. 



> Try to do a **FULL reboot** of Windows10, hold SHIFT and click reboot.
> 
> Normal reboot/shutdown action in the start menu will not shutdown win10 fully, for the "fast boot" mechanism saves memory from the last session. The other answer mentioned changing system settings which makes win10 doing a full reboot, it works, but unnecessary.
> 
> By holding SHIFT key and click the Shutdown/Reboot in start menu, win10 will go into maintain mode, choose Shutdown from the menu. Then start normally again.

I tried and it worked! So I let it go.



But the day after the error came back and the following day yet again and I realized that this wasn't a good solution for me. Having to reboot your computer before you start working is a pain and completely ruins my productivity. I start procrastinating immediately. The extra step of restarting my computer completely ruins my flow and my motivation. So I started searching more thoroughly.



Below the first answer there was a link to another thread on github where I found this [comment](https://github.com/Microsoft/WSL/issues/849#issuecomment-252053937).



> **I found my solution**, in another thread involving "multiple pagefiles" which is now marked "closed with workaround." Sorry I can't recall which number it is.
> 
> It was the solution to the exact problem of bash.exe hanging, AptPackageIndexUpdate window appearing and freezing, etc., at least for me.
> 
> I had changed to a C-drive pagefile of 800-1024, and in addition a system-managed size for drive D:, E:, and F:, which are all 1.8TB drives (C: is 512GB SSD). I had then tried all uninstalls, reinstalls, etc., thinking nothing of changing the pagefiles. I had suspected the usual: latest windows update, AVG antivirus hook DLL, etc.
> 
> Reading through the other issue, they suggested having only one pagefile as a workaround. I simply reconfigured the pagefiles to one only on C: (system managed) and "None" on the other three. Reboot, then bash.exe immediately shows me the Linux prompt.
> 
> Great day, thanks!
> 
> Alex



So I did as he said and lo and behold it seems to work. Now I hope it is gone for good otherwise I'll have to keep searching. What a pain.
