## <a name="validating-the-role-within-power-bi-desktop"></a>Power BI Desktop 내에서 역할 유효성 검사
사용자의 역할을 만든 후에 Power BI Desktop 내에서 역할의 결과를 테스트할 수 있습니다. 이를 수행하려면 **역할로 보기**를 선택합니다.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

**역할로 보기** 대화 상자를 사용하여 해당 특정 사용자 또는 역할에 대해 표시되는 보기를 변경할 수 있습니다. 만든 역할을 볼 수 있습니다.

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

만든 역할을 선택한 다음, **확인**을 선택하여 보고 있는 내용에 해당 역할 내용을 적용합니다. 보고서는 해당 역할과 관련된 데이터만 렌더링합니다.

또한 **다른 사용자**를 선택하고 지정된 사용자를 제공할 수 있습니다. Power BI 서비스가 사용하는 기능으로서 UPN(사용자 계정 이름)을 제공하는 것이 좋습니다. **확인**을 선택하면 보고서는 사용자가 볼 수 있는 내용에 따라 렌더링합니다. 

![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

> [!NOTE]
> Power BI Desktop 내에서 DAX 식을 기반으로 하는 동적 보안을 사용하는 경우 서로 다른 결과만 표시됩니다.
> 
> 

