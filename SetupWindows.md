## Le Wagon Ruby Workshop setup - Windows

### Step 1: Download Sublime Text
Download and install [Sublime Text](https://www.sublimetext.com/3).

This is the text editor where you'll be writing your code.

### Step 2: Download Docker Toolbox
Download and install [Docker Toolbox](https://www.docker.com/products/docker-toolbox) here. Just leave the default boxes ticked and click next until the installation process begins.

As writing in Ruby on Windows poses many problems, we will use a virtualization tool to simulate a Linux developer environment. Docker will handle that for us.

### Step 3: Start Docker Terminal
Run the docker quickstart Terminal, there should be a shortcut on your Desktop. It will install and download the additional modules that are necessary. Accept the prompts asking about Virtualbox modules.

The Docker Quickstart Terminal is where you'll be able to write commands and run Ruby code just like you could if you had a Linux or Mac machine.

<span style="color: #d23333">*If you get an error here, you need to enable CPU Virtualization. It's a lot less scary than it sounds, just ask a teacher.*</span>

### Step 4: Create folder and download challenges
Copy paste these lines one at a time into your Docker Terminal, pressing enter after pasting each one:
```bash
  cd ~/code
  git clone https://github.com/atmosfeer/lewagon-weekend-workshop.git
```

This step is pretty simple. We create new empty folders on your computer and download the challenges of the workshop into them using git.

### Step 5: Run Docker Container
Copy paste this long line to start the Ruby Virtual Environment. You're all set to start coding now.

`docker run -it -v ~/code/lewagon-weekend-workshop:/home/code/lewagon-weekend-workshop atmosfeer/lewagonsetup:latest /bin/zsh`

From now on, all you need to do is to run this last line from the Docker Quickstart Terminal whenever you want to work on our challenges.

### Step 6: Navigate to your challenges and open them in Sublime

Press `windows key + e` to bring up windows explorer.
Press F4 to go to the address bar.
Copy paste this line:

`%UserName%/code/lewagon-weekend-workshop`

Navigate to your current challenge and drag and drop the relevant folder into Sublime. Code away!
