# Day 19: Creating an Attack Diagram
## Objective
The objective of this section is to create an attack diagram that maps out our plan of attack.

## Steps
Our attack plan is as follows:

### Phase 1: Initial Access
- We'll RDP brute force into the Windows server.
- After successfully authenticating, we'll begin phase 2.

### Phase 2: Discovery
- In phase 2, we'll begin to discover more about the network and the machine we've compromised using commands such as `whoami`, `ipconfig`, `net user`, and `net group`.

### Phase 3: Defense Evasion
- In phase 3, we'll use our connection to prepare our execution by disabling Windows Defender on the Windows server.

### Phase 4: Execution
- In phase 4, we'll begin the execution.
- From the Windows server, we'll run a [PowerShell IEX](https://www.securonix.com/blog/hiding-the-powershell-execution-flow/) (invoke expression) command to obfuscate our malicious activity. We'll send this command to our Mythic C2 server.
- The command will install the Mythic Agent onto the Windows server. This is why we wanted to disable Windows Defender, among other reasons. Windows Defender might be able to detect the Mythic Agent, and we don't want that.
- The Windows server will then execute the Mythic agent, and now we have a connection established.

### Phase 5: Command & Control
- With a successfully established C2 session, we'll now be able to exfiltrate the data we want.

### Phase 6: Exfiltration
- During the exfiltration phase, we'll download the passwords.txt file and exfiltrate that data.

<p align="center"><img src="https://i.imgur.com/HAW643T.png"></p>
<p align="center"><i>Ref 1: Our attack plan.</i><p>
<br>
