## Description
`scp2server` is a Vim tool for alipay daily work. When you save some files, it will copy your local file to server.

## Usage
1. copy .scp_config to your path;
* edit .scp_config:  
    * `scp.host` set ther server host or ip;
    * `scp.user` user name for access server;
    * `scp.password` password for access server;
    * `scp.from` evaluate relative path of file depend on this item. it start with the relative path of `.scp_config` file;
    * `scp.to` the path you want to place, root of your build path;
    * `debug.mode` set to `1` will display more informations;
* link your scp2server to $PATH
    * `sudo ln -s {PATH_OF_YOUR_CMD}/scp2server /usr/sbin/scp2server`
* connect with your editor:
    * *VIM* `au BufWritePost \*.vm exec "!scp2server %"`
    * *Sublime Text 2* `Tools` > `Build System` > `New Build System`, and then copy the following code to your editor and save:

        ```javascript
        {
           "cmd": ["scp2server", "${file_name}"],
           "working_dir": "${file_path}",
           "selector": "*.*"
        } 
        ```
* replace {PATH} to your local path, change "\*.vm" to add or replace your file format;
* options:
    * `-f` scp the hole directory, by default ignore ".svn", ".git" and ".scp_config";
    * `-i {SOME_PATTERN}` use this option to ignore some files to scp when `-f` specified;
    * `-e {SOME_PATTERN}` use this option to filter some files to scp when `-f` specified;
    * `-c` use this option to create a `.scp_config` sample file under current directory;
    * `-p` use `mkdir -p` to create full path if remote path not exist.
* examples:
    * `scp2server` or `scp2server -c` create a `.scp_config` sample file;
    * `scp2server ./index.html` copy index.html file to remote server;
    * `scp2server -f` copy all files in current directory to remote server;
    * `scp2server -f -i ".vim\|.bak\|.swp\|.less"` copy all files in current directory to remote server exclude ".vim", ".bak", ".swp", ".less" files;
    * `scp2server -f -e ".htm\|.css"` copy all .htm and .css files in current directory to remote server;

## Have fun..
enjoy it. waiting for 12/21/2012.
