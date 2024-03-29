---
title: 管理商務用 Skype Server 的使用者帳戶
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各節說明如何啟用、暫時停用或移除 Active Directory 使用者商務用 Skype Server。
---

# <a name="manage-user-accounts-for-skype-for-business-server"></a>管理商務用 Skype Server 的使用者帳戶

本文中的各節說明如何啟用、暫時停用或移除 Active Directory 使用者商務用 Skype Server。

如需如何啟用 Active Directory 使用者的詳細資訊，請參閱 [建立新的使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))。 如需如何刪除 Active Directory 使用者的詳細資訊，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。

當商務用 Skype 使用狀況最低時，應在維護時段內執行這些程式。 在每日或每週排程上進行的工作是否取決於組織的需求。

本文包含下列程式：

- [搜尋一或多個使用者](#search-for-one-or-more-users)

- [新增及啟用新的商務用 Skype Server 使用者](#add-and-enable-a-new-skype-for-business-server-user)

- [停用或重新啟用商務用 Skype Server 的使用者帳戶](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [停用企業語音的使用者](#disable-a-user-for-enterprise-voice)

- [使用商務用 Skype Server 管理命令介面移除使用者帳戶](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>搜尋一或多個使用者

您可以使用搜尋查詢的結果，設定 Active Directory 使用者商務用 Skype Server。 您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。

您可以使用商務用 Skype Server 控制台] 或 [Active Directory 使用者和電腦] 嵌入式管理單元來搜尋使用者。 下列程式說明如何使用商務用 Skype Server 控制台來搜尋使用者。

> [!NOTE]
> 在具有中央樹系拓撲的環境中，當您使用使用者的電子郵件地址來搜尋使用者時，搜尋結果可能不准確。 您可以改為指定 SIP 位址首碼 (例如 sip:name) 來進行搜尋、新增搜尋篩選並選取包含部分電子郵件位址的 SIP 位址，或使用 **Get-CSUser** Cmdlet。

### <a name="search-for-users-using-the-new-control-panel"></a>使用 [新增控制台] 搜尋使用者 

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 [ **使用者** ] 頁面上的 **搜尋** 方塊中，輸入您要搜尋的顯示名稱全部或第一個部分，然後按 **enter**。

5. (選用) 指定其他搜尋條件，縮減結果：

    1. 按一下 [ **搜尋** ] 方塊旁的 [篩選] 按鈕。

    2. 在出現的 [ **篩選** ] 面板中，按一下下拉式清單中的箭號，選取所需的 user 屬性。

    3. 按一下下拉式運算子清單中的箭號，以選取必要的運算子。

    4. 在文字方塊中，輸入您要用來篩選搜尋結果的搜尋準則，然後按一下 **[確定]**。

6. 搜尋結果會顯示在 [ **使用者** ] 頁面上。 您可以選取清單中任一或全部使用者，然後對所選使用者執行設定工作。

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="search-for-users-using-the-legacy-control-panel"></a>使用舊版控制台搜尋使用者 

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 **[搜尋使用者]** 方塊中，輸入您要搜尋之使用者帳戶的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或線路 URI 的全部或頭幾個字，然後按一下 **[尋找]**。

5. (選用) 指定其他搜尋條件，縮減結果：

    1. 按一下畫面右上角就在 **[搜尋結果]** 上方的展開箭頭，然後按一下 **[新增篩選]**。

    2. 輸入使用者屬性或按一下下拉式清單中的箭號，以選取使用者屬性。

    3. 在 [ **等於** ] 清單中，選取 [ **等於** ] 或 [ **不等於**]。

    4. 在文字方塊中，輸入您要用來篩選搜尋結果的搜尋條件，然後按一下 **[尋找]**。

6. 搜尋結果會出現在 **[搜尋結果]** 下方。您可以選取清單中任一或全部使用者，然後對所選使用者執行設定工作。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新增及啟用新的商務用 Skype Server 使用者

在 [Active directory 使用者及電腦] 中啟用使用者帳戶之後，您可以使用商務用 Skype Server 控制台，將 Active Directory 使用者新增至商務用 Skype Server，以建立及啟用新的商務用 Skype Server 使用者帳戶。

您也可以使用 Cmdlet，特別是 [Enable-get-csuser](/powershell/module/skype/enable-csuser)。

### <a name="add-a-user-using-the-new-control-panel"></a>使用 [新增控制台] 新增使用者 

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。

3. 流覽至 [**使用者**  >  ]**啟用使用者**，然後按一下 [**新增**]。

4. 在 **搜尋** 方塊中，輸入顯示名稱的全部或第一個部分，然後按一下 [ **尋找**]。

5.  (選用) 若要指定其他使用者準則，請按一下 [ **+ 新增篩選**]，然後選取必要的使用者屬性，選取運算子，然後輸入值。 按一下 [尋找]。

6. 在表格中，選取您要新增商務用 Skype Server 的帳戶，然後按一下 **[確定]**。

7. 將使用者指派至集區、指定其他詳細資料，並將必要的原則指派給使用者，然後按一下 [ **啟用**]。

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="add-a-user-using-the-legacy-control-panel"></a>使用舊版控制台新增使用者 

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 流覽至  >  **[使用者]**[**啟用使用者**  >  ] [**新增 Lync Server 使用者**]，然後按一下 [**新增]。**

6. 在 [搜尋使用者] 方塊中，輸入您要找的 Active Directory 使用者帳戶的名稱、顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、電子郵件地址、使用者主要名稱 (UPN) 或電話號碼的全部或頭幾個字，然後按一下 [尋找]。

7. 在表格中，選取您要新增商務用 Skype Server 的帳戶，然後按一下 **[確定]**。

8. 指派使用者至集區、指定其他詳細資料，並指派原則給您要的使用者，然後按一下 **[啟用]**。

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>停用或重新啟用商務用 Skype Server 的使用者帳戶

您可以使用下列程式在商務用 Skype Server 中停用先前啟用的使用者帳戶，而不會丟失您為使用者帳戶所設定的商務用 Skype Server 設定。 因為您不會遺失商務用 Skype Server 使用者帳戶設定，所以您可以重新啟用先前啟用的使用者帳戶，而不必重新設定使用者帳戶。

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>使用 [新增控制台] 停用或重新啟用使用者帳戶

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 [ **使用者** ] 頁面上的 **搜尋** 方塊中，輸入所有或第一個顯示名稱的部分，然後按 **enter**。

5. 在表格中，按兩下您要停用或重新啟用的使用者帳戶。
    1. 在出現的窗格中，若要暫時停用商務用 Skype Server 的使用者帳戶，請選取 [**停用使用者**]。 在出現的窗格中，按一下 [ **儲存**]。
    2. 若要重新啟用商務用 Skype Server 的使用者帳戶，請選取面板中的 [**重新啟用使用者**]。 在出現的下一個窗格中，按一下 [ **儲存**]。

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>使用舊版控制台停用或重新啟用使用者帳戶

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 **[搜尋使用者]** 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 **[尋找]**。

5. 按一下表中您想要停用或重新啟用的使用者帳戶。

6. 在 **[動作]** 功能表上，執行下列其中一項：
   1. 若要暫時停用商務用 Skype Server 的使用者帳戶，請選取 [**暫時停用 Lync Server**]。
   2. 若要為商務用 Skype Server 啟用使用者帳戶，請選取 [**重新啟用 Lync Server**]。
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>使用 Windows PowerShell 停用或重新啟用使用者帳戶

您可以暫時停用使用者帳戶，然後再使用 **Set-CsUser** Cmdlet 重新啟用使用者帳戶。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。

### <a name="to-disable-a-user-account-using-windows-powershell"></a>使用 Windows PowerShell 停用使用者帳戶

- 若要暫時停用使用者帳戶，請將 enabled 屬性的值設為 False ($False) 。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>使用 Windows PowerShell 重新啟用使用者帳戶

- 若要重新啟用已停用的使用者帳戶，請將 enabled 屬性的值設為 True ($True) 。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

如需詳細資訊，請參閱 [Set-CsUser](/powershell/module/skype/set-csuser) Cmdlet 的 [說明] 主題。

## <a name="disable-a-user-for-enterprise-voice"></a>停用企業語音的使用者

使用下列程式可針對商務用 Skype Server 啟用的使用者帳戶停用企業語音。

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>使用新控制台停用企業語音的使用者

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。

3. 在左窗格中，按一下 [ **使用者**]。

4. 在 **搜尋** 方塊中，輸入顯示名稱的全部或第一個部分，然後按一下 [ **尋找**]。

5. 在表格中，按兩下您要為企業語音停用的使用者帳戶。

6. 在出現的窗格中，按一下 [ **指派的原則**] 旁邊的鉛筆圖示。

7. 在 [**指派的原則**] 面板的 [**電話語音**] 下，按一下下拉式清單中的 [**企業語音** 以外的任何選項。

8. 按一下 **[儲存]**。

    > [!NOTE]
    > 若要限制使用者進行音訊或視頻通話，請按一下 [ **電話語音**] 下的 [ **Audio/Video 停用**]。

使用者現在無法使用企業語音功能。 

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>使用舊版控制台停用企業語音的使用者帳戶

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左窗格中，按一下 [ **使用者**]。

4. 在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。

5. 在表格中，按一下您要為企業語音啟用的使用者帳戶。

6. 在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

7. 在 [**編輯 Lync Server 使用者**] 頁面的 [**電話語音**] 下，按一下 [**企業語音** 以外的任何選項。

    > [!NOTE]
    > 若要使用 Lync 限制使用者進行音訊或視頻通話，請在 [ **電話語音**] 下，按一下 [ **音訊/視頻已停用**]。

8. 按一下 **[認可]**。

使用者現在無法使用企業語音功能。

相關資訊： <br/>[企業語音和行動性](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [在商務用 Skype Server 中為使用者啟用企業語音](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [商務用 Skype Server 管理命令介面](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面移除使用者帳戶

您可以使用下列程式，在商務用 Skype Server 中移除之前新增的使用者帳戶。

> [!NOTE]
> 移除使用者會造成您遺失該使用者的所有設定。 若要暫時停用使用者帳戶，請參閱[停用或重新啟用先前為商務用 Skype Server 啟用的使用者帳戶](#disable-or-re-enable-a-user-account-for-skype-for-business-server)。

### <a name="remove-a-user-using-the-new-control-panel"></a>使用 [新增控制台] 移除使用者

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。
 
2. 使用指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 **搜尋** 方塊中，輸入顯示名稱的全部或第一個部分，然後按一下 [ **尋找**]。

5. 在表格中，按兩下您要移除的使用者帳戶。

6. 在出現的窗格中，按一下 [ **移除使用者**]。 在出現的下一個窗格中，按一下 **[確定]**。

> [!NOTE]
> 無法使用商務用 Skype Server 2015 的 [新增控制台]。

### <a name="remove-a-user-using-the-legacy-control-panel"></a>使用舊版控制台移除使用者

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3. 在左窗格中，選取 [ **使用者**]。

4. 在 [ **搜尋使用者** ] 方塊中，輸入您要移除之使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) ，然後按一下 [ **尋找**]。

5. 在表中按一下您想要移除的使用者帳戶。

6. 選取 [動作] 功能表中的 [從 Lync Server 移除]，隨即顯示對話方塊。

7. 選取對話方塊中的 [確定] 以移除使用者。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>移除具有 Windows PowerShell Cmdlet 的使用者帳戶

您可以使用 Disable-CsUser Cmdlet 來移除使用者帳戶。 您可以從商務用 Skype Server 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。

若要移除使用者帳戶，請使用 Disable-CsUser Cmdlet。例如：

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

執行此命令之後，將無法再重新啟用帳戶及其設定。所以請使用 Enable-CsUser Cmdlet 為 Ken Myer 建立新帳戶。

如需詳細資訊，請參閱 [get-csuser 指令程式](/powershell/module/skype/disable-csuser) 的 [說明] 主題。

## <a name="see-also"></a>另請參閱

[Enable-Get-csuser](/powershell/module/skype/enable-csuser)

[停用 Get-csuser](/powershell/module/skype/disable-csuser)
