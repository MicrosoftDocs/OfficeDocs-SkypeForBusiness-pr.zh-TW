---
title: 在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN
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
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 摘要：為商務用 Skype Server 設定使用者的電話撥入式會議 PIN。
---

# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>在商務用 Skype Server 中設定使用者的電話撥入式會議 PIN
 
**總結：** 設定使用者的電話撥入式會議 PIN 以供商務用 Skype Server。
  
若要將電話撥入式會議加入為已驗證的使用者，具有 Active Directory 網域服務 (AD DS) 認證的商務用 Skype Server 使用者必須有個人識別碼 (PIN) 。 如果使用者忘記電話撥入式會議 PIN，或是未使用商務用 Skype Server 設定 pin，您可以從商務用 Skype Server 控制台設定使用者的 pin 碼。 您可以自動產生 PIN 碼，也可以手動建立 PIN 碼。
  
> [!NOTE]
> PIN 碼的特定特性（如其最小長度）可以設定為原則。 除了通用原則之外，您還可以為個別網站或使用者設定 PIN 原則。 
  
### <a name="to-set-a-users-pin"></a>設定使用者的 PIN

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 使用下列其中一種方法，找到使用者：
    
   - 在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。
    
   - 如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。
    
5. (選用) 指定其他搜尋條件，縮減結果：
    
   a. 按一下 **[新增篩選]**。
    
   b. 輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。
    
   c. 在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。
    
   d. 視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。
    
    > [!TIP]
    > 若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。 
  
   e. 按一下 [尋找]。
    
    > [!NOTE]
    > 如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行] 和 [解除鎖定 PIN]。 
  
6. 按一下搜尋結果中的使用者，按一下 [ **動作**]，然後按一下 [ **設定 PIN**]。
    
7. 在 [ **設定 PIN** ] 對話方塊中，執行下列其中一項動作：
    
   - 若要允許商務用 Skype Server 產生使用者的 pin，請選取 [**自動產生有效的 pin** (預設) ]。
    
   - 若要建立您自己的 PIN，請按一下 [ **手動輸入特定的 pin**]，然後按一下文字方塊，然後輸入符合 pin 原則設定中所指定之 pin 碼需求的 pin 碼。
    
8. 按一下 [確定]。
    
9. 在 [ **設定 PIN**] 中，執行下列其中一項動作： 
    
   - 選取 [ **顯示 pin** ] 核取方塊以查看 pin，然後複製 pin 碼，並使用組織的慣用方法將其傳送給使用者。
    
   - 按一下 [ **開啟我的電子郵件應用程式]，將新的 PIN 碼傳送給使用者** ，以便透過電子郵件傳送 pin 碼。 如果 Microsoft Office Outlook 是您的電子郵件客戶程式，PIN 碼會自動複製到新的電子郵件中。 如果您使用不同的電子郵件用戶端，請選取 [ **顯示 pin** ] 核取方塊以查看 pin 碼，然後將其複製到您的電子郵件訊息中。
    
10. 按一下 **[關閉]**。
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指派使用者 PIN

您也可以使用 Set-CsClientPin Cmdlet 來指派 PIN 碼號碼。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>若要自動將 PIN 碼指派給使用者

下列命令會將 PIN 碼指派給使用者 Ken Myer。 因為未包含 pin 參數，所以商務用 Skype Server 會自動產生並指派 pin 碼號碼。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>若要將特定 PIN 碼號碼指派給使用者

這個命令會使用 Pin 參數，將 PIN 碼121989指派給使用者 Ken Myer。
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

如需詳細資訊，請參閱 [unlock-csclientpin](/powershell/module/skype/set-csclientpin?view=skype-ps) Cmdlet 的 [說明] 主題。
