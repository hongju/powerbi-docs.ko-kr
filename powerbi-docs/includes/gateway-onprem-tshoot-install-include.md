## <a name="update-to-the-latest-version"></a>최신 버전으로 업데이트
게이트웨이 버전이 만료되면 많은 문제가 발생할 수 있습니다.  최신 버전을 사용하고 있는지 확인하는 것이 좋습니다.  한 달 이상 게이트웨이를 업데이트하지 않은 경우에는 최신 버전 게이트웨이를 설치하고 문제를 재현할 수 있는지 확인할 수 있습니다.

## <a name="common-issues"></a>일반적인 문제
여기에는 인터넷 액세스를 제한하는 환경에서 많은 고객에게 도움이 되었던 몇 가지 일반적인 문제와 해결책이 나와 있습니다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>프록시 서버에 대한 인증
프록시는 도메인 사용자 계정으로부터 인증이 필요할 수 있습니다. 기본적으로 게이트웨이는 Windows 서비스 로그온 사용자용 서비스 SID를 사용합니다. 도메인 사용자에 대한 로그온 사용자를 변경하면 이 작업이 수월해집니다. 자세한 내용은 [게이트웨이 서비스 계정을 도메인 사용자로 변경](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)을 참조하세요.

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>프록시는 포트 80 및 443 트래픽만 허용합니다.
일부 프록시는 포트 80 및 443에 대한 트래픽을 제한합니다. 기본적으로 Azure 서비스 버스와의 통신은 443 이외의 포트에서 발생합니다.

게이트웨이가 직접 TCP 대신 HTTPS를 사용하여 Azure Service Bus와 통신하도록 강제할 수 있습니다. *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* 파일을 수정해야 합니다. 값을 `AutoDetect`에서 `Https`로 변경합니다. 이 파일은 기본적으로 *C:\Program Files\On-premises data gateway* 에 있습니다.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>설치
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>오류: 사용자를 그룹에 추가하지 못했습니다.  (-2147463168 PBIEgwService 성능 로그 사용자)
도메인 컨트롤러에 게이트웨이를 설치하려고 하는 경우 이 오류가 표시될 수 있습니다. 도메인 컨트롤러에는 배포할 수 없습니다. 도메인 컨트롤러가 아닌 컴퓨터에서 게이트웨이를 배포해야 합니다.

