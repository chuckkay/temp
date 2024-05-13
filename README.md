 **Facefusion QueueItUp 2.5.3 for sd-webui**
 Automatic 1111
![Screenshot 2024-04-09 174800](https://github.com/chuckkay/QueueItUp/assets/10617746/65cd8c2f-1192-4bde-a3e6-39540cee42bc)



![Screenshot 2024-04-15 063227](https://github.com/chuckkay/QueueItUp/assets/10617746/971e2bd3-df87-412e-998a-9e93b7d19f63)

This is it—at least until Henry releases the official queueing feature for Facefusion. I'm not a coder, but I think I did a pretty good job creating this simple one-file drop-in addon to fill the void until the official features are added.
**How to Install:**
put this in your automatic1111 extensions install from url tab
https://github.com/chuckkay/Facefusion-QueueItUp-sd-webui.git
click install
restart when done...
enjoy

**Features of QueueItUp:**
- **Job Queueing:** Below the normal start button in the Facefusion web UI, you will find a queue status box and three buttons: ADD JOB, RUN QUEUE, and EDIT QUEUE. They do exactly what they say. Although the ADD JOB and RUN QUEUE might seem redundant and could be removed in future versions, they currently serve a purpose. Once you've added some jobs and clicked RUN QUEUE, it will start processing all the swaps in order, but you're not stuck waiting. Build more jobs, and when you click ADD JOB, if the queue is still processing other jobs, any additional jobs will be added to the back of the queue and will execute when their turn comes. This was a huge addition I made, as I could launch a bunch of jobs, work on some more, add them to the back of the line and go to bed. In the morning, they are all done—LOL.
- **Edit Queue:** If you want to change a job's position in the queue or quickly change a source or target image, just click on the image button, and a file dialog will pop up allowing you to select a replacement source or target. This is a convenient tool, and you will soon discover it has a bunch of other benefits. Changing a target video isn't out of the question, but due to the complexity of face finding in videos and other needed tweaks, I wouldn't recommend it for all scenarios. It will work but just using the previous settings... wait, did I say settings? I meant arguments. And what about those amazing things—who can remember what to type when you manually try to change one? Well, now you don't have to! No need to open JSONs and poke around (although feel free), but wouldn’t it be so much better if you could go back in time to change that one setting you wish you had changed? Well, get ready for EDIT ARGUMENTS, the latest "hack" I added to QueueItUp 2.5.3. In the edit queue window, just click on the button that shows your command-line arguments, and like magic, the job will be loaded back into Facefusion's Web UI where you can re-edit every aspect, and when done, add it back to the queue or even run it with the standard start button. But don't try clicking start if something's already running, unless you've got two RTX 4090s in your arsenal.
- 
**Quirks:**
1. Gradio oh Gradio... So, have you noticed Gradio doesn’t actually use your source or target files? It copies them to a `user\temp\gradio` directory with an undecipherable hash, maybe for security, I don’t know... But!!! How can you use a queuing program when you don't have the original source paths or target paths, only some temp folder? And what happens if you don’t have time to finish all the items in your queue? Oh wait, I just realized this belongs in the features section. That's right, you can crash, abort, unplug, do whatever—QueueItUp 2.5.3 has your back and can resume from the last job! Awesome... But this wouldn’t be possible if QueueItUp relied on Gradio’s temp directory which periodically gets wiped clean by other programs like Automatic 1111 and even Facefusion... So goodbye source and targets, and although you can fix that in Edit Queue by finding the files again if you remember where they are. But you don’t have to, BECAUSE QueueItUp 2.5.3 one-ups Gradio and makes its own media cache directory the second Gradio absconds with your media. QueueItUp 2. 5.2 steals it right back and stores it for safekeeping and tracking where every job has a record of which files to use, and even when jobs are completed which cache files to delete, so long as there are no other pending jobs that might need that specific file. Nice, right? I thought so—a nice and tidy media cache directory that only cleans out the cache when there are no jobs that need it.

Speaking of cache, yes, please feel free to donate... and enjoy QueueItUp 2.5.3! 😊
