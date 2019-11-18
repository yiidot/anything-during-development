
1. 制作预制体
预制体结构及脚本
1.1 属性组预制体
PropertyGroup(Image) -> Vertical Layout Group、Content Size Filter(Vertical Fit->Preffered Size)
  |- Header(Toggle)
  |- Body(Image) -> Vertical Layout Group
1.2 属性条目预制体
PropertyItem(Image) -> Horizontal Layout Group、Content Size Filter(Vertical Fit->Preffered Size)
  |- Label(Image)
    |- Text Content Size Filter(Vertical Fit->Preffered Size)
  |- Value(Image)
    |- Text Content Size Filter(Vertical Fit->Preffered Size)

2. 编写脚本动态生成grid,动态计算未绑定Content Size Filter脚本的节点高度。
