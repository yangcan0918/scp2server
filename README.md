## Description
`scp2server` is a Vim tool for alipay daily work. When you save some files, it will copy your local file to server.

## Usage
1. copy .scp_config to your path;
* edit .scp_config:  
    * `scp.host` set ther server host or ip;
    * `scp.user` user name for access server;
    * `scp.password` password for access server;
    * `scp.from.root` evaluate relative path of file depend on this item. it start with the relative path of `.scp_config` file;
    * `scp.to.root` the path you want to place, root of your build path;
* edit your .gvimrc or .vimrc to add the this line:
    * `au BufWritePost \*.vm exec "!{PATH}/scp2server %"`
* replace {PATH} to your local path, change "\*.vm" to add or replace your file format;
* options:
    * `-f` scp the hole directory, by default ignore ".svn", ".git" and ".scp_config";
    * `-i {SOME_PATTERN}` use this option to ignore some files to scp when `-f` specified;
    * `-e {SOME_PATTERN}` use this option to filter some files to scp when `-f` specified;
    * `-c` use this option to create a `.scp_config` sample file under current directory;
* examples:
    * `scp2server` or `scp2server -c` create a `.scp_config` sample file;
    * `scp2server ./index.html` copy index.html file to remote server;
    * `scp2server -f` copy all files in current directory to remote server;
    * `scp2server -f -i "/\.vim\|\.bak\|\.swp\|\.less"` copy all files in current directory to remote server exclude ".vim", ".bak", ".swp", ".less" files;
    * `scp2server -f -e "\.htm\|\.css"` copy all .htm and .css files in current directory to remote server;

## Have fun..
enjoy it. waiting for 12/21/2012.
