<h1>Docker commands</h1>
<h3>Simple command to get started with docker</h3>

1. Run a container <br>
`docker run <image>`
<br><br>
2. Run conatiner and drop to shell <br>
`docker run -it <image>` 
<br>Full form <br>
`docker run --interactive --tty <image>`
<br><br>
3. Run a container in background <br>
`docker run -d <image>`
<br><br>
4. Set container restart settings <br>
`docker run --restart (always|no|on-failure[:maxretries]|unless-stopped) <image>`
<br><br>
5. Remove a container when exited <br>
`docker run -rm <image>`
<br><br>
6. Provide container nickname <br>
`docker run --name <name> <image>`

