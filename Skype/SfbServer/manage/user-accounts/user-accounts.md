---
title: 管理商務用 Skype Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 本文中的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817053"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>管理商務用 Skype Server 的使用者帳戶

本文中的各節說明如何啟用、暫時停用或移除商務用 Skype Server 中的 Active Directory 使用者。

如需如何啟用 Active Directory 使用者的相關資訊，請參閱[建立新的使用者帳戶](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)。 如需如何刪除 Active Directory 使用者的相關資訊，請參閱[刪除使用者帳戶](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)。

當商務用 Skype 使用為最低時，這些程式應該在 [維護] 視窗中執行。 無論是在每天或每週排程上完成，都將由貴組織的需求決定。

本文包含下列程式：

- [搜尋一或多位使用者](user-accounts.md#Search)

- [新增並啟用新的商務用 Skype Server 使用者](user-accounts.md#Add)

- [停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶](user-accounts.md#Disable)

- [停用企業語音的使用者](user-accounts.md#Disable_EV)

- [使用商務用 Skype Server Management Shell 移除使用者帳戶](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>搜尋一或多位使用者
<a name="Search"> </a>

您可以使用搜尋查詢的結果來設定商務用 Skype Server 的 Active Directory 使用者。 您可以依顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）來搜尋使用者。

您可以使用商務用 Skype Server 的 [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。 下列程式說明如何使用商務用 Skype Server 的 [控制台] 來搜尋使用者。

> [!NOTE]
> 在具有中央林拓撲的環境中，當您使用使用者的電子郵件地址搜尋使用者時，搜尋結果可能不正確。 相反地，您可以透過指定 SIP 位址首碼（例如 sip： name、新增搜尋篩選器，然後選取包含部分電子郵件地址的 SIP 位址）來搜尋使用者，或使用**move-csuser** Cmdlet。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**使用者**]。

4. 在 [**搜尋使用者**] 方塊中，輸入您要搜尋之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或行 URI，然後按一下 [**尋找**]。

5. 可選指定額外的搜尋準則以縮小結果範圍：

   是. 按一下 [**搜尋結果**] 上方畫面右上角的展開箭號按鈕，然後按一下 [**新增篩選**]。

   乙. 輸入使用者屬性或按一下下拉式清單中的箭號，以選取使用者屬性。

   c-clip. 在 [**等於**] 清單中，按一下 [**等於**或**不等於**]。

   希望. 在文字方塊中，輸入您要用來篩選搜尋結果的搜尋準則，然後按一下 [**尋找**]。

6. 搜尋結果會顯示在 [**搜尋結果**] 下。 您可以選取清單中的任何或所有使用者，並在您選取的使用者上執行設定工作。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新增並啟用新的商務用 Skype Server 使用者
<a name="Add"> </a>

在 Active Directory 使用者和電腦中啟用使用者帳戶之後，您就可以使用商務用 Skype Server 的 [控制台]，透過將 Active Directory 使用者新增至商務用 Skype 伺服器來建立並啟用新的商務用 Skype Server 使用者帳戶。

您也可以使用 Cmdlet，特別是[Enable-move-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**使用者**]。

4. 按一下 [**啟用使用者**]。

5. 在 [**新的 Lync Server 使用者**] 對話方塊中 **，按一下 [新增]**。

6. 在 [**搜尋使用者**] 方塊中，輸入所有或第一個部分的名稱、顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、電子郵件地址、使用者主體名稱（UPN），或您想要的 Active Directory 使用者帳戶的電話號碼，然後按一下 [**尋找**]。

7. 在表格中，選取您要新增至商務用 Skype Server 的帳戶，然後按一下 **[確定]**。

8. 將使用者指派至 [泳池]，指定任何其他詳細資料，然後將原則指派給您想要的使用者，然後按一下 [**啟用**]。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶
<a name="Disable"> </a>

您可以使用下列程式，在商務用 Skype Server 中停用先前啟用的使用者帳戶，而不會遺失您針對使用者帳戶所設定的商務用 Skype 伺服器設定。 因為您不會遺失商務用 Skype Server 的使用者帳戶設定，所以您可以重新啟用先前已啟用的使用者帳戶，而不需重新設定使用者帳戶。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**使用者**]。

4. 在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5. 在表格中，按一下您要停用或重新啟用的使用者帳戶。

6. 在 [**動作**] 功能表上，執行下列其中一項操作：

   - 若要暫時停用商務用 Skype Server 的使用者帳戶，請按一下 [**針對 Lync Server 暫時停**用]。

   - 若要啟用商務用 Skype Server 的使用者帳戶，請按一下 [**針對 Lync Server 重新啟用**]。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows Powershell 來停用或重新啟用使用者帳戶

使用者帳戶可以暫時停用，稍後再使用**move-csuser** Cmdlet 重新啟用。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。

### <a name="to-disable-a-user-account"></a>停用使用者帳戶

- 若要暫時停用使用者帳戶，請將 Enabled 屬性的值設為 False （$False）。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>若要重新啟用使用者帳戶

- 若要重新啟用已停用的使用者帳戶，請將 Enabled 屬性的值設定為 True （$True）。 例如：

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

如需詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 的說明主題。

## <a name="disable-a-user-for-enterprise-voice"></a>停用企業語音的使用者
<a name="Disable_EV"> </a>

使用下列程式來停用商務用 Skype Server 啟用的使用者帳戶的企業語音。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>針對企業語音停用使用者帳戶

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**使用者**]。

4. 在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5. 在表格中，按一下您要為企業語音啟用的使用者帳戶。

6. 按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

7. 在 [**編輯 Lync Server 使用者**] 頁面的 [**電話**] 底下，按一下 [**企業語音**] 以外的任何選項。

    > [!NOTE]
    > 若要使用 Lync 限制使用者進行音訊或視頻通話，請在 [**電話**] 底下，按一下 [**音訊/視頻已停用**]。

8. 按一下 [認可]****。

使用者現在無法使用企業語音功能。 相關資訊： <br/>[企業語音與行動性](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [在商務用 Skype Server 中啟用企業語音的使用者](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [商務用 Skype Server 管理命令介面](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 移除使用者帳戶
<a name="Remove"> </a>

您可以使用下列程式，在商務用 Skype Server 中移除先前新增的使用者帳戶。

> [!NOTE]
> 移除使用者將會導致您遺失任何您為使用者帳戶所設定的設定。 如果您想改為暫時停用使用者帳戶，請參閱[停用或重新啟用先前針對商務用 Skype Server 啟用的使用者帳戶](user-accounts.md#Disable)。

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3. 在左側導覽列中，按一下 [**使用者**]。

4. 在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5. 在表格中，按一下您要移除的使用者帳戶。

6. 在 [**動作**] 功能表上，選取 [**從 Lync Server 移除**]，隨後便會出現一個對話方塊。

7. 從對話方塊中，選取 **[確定]** 以移除使用者。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>使用 Windows Powershell Cmdlet 移除使用者帳戶

您可以使用 Disable Move-csuser Cmdlet 來移除使用者帳戶。 此 Cmdlet 可從商務用 Skype Server Management 命令介面或從遠端會話 Windows PowerShell 執行。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。

### <a name="to-remove-a-user-account"></a>移除使用者帳戶
若要移除使用者帳戶，請使用 Disable-Move-csuser Cmdlet。 例如：

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

如需詳細資訊，請參閱[Disable move-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) Cmdlet 的說明主題。

## <a name="see-also"></a>另請參閱
<a name="Remove"> </a>

[Enable-Move-csuser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-Move-csuser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
