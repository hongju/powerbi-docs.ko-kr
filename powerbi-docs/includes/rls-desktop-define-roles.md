## <a name="define-roles-and-rules-within-power-bi-desktop"></a>Power BI Desktop 내에서 역할 및 규칙 정의
Power BI Desktop 내에서 역할 및 규칙을 정의할 수 있습니다. Power BI에 게시할 때 역할 정의도 게시됩니다.

보안 역할을 정의하기 위해 다음을 수행할 수 있습니다.

1. Power BI Desktop 보고서에 데이터를 가져 오거나 DirectQuery 연결을 구성합니다.
   
   > [!NOTE]
   > Analysis Services 라이브 연결을 위해 Power BI Desktop 내에서 역할을 정의할 수 없습니다. Analysis Services 모델 내에서 이를 수행해야 합니다.
   > 
   > 
2. **모델링** 탭을 선택합니다.
3. **역할 관리**를 선택합니다.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. **만들기**를 선택합니다.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. 역할의 이름을 입력합니다. 
6. DAX 규칙을 적용하려는 표를 선택합니다.
7. DAX 식을 입력합니다. 이 식은 true 또는 false를 반환해야 합니다. 예: [엔터티 ID] = "Value"입니다.
   
   > [!NOTE]
   > 이 식에 *username()* 을 사용할 수 있습니다. *username()* 은 Power BI Desktop 내에서 *도메인\사용자 이름*의 형식을 취합니다. Power BI 서비스 내에서는 사용자의 UPN 형식이 됩니다. 대신 항상 사용자 계정 이름 형식으로 사용자를 반환하는 *userprincipalname()* 을 사용할 수 있습니다.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. DAX 식을 만든 후 식의 유효성을 검사하기 위해 식 상자 위에 확인란을 선택할 수 있습니다.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. **저장**을 선택합니다.

Power BI Desktop 내에서는 사용자를 역할에 할당할 수 없습니다. 이 작업은 Power BI 서비스 내에서 수행됩니다. *username()* 또는 *userprincipalname()* DAX 함수를 사용하고 적절한 관계를 구성하여 Power BI Desktop 내에서 동적 보안을 사용할 수 있습니다.

