
    # 定义网络接口和 IP 地址范围
    $interfaceAlias = "以太网"  # 请根据实际网络接口名称进行更改
    $startIp = "192.168.1.2"     # 起始 IP 地址
    $endIp = "192.168.1.254"      # 结束 IP 地址
    $prefixLength = 24            # 子网掩码
    
    # 获取起始和结束地址的最后一段
    $startLastOctet = [int]($startIp.Split('.')[-1])
    $endLastOctet = [int]($endIp.Split('.')[-1])
    $baseIp = $startIp.Substring(0, $startIp.LastIndexOf('.') + 1)
    
    # 循环添加 IP 地址
    for ($i = $startLastOctet; $i -le $endLastOctet; $i++) {
        $ipAddress = "$baseIp$i"
        try {
            # 添加 IP 地址
            New-NetIPAddress -IPAddress $ipAddress -PrefixLength $prefixLength -InterfaceAlias $interfaceAlias -ErrorAction Stop
            Write-Host "成功添加 IP 地址: $ipAddress"
        } catch {
            Write-Host "无法添加 IP 地址: $ipAddress，错误信息: $_"
        }
    }
  
1.打开 PowerShell，以管理员身份运行。

2.将上面的脚本复制并粘贴到 PowerShell 窗口中。

3.根据需要修改 $interfaceAlias 变量，以匹配你的实际网络接口名称（可以通过运行 Get-NetAdapter 来查看可用的网络接口）。

4.运行脚本后，它将根据指定的 IP 范围和掩码批量添加 IP 地址。
