## <a name="firewall-or-proxy"></a>방화벽 또는 프록시
게이트웨이에 대한 프록시 정보 제공에 대한 내용은 [Power BI Gateway에 대한 프록시 설정 구성](../service-gateway-proxy.md)을 참조하세요.

PowerShell 프롬프트에서 [Test-NetConnection](https://technet.microsoft.com/library/dn372891.aspx) 명령을 실행하여 방화벽 또는 프록시에서 연결을 차단하고 있는지 테스트할 수 있습니다. Azure Service Bus에 대한 연결을 테스트합니다. 네트워크 연결만을 테스트하며 클라우드 서버 서비스 또는 게이트웨이와 전혀 관계가 없습니다. 컴퓨터가 실제로 인터넷에 연결될 수 있는지 확인하는 데 도움이 됩니다.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection은 Windows Server 2012 R2 이상에서만 사용할 수 있습니다. Windows 8.1 이상에서도 사용할 수 있습니다. 이전 OS 버전에서는 Telnet을 사용하여 포트 연결을 테스트할 수 있습니다.
> 
> 

결과는 다음과 유사하게 나타납니다. 차이는 TcpTestSucceeded로 됩니다. **TcpTestSucceeded** 가 *true* 가 아닌 경우 방화벽으로 차단될 수 있습니다.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

철저히 하려는 경우 **ComputerName** 및 **포트** 값을 [포트](../service-gateway-onprem.md#ports)에 대해 나열된 값으로 대체합니다.

또한 방화벽은 Azure Service Bus가 Azure 데이터 센터에 대해 만드는 연결을 차단할 수 있습니다. 이 경우 해당 데이터 센터에 대한 지역의 IP 주소를 화이트 리스트(차단 해제)합니다. [여기](https://www.microsoft.com/download/details.aspx?id=41653)에서 Azure IP 주소의 목록을 가져올 수 있습니다.

