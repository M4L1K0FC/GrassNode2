# Grass节点阶段2

使用此基于Python的脚本在VPS上自动化Grass节点挖矿，管理多个设备和IP地址，确保24/7的正常运行时间并最大化收益。适合那些希望通过SOCKS5协议无缝且高效地处理WebSocket连接的用户。

# 由Phantom提供的社区节点计划

我会代表你们运行Grass节点，因为很多人表示无法自己运行服务器或VPS，或者由于代理无法运行脚本，单用户的VPS成本非常高。因此，我购买了高内存配置和100GB高级计划的VPS，这样可以有效地为社区运行节点，降低成本！

-> 你们购买代理的费用是4美元，而我批量购买仅需2美元！

-> 你无法获得更高收益的原因之一是不了解如何运行节点，因此对于非开发或非技术人员，社区节点是最佳选择。我们目前有约120人加入我们的社区节点，日收益超过120M积分！

-> 很多人未使用VPS，而是通过个人电脑运行，可能导致带宽损失，并且需要24/7高速互联网，因此VPS是最佳选择。

-> 解决方案：直接通过Discord私信联系我，发送你的ID，我会将Grass积分直接添加到你的Grass账户中！

-> **每百万积分仅需6美元**，低于自己运行节点的成本！无需监控或管理服务器！无需额外VPS费用！

-> 联系方式：`0xphatom` 在Discord上 https://discord.com/users/979641024215416842

# 注意 - 基于阶段1的空投 = 1M积分 == 平均约45个代币~~>
# 100M+积分订单享受5%折扣
# 150M+积分订单享受10%折扣
# 300M+积分订单享受15%折扣
# 500M+积分订单享受20%折扣

## 功能特点

- Grass节点脚本适用于**阶段2**，并提供1.25倍加成！
- 通过SOCKS5代理连接到WebSocket服务器。
- 支持同时管理多个Grass用户ID和代理（每个代理每日约生成3000 $GRASS积分）。
- 根据**阶段1的空投**，1M Grass积分约等于45个GRASS代币（不适用于额外奖励）。
- 基于数据消耗的预估：2GB代理数据生成1M积分；6美元代理成本产生约45 GRASS代币。
- 自动处理各种错误，如代理失效、SSL错误、无效IP地址、空连接回复、发送错误代码等。
- 自动从文件中移除失效代理！

# 获取用户ID

1. 打开链接并登录：https://app.getgrass.io/dashboard
2. 按F12打开控制台，输入代码（Ctrl + Shift + i）进入检查界面
3. 在控制台中输入 `localStorage.getItem('userId')`
4. **控制台打印的文本即为用户ID**
5. ![image](https://github.com/Solana0x/getgrass/assets/142747768/099b7ce1-1c56-4709-a9ba-7c45fc65ef2d)

# 获取Socks5代理IP地址

1. 在https://app.proxies.fo/signup?referral=662d5a3a775a945a8de790ba创建账号
2. 访问https://app.proxies.fo/plans并购买下列计划
3. ![image](https://github.com/user-attachments/assets/5453eabd-0a09-49f7-b004-1ca4617b9f8a)
4. **最佳选择** - 支持使用加密货币和Binance支付！
5. 进入控制面板，点击“Go to Generator”按钮
6. 修改代理格式为 `USER:PASS@HOST:PORT` 并选择 `Socks5`，在代理数量中填写200或其他数字。
7. 点击“保存”以生成代理。
8. ![image](https://github.com/user-attachments/assets/010753b5-1112-48c0-9a40-6b00189abd10)
9. 可以使用任意数量的代理，总池大小为25,000个代理。

## 要求

- Get Grass账号邀请链接 (https://app.getgrass.io)
- Python (安装Python：https://www.python.org/downloads/ [Windows/mac]) 或Ubuntu服务器 [`sudo apt install python3`]
- VPS服务器！可通过AWS免费套餐或Google免费套餐获得，或以2-5美元每月的价格购买。
- 代理服务器 - 请仅购买ISP住宅代理以获取$GRASS代币，数据中心或廉价免费代理将无法获得收益。（推荐代理提供商）
- Proxies.fo - [https://app.proxies.fo/signup?referral=662d5a3a775a945a8de790ba](https://app.proxies.fo/signup?referral=662d5a3a775a945a8de790ba) [购买1GB计划即可，足够使用1-6个月，并支持无限账户或代理]
- - Light Node (for VPS) - [https://www.lightnode.com/?inviteCode=OUMJXM&promoteWay=LINK](https://www.lightnode.com/?inviteCode=OUMJXM&promoteWay=LINK)
- 从Grass仪表板获取用户ID

## 运行代码的步骤 -

在运行脚本之前，请确保您的机器已安装Python。然后使用以下命令安装所需的Python包：

1. ``` git clone https://github.com/Solana0x/GrassNode2.git ```
2. ``` cd GrassNode2 ```
3. ``` pip install -r requirements.txt ```
4. 在 `main.py` 文件的第81行替换 `User ID`。
5. 默认情况下会随机使用100个代理，如果需要更改，请在第87行的 `active_proxies = random.sample(all_proxies, 100)` 处进行修改。这里的100表示一次性使用100个代理。
6. 别忘了在proxy.txt文件中添加多个代理，支持1000多个代理！格式：`socks5://username:pass@ip:port`。
7. 可从Proxies.fo网站获取多个代理IP地址！[使用多个IP！`1 IP 每天约3000 $Grass`。
8. 运行脚本 `python3 main.py` - 单代理模式
10. 若要使用多个用户ID，复制 `main.py` 文件代码并创建新Python文件，重复操作，确保创建新文件夹并添加不同的代理。

**注意** - ~2GB代理消耗= 45 $Grass代币 = 约90美元（根据以往趋势和第一阶段用户的数据）。

![image](https://github.com/Solana0x/getgrass/assets/142747768/27b7b243-07cc-4e66-9f23-1a6091702e0d)

## 获取帮助请联系：`0xphatom` 在Discord上 https://discord.com/users/979641024215416842

# 社交平台

- **Telegram** - [https://t.me/phantomoalpha](https://t.me/phantomoalpha) 
- **Discord** - [https://discord.gg/pGJSPtp9zz](https://discord.gg/pGJSPtp9zz)
