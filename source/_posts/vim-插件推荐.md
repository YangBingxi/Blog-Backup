---
title: vim 插件推荐
date: 2020-02-06 22:41:35
tags: 
- vim
- linux
- tool
categories:
- code
---
## 工欲善其事必先利其器之vim-插件

### 介绍

#### 为什么要安装插件

[[尽管vim本身已经十分强大，但是还是有很多不足的地方，这些就可以通过插件来进行补充，安装自己喜欢的插件并配置成自己习惯的方式]]

#### 怎么找vim插件
- 按照需求在网上搜索
- [vimawesome](https://vimawesome.com/)
- 参考别人的开源配置
  - 推荐一个开源项目[spacevim](https://github.com/SpaceVim/SpaceVim)

<!-- more -->

---

### 推荐的插件
**注意：插件的配置请参考项目地址的文档**


#### plugged manage tool：VIM下的插件管理工具

[Link:vim-plug](https://github.com/junegunn/vim-plug)

---
#### display tool：有关界面美化的插件

[Link:vim-airline:状态栏插件](https://github.com/vim-airline/vim-airline)

[Link:vim-snazzy：主题插件](https://github.com/connorholyday/vim-snazzy)

[Link:vim-startify:欢迎界面](https://github.com/mhinz/vim-startify）

- 在```vimrc```中添加设置： ```color snazzy```
- airline自动生效，会在不同的Model下显示不同的颜色，以及一些文件相关的信息(文件路径、文件名、所在git分支、当前行、列数、编码等)
![airline](/img/Vim/plug/airline1.png)
![airline](/img/Vim/plug/airline2.png)
![airline](/img/Vim/plug/airline3.png)
- startify会显示一个启动效果(最近打开的文件列表，提供通过文件前的数字编号快速跳转)
  - 如果startify没有自动打开，可以执行```:startify``` <br>
![startify](/img/Vim/plug/startify.png)
---
#### File navigation：文件导航相关的插件

[Link:nerdtree：文件树](https://github.com/scrooloose/nerdtree)
- 在```vimrc```中添加设置

```vim

"                           === NERDTree ===                                 "
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"autocmd vimenter * NERDTree  "进入vim后，自动加载目录树
"打开文件时不会自动打开目录树和startify，否则会自动打开目录和startify
autocmd StdinReadPre * let s:std_in=1
"autocmd VimEnter * if argc() == 0 && !exists("s:std_in") | NERDTree | endif
autocmd VimEnter *
                \   if !argc()
                \ |   Startify
                \ |   NERDTree
                \ |   wincmd w
                \ | endif

noremap ff :NERDTreeToggle<CR>   "按ff可以进入目录树"
noremap <LEADER>v :NERDTreeFind<CR>
"关闭默认显示隐藏文件，需要显示时可以在tree中按I
"let NERDTreeShowHidden=1

" NERDTress File highlighting
function! NERDTreeHighlightFile(extension, fg, bg, guifg, guibg)
exec 'autocmd filetype nerdtree highlight ' . a:extension .' ctermbg='. a:bg .' ctermfg='. a:fg .' guibg='. a:guibg .' guifg='. a:guifg
exec 'autocmd filetype nerdtree syn match ' . a:extension .' #^\s\+.*'. a:extension .'$#'
endfunction

call NERDTreeHighlightFile('java', 'blue', 'none', '#3366FF', '#151515')
call NERDTreeHighlightFile('cpp', 'Red', 'none', 'red', '#151515')
call NERDTreeHighlightFile('c', 'Red', 'none', 'red', '#151515')
call NERDTreeHighlightFile('py', 'green', 'none', 'green', '#151515')
call NERDTreeHighlightFile('jade', 'green', 'none', 'green', '#151515')
call NERDTreeHighlightFile('ini', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('md', 'blue', 'none', '#3366FF', '#151515')
call NERDTreeHighlightFile('yml', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('config', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('conf', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('json', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('html', 'yellow', 'none', 'yellow', '#151515')
call NERDTreeHighlightFile('styl', 'cyan', 'none', 'cyan', '#151515')
call NERDTreeHighlightFile('css', 'cyan', 'none', 'cyan', '#151515')
call NERDTreeHighlightFile('coffee', 'Red', 'none', 'red', '#151515')
call NERDTreeHighlightFile('js', 'Red', 'none', '#ffa500', '#151515')
call NERDTreeHighlightFile('php', 'Magenta', 'none', '#ff00ff', '#151515')
```
- 快捷键
  - **ff** : 打开/关闭目录树
  - **r** : 刷新目录树(需在nertree下执行)
  - **I** : 打开/关闭显示隐藏文件
  - **[LEADER]v** : 在目录树中查找当前文件

- 配合上面提到的startify可以有如下效果
![nerdtree](/img/Vim/plug/nerdtree.png)

---

#### Taglist：函数、变量列表
[Link:tagbar](https://github.com/majutsushi/tagbar)
- 说明
  - 为了更好的支持，需要安装ctags
  - [Link](https://docs.ctags.io/en/latest/autotools.html)
- 在```vimrc```添加配置```noremap <silent>F :TagbarToggle<CR>```
- 快捷键
  - **F**

![taglist](/img/Vim/plug/taglist.png)

---
#### Error checking：代码错误检测

[Link:ale](https://github.com/w0rp/ale)
- 在```vimrc```中添加配置

```vim
let b:ale_linters = ['pylint']
let b:ale_fixers = ['autopep8', 'yapf']
let g:ale_sign_error = '✗'
let g:ale_sign_warning = '⚡'
let g:airline#extensions#ale#enabled = 1
map <LEADER>s :ALEToggle<CR>
```
- 快捷键
  - [LEADER]s
---
#### Auto Complete：代码自动补全

[Link:YouCompleteMe](https://github.com/Valloric/YouCompleteMe)
- **说明** ： 需要额外安装，详见项目地址
- 在```vimrc```中添加配置
```vim
nnoremap gd :YcmCompleter GoToDefinitionElseDeclaration<CR>
nnoremap g/ :YcmCompleter GetDoc<CR>
nnoremap gt :YcmCompleter GetType<CR>
nnoremap gr :YcmCompleter GoToReferences<CR>
let g:ycm_autoclose_preview_window_after_completion=0
let g:ycm_autoclose_preview_window_after_insertion=1
let g:ycm_use_clangd = 0
let g:ycm_python_interpreter_path = "/usr/bin/python3"
let g:ycm_python_binary_path = "/usr/bin/python3"
```
- 快捷键
  - **gd** : Goto Definition
  - **g/** ： Get Doc
  - **gt** : Get Type
  - **gr** : Goto References

---
#### Undo Tree：文件修改历史树

[Link:undotree](https://github.com/mbbill/undotree/)
- 在```vimrc```中添加配置
```vim
let g:undotree_DiffAutoOpen = 0
map <LEADER>al :UndotreeToggle<CR>
```
- 快捷键
  - [LEADER]al

![undotree](/img/Vim/plug/undotree.png)

---
#### Other visual enhancement

[Link:vim-cursorword](https://github.com/itchyny/vim-cursorword)
- 快捷键
  - **cs"'** : [change surround]将单词的"改为'，同理也可以操作'' "" {} () [] 等
  - **cs'"** : 将单词的'改为"，同理也可以操作'' "" {} () [] 等
  - **ds'** : [delete surround]删除单词的'，同理也可以操作'' "" {} () [] 等
  - **ds"** : 删除单词的"，同理也可以操作'' "" {} () [] 等
  - **ysiw"** : [you add a surround]给光标所在的单词添加"" ，同理也可以添加'' "" {} () [] 等
[Link:indentline:代码缩进线](https://github.com/yggdroot/indentline)

[Link:vim-interestingwords:高亮单词](https://github.com/lfv89/vim-interestingwords)
- 快捷键
  - [LEADER]k : 对光标下的单词高亮
  - n : 跳转到下一个
  - N : 跳转到上一个
  - [LEADER]K : 清除高亮
![interestingwords](/img/Vim/plug/interestingword.png)
---
#### Git：git相关

[Link:confict-mark （==没搞懂==）](https://github.com/rhysd/conflict-marker.vim)

[Link:vim-fugitive](https://github.com/tpope/vim-fugitive)

[Link:vim-gitignore](https://github.com/gisphm/vim-gitignore)

[Link:vim-gitgutter 实时显示文件的修改情况](https://github.com/airblade/vim-gitgutter)
- 在```vimrc```中添加```set updatetime=100```

[Link:gv.vim 显示文件的提交历史](https://github.com/junegunn/gv.vim)
- 命令
  - ```:GV```

---
#### HTML, CSS, JavaScript, PHP, JSON, etc.

[Link:vim-json](https://github.com/elzr/vim-json)

[Link:vim-ccs3-syntax](https://github.com/hail2u/vim-css3-syntax)

[Link:PIV](https://github.com/spf13/PIV)

[Link:vim-colorseque](https://github.com/gko/vim-coloresque)

[Link:vim-javascript](https://github.com/pangloss/vim-javascript)

[Link:emmet-vim](https://github.com/mattn/emmet-vim)

---
#### Python

[Link:python-mode](https://github.com/python-mode/python-mode)

---
#### Markdown

[Link:mathjax-support-for-mkdp](https://github.com/iamcco/mathjax-support-for-mkdp)

[Link:markdowm-preview](https://github.com/iamcco/markdown-preview.vim)
- 在```.vimrc```文件中添加下面配置

```vim
let g:mkdp_path_to_chrome = "google-chrome"
let g:mkdp_auto_start = 0
let g:mkdp_auto_close = 1
let g:mkdp_refresh_slow = 0
let g:mkdp_command_for_g1lobal = 0
let g:mkdp_open_to_the_world = 0
let g:mkdp_open_ip = ''
let g:mkdp_browser = 'chromium'
let g:mkdp_echo_preview_url = 0
let g:mkdp_browserfunc = ''
let g:mkdp_preview_options = {
    \ 'mkit': {},
    \ 'katex': {},
    \ 'uml': {},
    \ 'maid': {},
    \ 'disable_sync_scroll': 0,
    \ 'sync_scroll_type': 'middle',
    \ 'hide_yaml_meta': 1
    \ }
let g:mkdp_markdown_css = ''
let g:mkdp_highlight_css = ''
let g:mkdp_port = ''
let g:mkdp_page_title = '「${Sname}」'

```
- **:MarkdownPreview** : 可以在浏览器中进行markdown文件的预览

---

#### Bookmarks：书签

[Link:vim-signture:添加标记和快速跳转](https://github.com/kshenoy/vim-signature)
- 快捷键
  - **mx** : Toggle mark 'x' and display it in the leftmost column
  - **'x** : Jump to mark x
  - **dmx** : Remove mark 'x' where x is a-zA-Z
  - **m<Space>** : Delete all marks from the current buffer
  - **]`** : Jump to next mark
  - **[`** : Jump to prev mark
  - **m[0-9]** : Toggle the corresponding marker !@#$%^&*()

---
#### Other useful utilities

[Link:goyo 专注写作模式Focus model](https://github.com/junegunn/goyo.vim)
- 在```.vimrc```文件中添加配置<br>

```
map <LEADER>gy :Goyo<CR>
```

- 快捷键：
  - **[LEADER]gy** : 开启focus model
![goyo](/img/Vim/plug/goyo.png)

[Link:vim-surround:快速编辑成对内容](https://github.com/tpope/vim-surround)
- 快捷键：
  - **cs"'** : [change surround]将单词的"改为'，同理也可以操作'' "" {} () [] 等
  - **cs'"** : 将单词的'改为"，同理也可以操作'' "" {} () [] 等
  - **ds'** : [delete surround]删除单词的'，同理也可以操作'' "" {} () [] 等
  - **ds"** : 删除单词的"，同理也可以操作'' "" {} () [] 等
  - **ysiw"** : [you add a surround]给光标所在的单词添加"" ，同理也可以添加'' "" {} () [] 等

[Link:wildfire](https://github.com/gcmt/wildfire.vim)

[Link:vim-multiple-cursors 多光标操作，快捷编辑](https://github.com/terryma/vim-multiple-cursors)

[Link:tabular](https://github.com/godlygeek/tabular)

[Link:nerdcommenter 代码快速注释工具](https://github.com/scrooloose/nerdcommenter)

---
#### Dependencies

[Link:[[vim-addon-mw-utils]]](https://github.com/MarcWeber/vim-addon-mw-utils)

[Link:vim-textobj-user](https://github.com/kana/vim-textobj-user)

[Link:vim-FIGlet](https://github.com/fadein/vim-FIGlet)

---

#### Tool
[Link:auto-pairs 括号补全插件](https://github.com/jiangmian/auto-pairs)

[Link:vimwiki 个人wiki](https://github.com/vimwiki/vimwiki)
- 用法参见github主页

[Link:calendar 日历](https://github.com/itchyny/calendar.vim)
- 在```vimrc```文件中添加配置

```vim
let g:calendar_frame = 'default'
noremap <LEADER>ac :Calendar<CR>
noremap <LEADER>acc :Calendar -view=clock<CR>
noremap <LEADER>acw :Calendar -view=week<CR>
noremap <LEADER>acm :Calendar -view=month<CR>
noremap <LEADER>acy :Calendar -view=year<CR>
```
- 快捷键：
  - **[LEADER]ac** : 打开日历
  - **[LEADER]acc** : 打开日历时钟模式
  - **[LEADER]acy** : 打开日历年模式
  - **[LEADER]acm** : 打开日历月模式
  - **[LEADER]acw** : 打开日历周模式
  - **<**、**>** : 在日历中前进后退
  - **T** : 进入TASK
    - **i** **c** **a** : 进行修改
    - **D** : 标记为完成
    - **L** : 清除完成的任务
  - **E** : 进入EVENT
  - **?** : 进入帮助文档
