- step 1：open demo，Automatically load the home page

- step 2：open devtools profiles, take a snapshot. ( now, we have 6 VueComponets )

- step 3：click `go page1` to switch router to page 1, take a snapshot again. (  now, we have 18 VueComponets  )

- step 4：click `go home` to switch router to home,  take a snapshot again. (  now, we have 6 VueComponets, this is the result we want to see. )

- step 5: click `go page1` to switch router to page 1, and click `click me` to call MessageBox, take a snapshot again. (  now, we have 22 VueComponets  )

- step 6: click `go page1` to switch router to page 1, take a snapshot again. (  now, we have 23 VueComponets, the componet of page 1 is not destroyed  )

- 步骤一： 打开demo, 自动加载home页面

- 步骤二： 打开devtools profiles, 拍一张内存快照 （这个时候有6个 vue组件）

- 步骤三： 点击路由链接，跳转到页面一， 拍一张快照， （这个时候有18个 vue组件）

- 步骤四： 回到home页面，拍快照， （这个时候也只有 6 vue组件，属于正常情况）

- 步骤五： 再点路由链接，跳转到页面一，并且点击一下`click me` 调用一次messageBox， 拍快照。（这个时候有 22 个vue组件, 对比可以发现，之前页面一里面的 el-input  和 el-button 等组件并没有被销毁掉。）

另外还有一个现象，就是我先在页面一调用一次messageBox 的时候，然后再到页面二调用一次messageBox，完了，回到home 去抓快照，

这个时候的情况是：`发现抓到的是页面二里面的vue组件被残留下来了，没有被销毁`

所以我觉得是不是最后哪个路由页面里面调用了一次`messageBox`后，该路由里面所有的组件就会一直不被销毁，直到下一次 再调用`messageBox`，当前没被销毁的vue组件才会被销毁掉，但是又会重新产生一批新的vue组件去占用内存。

之前好像有人提过一次，`this.$confirm`  内存泄漏，但是官方给出的解释是，这是预期行为，messageBox创建一个单独的实力，知道window关闭才会被销毁，这我也觉得合理，但是由于messageBox导致了该页面的所有其他组件不能被销毁，这样是不是不合理了？一个页面的vue组件少说也有几百上千个吧！这个还是挺占内存的。









