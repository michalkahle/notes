To initialize:
    
    $ git init --bare ~/.dotfiles
    $ alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
    $ dotfiles config status.showUntrackedFiles no
    
To clone:

    $ git clone --separate-git-dir=$HOME/.dotfiles https://github.com/michalkahle/.dotfiles.git ~/dotfiles
    $ mv ~/dotfiles/.bashrc ~/
    $ source ~/.bashrc
    $ dotfiles config status.showUntrackedFiles no    
    
When adding files to commit use:

    $ dotfiles add -u
    $ dotfiles commit
    $ dotfiles push
