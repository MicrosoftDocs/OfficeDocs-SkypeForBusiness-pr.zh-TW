---
title: 在商務用 Skype Server 中建立或修改未指派的號碼範圍
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在商務用 Skype Server 企業語音中建立、修改或刪除宣告應用程式的未指派號碼範圍。 這會影響如何處理未指派號碼的呼叫。
ms.openlocfilehash: 10e65d6202babd0c15fe569c71f6e8a84b301eb7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410546"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改未指派的號碼範圍
 
在商務用 Skype Server 企業語音中建立、修改或刪除宣告應用程式的未指派號碼範圍。 這會影響如何處理未指派號碼的呼叫。
  
商務用 Skype Server 可讓您瞭解對您的組織有效但未指派給使用者或電話之電話號碼的來電所發生的情況。 若要處理這類通話，您可以設定未指派的號碼表。 您可以使用表格將通話路由傳送至宣告應用程式或 Exchange UM 伺服器。
  
設定未指派號碼表的方式取決於其使用方式。 您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。 未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。 如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。 如果您在表格中包含未指派的副檔名，您可以修改針對特定數位所發生的動作。 例如，如果您變更客戶服務服務台的分機號碼，您可以在資料表中包含舊的客戶服務號碼，然後將其指派給提供新號碼的宣告。
  
## <a name="configure-unassigned-phone-numbers"></a>設定未指派的電話號碼

使用下列其中一個程式來設定宣告應用程式的未指派號碼範圍。
  
> [!IMPORTANT]
> 在您設定未指派的號碼表之前，您的系統必須已定義宣告，或是已設定 Exchange 整合通訊 (UM) 自動語音應答。 
  
> [!TIP]
> 當某人呼叫未指派的號碼時，商務用 Skype Server 會從上到下搜尋未指派號碼表格，並使用第一個相符的範圍。 因此，應為表格中的最後一個範圍指定您想要執行做為最後一個手段的動作。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>若要使用商務用 Skype Server 控制台設定未指派的電話號碼

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左導覽列中，依序按一下 [ **語音功能**] 和 [ **未指派的號碼**]。
    
4. 在 [ **未指派的號碼** ] 頁面上，執行下列其中一項操作：
    
   - 若要建立新的號碼範圍，請按一下 [ **新增**]。 在 **[名稱]** 中，輸入此號碼範圍的識別名稱。
    
     > [!NOTE]
     > 在您認可新的未指派號碼範圍至資料庫之後，就無法變更此名稱。 
  
   - 若要修改現有的號碼範圍，請在 [搜尋] 欄位中輸入編號範圍的全部或部分名稱。 在產生的號碼範圍清單中，按一下您想要的名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在第一個 **[號碼範圍]** 欄位中輸入範圍的開始號碼，在第二個 **[號碼範圍]** 欄位中輸入範圍的結束號碼。
    
   - 該範圍的起始號碼必須小於或等於範圍的結束號碼。
    
   - 如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。
    
   - 此數位必須符合正則運算式 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。 這表示數位可以以字串 `tel:` 開頭 (如果您未指定該字串，將會自動為您新增) 、加號 (+) 及數位1到9。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。
    
6. 在 **[宣告服務]** 中，執行下列其中一個動作： 
    
   - 按一下 **[宣告]**。
    
   - 按一下 **[Exchange UM]**。
    
7. 如果您在上一個步驟按了 **[宣告]**，請執行下列動作：
    
    a. 在 **[目的地伺服器的 FQDN]** 下方按一下 **[選取]**，按一下執行宣告應用程式之應用程式服務的服務 ID (此服務會處理此未指派號碼範圍的來電)，然後按一下 **[確定]**。
    
    b. 在 **[宣告]** 中，按一下要針對此未指派號碼範圍播放的宣告。
    
8. 如果您在上一個步驟按了 **[Exchange UM]**，請在 **[自動語音應答電話號碼]** 下方按一下 **[選取]**，按一下要用於此未指派號碼範圍的電話號碼，然後按一下 **[確定]**。
    
9. 按一下 **[確定]**。
    
10. 在 [ **未指派的號碼** ] 頁面上，確定未指派的號碼範圍以您想要的順序排列。 若要變更某個範圍在表格中的位置，請在範圍清單中按一下一個或多個連續的名稱，然後按一下向上鍵或向下箭號。
    
    > [!TIP]
    > 商務用 Skype Server 會從上到下搜尋未指派號碼表格，並使用符合未指派號碼的第一個範圍。 如果您有重疊的範圍，且有一個範圍指定最後採取的動作，請確定該範圍位於清單底部。 
  
11. 當您以您想要的順序排列未指派的號碼範圍時，請按一下 [ **全部認可**]。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>若要使用商務用 Skype Server 管理命令介面設定未指派的電話號碼

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 使用 **New-CsUnassignedNumber** 建立新的未指派號碼範圍。 使用 **Set-CsUnassignedNumber** 修改現有的未指派號碼範圍。
    
    > [!TIP]
    > 如果您有重疊的範圍，且想要依特定順序套用範圍，請包含 Priority 參數。 具有最高優先順序的範圍會套用至通話。 值0代表最高優先順序。
  
    在命令列中，執行下列其中一項操作：
    
   - 若要建立宣告服務的號碼範圍，請執行：
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 或者，若要為 Exchange UM 自動語音應答建立號碼範圍，請執行：
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     例如：
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     或
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     下列範例會顯示如何修改現有未指派號碼範圍中的號碼：
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>刪除 unnasigned 號碼範圍

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>若要使用商務用 Skype Server 控制台刪除未指派的號碼範圍

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左側導覽列中，依序按一下 **[語音功能]** 和 **[未指派的號碼]**。
    
4. 在 [ **未指派的號碼** ] 頁面上的搜尋欄位中，輸入您要刪除之未指派號碼範圍的全部或部分名稱。
    
5. 在產生的編號範圍清單中，按一下名稱，按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
6. 按一下 [ **全部認可**]。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>若要使用商務用 Skype Server 管理命令介面來刪除未指派的號碼範圍

1. 以 **委派安裝許可權** 中所述，以 RTCUniversalServerAdmins 群組成員的身分或必要使用者權限的方式，登入安裝商務用 Skype Server 管理命令介面的電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 在命令列中輸入：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    例如：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 如需更多選項的詳細資訊，請參閱 [Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>另請參閱

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)