# 解锁FPS帧率上限

> 参考[自定义参数启动]的预览图勾选 **[解锁游戏内帧率上限]** 后即可解锁FPS上限
>
> 勾选启用该功能后，您可以在右侧显示[120]的输入框中自定义您的游戏帧率上限限制

- 一些常见的问题：
  - 开启本功能会封号吗
    - 不知道，敢用就用，用就不要怕怕就不用用
  - 会导致客户端损坏吗
    - 不会，此功能不会修改您计算机的任何文件
  - 为什么我解锁之后跑不到所设置的帧率
    - 请确保您使用了**管理员身份**运行此程序
    - 请确保游戏内设置中【垂直同步】选项关闭
    - 请确保开启本功能后您没有退出此程序
  - 其他问题
    - 请[联系开发者](https://github.com/DawnFz/Genshin.Launcher.Plus/issues/new)或[加群](https://jq.qq.com/?_wv=1027&k=JXvpjEyR)咨询



- 解锁FPS的实现方式：

  - [Unlocker](https://github.com/DGP-Studio/Unlocker)

  - ### Simple Usage

    flexible way
    ```c#
    //create a genshin impact process
    Process p = new(){...};
    //pass the process and target fps to unlocker
    Unlocker unlocker = new(p,144);
    //start the process
    p.Start();
    //immediately call the UnlockAsync method
    //this method will not return until an error occurred or the process has exited
    var result = await unlocker.UnlockAsync();
    ```

    Or straightforward way
    ```c#
    //create a genshin impact process
    Process p = new(){...};
    //pass the process and target fps to unlocker
    Unlocker unlocker = new(p,144);
    //start the process and immediately call the UnlockAsync method
    //this method will also not return until an error occurred or the process has exited
    var result = await unlocker.StartProcessAndUnlockAsync();
    ```
