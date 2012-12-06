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

## Have fun..
enjoy it. waiting for 12/21/2012.