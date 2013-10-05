## 在 RStudio 下使用 R 的基本功能 


#### 概述

在前一节中已经提及，R 的核心是命令行界面的命令解释器。所有的 R 代码都被输入到解释器中，由其来执行并返回结果。 在 RStudio 中，Console 窗口是四个窗口中唯一一个没有标签页的。也就是说，无论如何你总是需要与 Console 打交道。

RStudio 的项目（project）功能使得用户很自然地把不同内容的工作区分开来，每个项目有各自的工作目录（working directory）、工作空间（workspace）和源文件。


继续之后的章节前，我们建议您已经获取或配置了可以使用的最新版本 R + RStudio 环境，不论是服务器版或桌面版均可。本节中所介绍的基本功能均不需要安装任何不随 R 附带的包。

### 1. 在 Console 中工作


RStudio Console 包含了多种功能，目的是为了使与 R 的交互更直接和高效。熟练掌握这些，并辅以 Source 和 History 窗口中的相关功能，可以迅速带来极大的收获，提升你的整体生产力。

#### 代码补全
R 默认加载了许多函数，随着分析的深入，你的 workspace 中还会有许多对象。在对于函数名记忆不准确，或对象名太长输入不便时，代码补全功能可以帮助你快速找到和输入当前 workspace 中你想找到的任何对象和函数。

RStudio 支持以 **Tab** 键来触发命令补全。比如说，在你的 workspace 中有一个叫做 `pollResults` 的对象，你只需在命令行中输入 `poll` 并按下 **Tab** 键，RStudio 就会自动帮你补全 `pollResults`。

代码补全同时提供函数的简单帮助功能。比如当你输入 `sub` 并按下 **Tab** 键时，你会看到：

