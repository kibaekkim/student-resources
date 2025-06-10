## ✅ Part 1: Check if Git is Already Installed

1. **Open the terminal** and type:

   ```bash
   git --version
   ```

2. If Git is installed, you'll see something like:

   ```
   git version 2.x.x
   ```

   If it's **not installed**, proceed to Part 2.

---

## ✅ Part 2: Install Git Locally (Without sudo)

### Step 1: Download and Build Git

```bash
# Create a folder for local installs
mkdir -p ~/local/bin ~/local/src
cd ~/local/src

# Download Git source (update version if needed)
wget https://github.com/git/git/archive/refs/tags/v2.42.0.tar.gz
tar -xzf v2.42.0.tar.gz
cd git-2.42.0

# Configure and compile Git for local use
make prefix=$HOME/local all
make prefix=$HOME/local install
```

### Step 2: Add Git to Your PATH

Edit `~/.bashrc` (or `~/.bash_profile`, `~/.zshrc` depending on the shell):

```bash
export PATH="$HOME/local/bin:$PATH"
```

Then apply it:

```bash
source ~/.bashrc
```

Now check:

```bash
git --version
```

---

## ✅ Part 3: Configure Git (No Admin Needed)

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your_email@example.com"
```

Check:

```bash
git config --list
```

---

## ✅ Part 4: Create a GitHub Account

1. Go to [https://github.com](https://github.com) in a browser.
2. Click **Sign up**, create a username/password/email.
3. Verify your email.

---

## ✅ Part 5: Setup SSH to Use GitHub

### Step 1: Generate SSH Key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Just press Enter to accept the default location (`~/.ssh/id_ed25519`). No need for a passphrase.

### Step 2: Start the SSH agent

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Step 3: Add SSH Key to GitHub

```bash
cat ~/.ssh/id_ed25519.pub
```

1. Copy the output.
2. Go to GitHub → **Settings** → **SSH and GPG Keys** → **New SSH key**.
3. Paste the key and name it (e.g., "My Linux Workstation").

---

## ✅ Part 6: Clone a Repository

1. On GitHub, find a repo (e.g., [https://github.com/octocat/Hello-World](https://github.com/octocat/Hello-World)).
2. Click **Code** → **SSH** → Copy the link.
3. Run:

   ```bash
   git clone git@github.com:octocat/Hello-World.git
   ```

---

## ✅ Part 7: Make Changes and Push

```bash
cd Hello-World
echo "My first change" >> notes.txt
git add notes.txt
git commit -m "Add my first note"
git push
```

---

## ✅ Part 8: Create Your Own GitHub Repository

1. On GitHub → **+** → **New repository**
2. Name it `my-test-repo`, then:

```bash
mkdir my-test-repo
cd my-test-repo
git init
echo "# My Test Repo" > README.md
git add README.md
git commit -m "Initial commit"
git remote add origin git@github.com:yourusername/my-test-repo.git
git push -u origin master
```

---

## ✅ Part 9: Summary of Useful Git Commands

| Command                   | Description                   |
| ------------------------- | ----------------------------- |
| `git status`              | Show changes and staging info |
| `git add <filename>`      | Stage a file                  |
| `git commit -m "message"` | Save your changes             |
| `git push`                | Upload changes to GitHub      |
| `git pull`                | Download changes from GitHub  |
| `git clone <url>`         | Copy a repo from GitHub       |
| `git log`                 | View commit history           |

---

## ✅ Optional: Practice with GitHub Projects

1. Use [GitHub Classroom](https://classroom.github.com) if set up by a teacher.
2. Try the official **GitHub Hello World Guide**:
   👉 [https://docs.github.com/en/get-started/quickstart](https://docs.github.com/en/get-started/quickstart)
