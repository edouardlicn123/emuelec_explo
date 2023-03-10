##已知问题

在某种不明条件下，对ES的目录设置作出调整后，如有与当前目录相同的name tag一致的系统，则原系统和新增系统很有可能在重启后一同消失。

例如，如果有一个psx的系统，你再新增一个psx，或者无意地新建一个psx，重启后有一定几率两个系统都无法显示。即使是你在暂停菜单中再次打开此系统的显示照样失效。

同时检查挂载，目录结构等一切正常。

甚至我都在怀疑，产生这个问题的原因是不是修改相同name tag导致，但我高度怀疑这是一个很有可能的原因。

##考虑

首先，增加一个附加usb盘，且我自己自建有其他“系统”但以“xxxviva”的后缀区分，按理说不可能产生冲突。但仍不排除系统缓存对新的配置文件冲突导致配置冲突。

其次，似乎PSP系统只能命名为PSP而不能改其他名称。我曾提交issue到GitHub，但被shanti粗暴地关闭，并认为此不是bug。因此对于PSP似乎这个无可避免地肯定需要出现相同name tag的系统。

因为bug的出现的不稳定性，因此暂时只能将就一下开两个PSP的name tag。

##建议

尽量在附加盘上创建跟系统不一样的name tag的system，虽然这不等于不会出现冲突，但至少降低几率。