![](http://www.rstudio.com/images/docs/using_console_completion.png)

这时，`subset` 函数的简介和参数接口也会被同时显示出来。

代码补全也能在函数内使用，提供函数参数的补全和帮助。如果你输入 `subset(` 并按下 **Tab**，你会看到如下的界面：

![](http://www.rstudio.com/images/docs/using_console_completion_args.png)

用上下键选择你需要输入的参数，按回车确认。按 **F1** 则可打开函数的详细帮助页面。

需要补充的是，未安装或未加载的包的帮助是不会显示的。如果你发现你想找的函数不能自动补全，请先检查你是否已经加载了包含这个函数的包，或已经输入的部分是否有错误（R 是大小写敏感的，大小写输错时也不会自动补全）。


#### 获取之前的命令
命令行交互的特点是一次只能输入一条命令（虽然这一条也可以是好几行）。所以大多数时候，我们使用 Console 时是逐行输入的，Console 也在读入一行后立即执行，执行完成后再读入下一行。在这种时候，如果我们可以重新获取之前输入的命令重新执行或加以修改，就可以避免大量的手工输入。

在 RStudio Console 中，你可以使用键盘的上下键来逐行读取之前输入过的命令。

如果觉得逐行读取太慢，想要立即找到好几条之前输入的命令，你可以使用 **control + up** 来获得最近输入的命令列表，并直接在列表中选择，如下图：

![](http://www.rstudio.com/images/docs/using_console_history_popup.png)

还嫌不够快的话，试试输入想查找的命令的一部分后，再按 **control + up**，可以直接查找输入过的符合这个前缀的命令，如下图：

![](http://www.rstudio.com/images/docs/using_console_history_search_popup.png)


#### Console 的标题栏
这张截图显示了 Console 窗口的一些其他功能：
* 显示当前工作目录
* 在代码的计算时间过长时中止 R。
* 最大/最小化 Console 窗口，同时也会最小/最大化和其摆放在同一侧的另一个窗口。通过点击右上角的图标或双击标题栏均可。

![](http://www.rstudio.com/images/docs/using_console_title_bar.png)



[1] RStudio Documentation, Working in the Console [http://www.rstudio.com/ide/docs/using/console](http://www.rstudio.com/ide/docs/using/console)


---


### 2. 使用编辑器来编辑和执行代码

#### 概述
RStudio 的 Source 窗口中包括了各种提高生产力的功能，包括语法高亮，代码自动补全（同 Console 中的一致），多文件编辑和查找/替换。

在编辑器中编辑和执行代码是更多 R 开发者喜爱的方式。在仅仅需要执行几行较短的代码时，可能更多人会选择使用 Console 窗口直接输入。但如果需要编辑并重用很多行代码，甚至将他们组织为一个函数，逐行键入的方式则显得不那么简便，并且 Console 本来也不是为这样的使用方式所设计的。

RStudio 的文本编辑器可以适用于大部分 R 或与 R 有关的语言写就的代码。根据当前编辑的源文件语言的不同，其上方的工具栏也会显示出不同的功能按钮，满足各个不同语言的需要。熟练掌握编辑器的操作可以极大地提升你的生产力。


#### 管理多个源文件
而 Source 窗口就是专门被设计来编辑长段代码的。其上方的标签页设计，可以使得你同时打开多个源文件，并在这些源文件之间切换。如果源文件过多，还可以搜索特定的文件名，见下图：

![](http://www.rstudio.com/images/docs/source_tabs.png)

对于 RStudio **File -> New** 菜单下可以新建的各个类型的文本文件，RStudio 都提供代码中关键字的高亮显示（新版本中支持的文件类型已经不止截图中这些了）。有许多类型的文件现在可能还用不到，但大部分都会在将来的章节中介绍。

![](http://www.rstudio.com/images/docs/source_new_menu.png)


#### 提取函数
RStudio 可以分析某一代码段，并自动将其转换成一个可重复使用的函数。任何在选择的代码内的“自由的”变量，即那些被引用但没有被创建的变量，将被转化为函数的参数：

![](http://www.rstudio.com/images/docs/source_extract_function.png)

这种情况在编写某个大型程序中的一小段时非常实用：在编写时，常常会使用一些测试数据集来检查分析的每一步是否正确。而在写完后，将代码中测试数据集的赋值的部分删去，这样剩下的代码段中，原先测试的数据集就变成了“被引用但没有被创建的变量”。接着对这段代码提取函数，即可生成执行这段分析的代码的函数，而原先的测试数据集就变为了函数的参数。

#### 注释和缩进
关于这一部分，Google 的 R Style Guide 中建议了一些编写 R 代码时的良好风格[1]，但也有人争辩说，Google 并不应该被视为 R 的权威[2]。无论如何，良好的编程风格是为了让人更容易读懂你的代码（代码本身就是写给人看的），统一的注释和缩进格式只是一种手段而已。

在 RStudio 的 Source 窗口中，你可以使用 **Ctrl + Shift + C** 来注释或去除注释。

![](http://www.rstudio.com/images/docs/source_comment.png)

在你编写 R 代码时，RStudio 编辑器会帮助你自动缩进代码，并且在以下情况时会自动重新缩进你的代码：

1. 当新的代码被粘贴进 Source 编辑器时（可在 Code Editing 中设置）。
2. 当你选择上图中的 Reindent Lines 命令时。

#### 执行代码
RStudio 支持在编辑器中直接执行代码：代码将被插入到 Console 窗口中并执行，其结果也将同时显示。

##### 执行单行代码
若想要当前执行当前指针所在的一行代码，你可以按下 **Ctrl + Enter** 键（或使用 Source 窗口标题栏上的 Run 按钮）：

![](http://www.rstudio.com/images/docs/source_execute_line.png)

执行完一行后，RStudio 会自动把指针移动到下一行，这样你就可以在手不离开键盘的情况下逐行执行代码段，并查看其运行结果。

##### 执行多行代码
RStudio 支持三种同时执行多行代码的方式：

1. 选择多行代码，按下 **Ctrl + Enter** 键（或使用 Source 窗口标题栏上的 Run 按钮）。
2. 在运行完某一段代码后，按下 **Ctrl + Shift + P** 键（或对应的标题栏按钮），即可重新运行上一次运行的代码段（单行或多行）。该命令并不是简单的读取执行的历史来重新执行，而是会把当前版本的代码段重新执行（即使和上一次相比已经修改过了）。
3. 如要执行整个文件，可以按下 **Ctrl + Shift + Enter** 键（或使用标题栏上的 Source 按钮）。这样做的好处是可以整个文档会被保存为一个临时文件，然后输入 Console，在 Console 中的代码不会被重新显示一遍（选择 Source with Echo 则会显示）。

##### Source on Save 
这是一个较奇怪的选项，但当你掌握它的用法后它其实非常好用。在分析时我们往往有这样两种类型的代码：re-usable functions 和 freestanding lines。通常，我们将固定的方法编写为 re-usable 的函数，而使用 freestanding 的几行 R 代码来整理实际的、千奇百怪的数据，并调用这些函数来分析。

在这里，这些 re-usable functions 是作为 freestanding lines 的“资源”存在的。 通常这些函数需要一直被加载于工作空间中，以协助主要代码的分析工作。这时，如果更新了这些 re-usable functions 的代码而忘记执行，则工作空间中的函数不会更新，代码执行的结果也无法查看到。

RStudio 提供这个选项的目的就是建议我们在遇到上述的使用情况时，将那些 re-usable functions 组织在一个单独的文件中，并勾选这个选项。这样这个文件的任何更新，只要一经保存都会直接同步于工作空间中，可供其他代码调用。

#### 代码折叠和分段
##### 代码折叠
RStudio 支持自动的或用户自定义的代码段折叠。代码折叠使得编辑器窗口更简洁，寻找代码段更迅速。比如在下图中，函数 `plot.autoregressive.model` 的内容就被折叠了起来：

![](http://www.rstudio.com/images/docs/codefolding_basic.png)

点击行号边的小箭头或括号内的箭头图标均可展开这段代码。

##### 代码分段
如果代码中更多的是如上图示意的函数等内容，由于其本来就是可折叠的，则并不需要再将代码分段并折叠了。可若是代码大多是以 freestanding lines 的形式存在，则自定义的代码分段和折叠就非常有用。以下的代码已经被分为了三段，其中前两段被折叠了：

![](http://www.rstudio.com/images/docs/codefolding_sections.png)

如果你希望新插入一个“代码段”的话，你可以使用 **Code -> Insert Section** 命令。更简单的方法是，任何以四个或以上的 dashes (-), equal signs (=), 或 pound signs (#) 结尾的注释行，都会被视为分段符。比如说如下的三种注释行都会自动生成新的一段：

	# Section One ---------------------------------
	
	# Section Two =================================
	
	### Section Three ############################# 

使用下方的导航栏，可以在不同的代码段中快速切换：

![](http://www.rstudio.com/images/docs/codefolding_jumpto.png)

这些功能对于较长的代码的编辑和整理非常有用。写注释除了帮助阅读代码的人理解外，常常也就是为了分段的。而现在只需在写注释时加上一些标记，代码就自动被分为了可折叠、可快速导航的段落。


[1] Google's R Style Guide: [http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml](http://google-styleguide.googlecode.com/svn/trunk/Rguide.xml)

[2] Stackoverflow, an answer and its comments to the question: When does it pay off to use S4 methods in R programming? [http://stackoverflow.com/a/3602729](http://stackoverflow.com/a/3602729)

[3] RStudio Documentation, Editing and Executing Code [http://www.rstudio.com/ide/docs/using/source](http://www.rstudio.com/ide/docs/using/source)

[4] RStudio Documentation, Code Folding and Sections [http://www.rstudio.com/ide/docs/using/code_folding](http://www.rstudio.com/ide/docs/using/code_folding)


---

### 3. 项目、工作目录和工作空间

#### 概述


#### 创建项目
若想要创建一个新的 RStudio 项目，你可以点选菜单项 **Project ->> Create Project **，该选项也可在 RStudio 界面右上方的项目快捷方式中找到。

你可以从以下三种文件夹来创建一个 RStudio 项目：

![](http://www.rstudio.com/images/docs/projects_new.png)

前两种就是普通的空文件夹，而第三种涉及到版本控制系统（VCS）的特殊文件夹将在之后的章节中详细介绍。

当一个新的项目被创建后：

1. RStudio 在项目文件夹中自动创建一个项目文件（以 `.Rproj` 为后缀名）。这个文件的内容包含了各种项目的设置，也可以被当做在文件系统中直接打开项目的快捷方式。
2. RStudio 在项目文件夹中自动创建一个隐藏文件夹（文件夹名为 `.Rproj.user`）来存放项目临时文件。这个文件夹会被自动添加到 `.Rbuildignore` 或 `.gitignore`，这意味着大部分时候这个文件夹可以被忽略。
3. 创建后，这个项目会被自动加载到当前打开的 RStudio 中。在之前提到的界面右上方的项目快捷菜单中，可以看到显示的项目名。有时你打开了 RStudio， 你会发现编写的代码和存储的数据集不在了，这往往都是由于本来你是在一个项目中工作，而现在这个项目没有正确地被加载。而检查右上角的项目名是最快捷的判断当前加载的项目的方法。


