1. Install gpg4win
2. Generate key
   ```sh
   gpg --full-generate-key
   # go with default options
   ```
   ```sh
   gpg --list-secret-keys --keyid-format=long
   # copy key
   ```
   ```sh
   gpg --armor --export <key>
   # copy everything from output
   ```
3. Add gpg key to github.com
4. Give info to git
   ```sh
   git config --global --unset gpg.format
   git config --global user.signingkey <key>
   git config --global commit.gpgsign true
   git config --global tag.gpgSign true
   git config --global gpg.program "path_to_gpg.exe"
   ```
5. Run `git commit` and enter passphrase
