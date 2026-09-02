<h1><b>the purpose of this project</b></h1>
The purpose of this project is to find a way to make Apple's TouchID they use on their macbook and magic keyboards work on linux by any means neccesary until Apple sends me a cease or desist or I get bored of this project,
in that case, I might transfer this repo to another user who does want to continue the project if possible (kinda new to github).
Any help toward the goal is welcome, donations, hardware (keyboards, Apple Silicon macs specifically), hardware, software, firmware (eg. for the mac's Secure Enclave thing and/or the keyboard), direct help, therapy, education on the subject of coding
and possibly contact/support with/from the big LT (Linus Torvalds) himself or any other company, foundation, organization or person within the linux space (NOT microsoft)

<h1><b>The use of LLM's for this project by me</b></h1>
I will use an LLM for most of the code I make for this project as I have (for now) zero understanding of any coding language, the reason I'm able to do the headers in this README is because I once picked it up while watching a YouTube video.
Once I learn how to code though, I will try to create as much code for this project myself as possible, the LLM is just a way of kickstarting this project.

<h1><b>Todo</b></h1>


- (optional) get a response from Apple/Amac on the E-mail I sent them asking for help with this project.
- get a hold of (someone who has) a mac and capture the USB traffic during the pairing of the keyboard with a mac to better understand the process
- find out how to simulate or bypass the need for a Secure Enclave unit

<details>
  <summary><b><i>A little thing in between</i></b></summary>
  <h3>what do I think happens during the pairing and scanning process of an Apple Magic Keyboard with a TouchID sensor</h3>
1. keyboard connects for the first time to a mac(book)<br>
2. message shows up on mac(book), "Magic keyboard detected, set up TouchID?"<br>
3. user clicks the message<br>
4. MacOS 11.4+ on an Apple Silicon Mac prompts the scanner to turn on in some way, probably through an HID command or something ((probably)obviously)<br>
5. Scanner responds with a request for a unique security key of some sort unique to that mac<br>
6. Mac sends the unique security code of it's Secure Enclave or something<br>
7. Scanner and Mac go "seems alright to me!"<br>
8. Mac displays on screen "tap finger on the scanner to begin"<br>
9. User rotates their fingertip in all sorts of grotesque ways<br>
10. TouchID sensor sends the scanned fingerprint data to the Secure Enclave chip (or whatever it is(probably)) where it is encrypted a billion times over and stored for the rest of eternity<br>
11. (probably) Mac sends command to the sensor, signaling the scan is complete and the sensor to turn off (or the other way around)<br>
<b><i>that was the end of this little thing in between</i></b>

</details>
<h3><i>The following points are only for a scenario where a Secure Enclave unit is required for TouchID to work.</i></h3>

- try to pull the thing's firmware and do a bit more research <i><b>yum</b></i>
- find out if we can talk to the keyboard's TouchID sensor at all and see if it goes <i>nuh</i> without a SEU
<details>
<summary><b><i>SEU</i></b></summary>
  <i>Secure Enclave Unit</i><br>
  <sup>I got tired of typing the whole thing each time, I might still type it in full after this point because <i>am dum</i>.</sup>
</details>

- attempt at creating a simulated SEU as a kernel driver/module or a serive that starts during boot <br>
- test the simulated SEU and see if it works by sending eg. the same HID command (if that's what MacOS used) MacOS used to initialize the sensor's/keyboard's pairing mode and see if we get a response back from the sensor<br>
of it confirming it's in pairing mode<br>
- desperately find out how to get the keyboard/sensor out of pairing mode <sup><i>oh shittings</i></sup><br>
- celebrate the fact I don't have a massive 179,00 euro paperweight (worst case scenario)<br>
- try to make a prototype for the scanning process and test the functionality by just having a terminal session open which displays stuff like "got finger"<br>
- scan finger and pray to anything you can think of to make it work (if not fix issues)<br>
- (best case scenario) you win a billion dollars and a nobel prize because the scan was successful (in this case, the money will be distributed among the people who've committed to this repo with the person who did the most obviously getting the most money)<br>
- (worst case scenario) Apple Strike Team raids your house because you're a moron and the scan failed<br>
<h3>this was the end of the bit if a SEU is required for TouchID to work</h3><br>
<h3>the following are dedicated to a scenario where the SEU isn't required</h3><br>

- find out how to talk to the sensor<br>
- talk to the sensor<br>
- try to see if fprint(something) recognises it immediately (probably not).<br>
- (if fprint(something) doesn't immediately recognise the sensor) find out why it doesn't and hit it until the very sparks cry for mercy.<br>
- fingerprint scans correctly because people on github are absolute geniuses<br>
- celebrate<br>

<h3>this was my (probably extremely optimistic) idea of how this project will likely go (don't worry if you don't understand anything you just read, I don't either.)</h3><br>

<h1>when to stop with project</h1><br>

- if Apple sends a cease and desist to me<br>
- if the project succeeds<br>
- heat-death of the universe<br>

<h1>notes for Apple</h1><br>

- We're not trying to compromise your incredible security<br>
- We're not trying to hack any information<br>
- your security system <i><b>might</b></i> <i>accidentally</i> be open-sourced<br>
