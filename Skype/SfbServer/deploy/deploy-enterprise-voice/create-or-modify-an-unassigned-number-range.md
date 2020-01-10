---
title: 在商務用 Skype Server 中建立或修改未指定的數位範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: 在商務用 Skype Server Enterprise Voice 中，建立、修改或刪除未指定的號碼範圍給宣告應用程式。 這會影響如何處理未指派數位的呼叫。
ms.openlocfilehash: c52cbf8e281307ad75023f3edc8b4ec1d77f4b42
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001663"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改未指定的數位範圍
 
在商務用 Skype Server Enterprise Voice 中，建立、修改或刪除未指定的號碼範圍給宣告應用程式。 這會影響如何處理未指派數位的呼叫。
  
商務用 Skype Server 可讓您說撥入電話號碼對您的組織有效，但不會指派給使用者或電話。 若要處理此類通話，您必須設定未指派的 [數位] 資料表。 您可以使用表格，將呼叫路由至宣告應用程式或 Exchange UM 伺服器。
  
設定未指派號碼表的方式取決於其使用方式。 您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。 未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。 如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。 如果您在表格中包含未指定的延伸，您可以修改針對特定數位所發生的動作。 例如，如果您變更客戶服務台的延伸，您可以在表格中包含舊的客戶服務編號，然後將它指派給提供新號碼的宣告。
  
## <a name="configure-unassigned-phone-numbers"></a>設定未指派的電話號碼

使用下列其中一個程式來設定宣告應用程式的未指派數量範圍。
  
> [!IMPORTANT]
> 在您設定 [未指派的號碼] 資料表之前，您的系統必須已定義宣告，或已設定 Exchange 整合通訊（UM）自動語音應答。 
  
> [!TIP]
> 當某人呼叫未指派的號碼時，商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表，並使用第一個相符的範圍。 因此，您想要執行的動作必須針對表格中的最後一個範圍指定，才能做為最後一個手段。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>使用商務用 Skype Server 的 [控制台] 來設定未指派的電話號碼

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱**委派設定許可權**。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**未指定的號碼**]。
    
4. 在 [**未指定的號碼**] 頁面上，執行下列其中一項操作：
    
   - 若要建立新的編號範圍，請按一下 [**新增**]。 在 [**名稱**] 中，輸入此數位範圍的識別名稱。
    
     > [!NOTE]
     > 在您將新的未指派的數位範圍提交至資料庫之後，您就無法變更此名稱。 
  
   - 若要修改現有的數位範圍，請在 [搜尋] 欄位中輸入全部或部分的數位範圍名稱。 在產生的數位範圍清單中，按一下您想要的名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在第一個 [**數位範圍**] 欄位中，輸入範圍的起始編號，然後在 [第二個**數位範圍**] 欄位中，輸入範圍的結束數位。
    
   - 該範圍的起始號碼必須小於或等於範圍的結束號碼。
    
   - 如果範圍的起始編號或範圍的結束數位包含分機號碼，則起始編號與範圍的結束數位都必須包含延伸，且起始編號和所需的延伸號碼必須是相同的。結束數位。
    
   - 這個數位必須符合正則運算式（電話：）嗎？（\+)?[1-9] \d{0,17}（; ext = [1-9] \d{0,9}）？。 這表示數位可能會從電話號碼開始：（如果您沒有指定該字串，會自動為您新增）、加號（+），以及1到9的數位。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。
    
6. 在 [**宣告服務**] 中，執行下列其中一項操作： 
    
   - 按一下 [**宣告**]。
    
   - 按一下 [ **EXCHANGE UM**]。
    
7. 如果您在上一個步驟中按一下 [**宣告**]，請執行下列動作：
    
    是. 在 [**目的地伺服器的 FQDN**] 底下，按一下 [**選取**]，然後按一下執行宣告應用程式的應用程式服務識別碼，該應用程式服務會處理撥入呼叫到此未指定號碼的範圍，然後按一下 **[確定]**。
    
    乙. 在 [**宣告**] 中，按一下要在此未指定編號範圍中播放的宣告。
    
8. 如果您在上一個步驟中按一下 [ **EXCHANGE UM**]，請在 [**自動語音應答電話號碼**] 底下，按一下 [**選取**]，然後按一下要用於此未指定號碼範圍的電話號碼，然後按一下 **[確定]**。
    
9. 按一下 [確定]****。
    
10. 在 [**未指定的號碼**] 頁面上，確定未指定的數位範圍是依您想要的順序排列。 若要變更範圍在表格中的位置，請在範圍清單中按一下一或多個連續的名稱，然後按一下向上箭號或向下箭號。
    
    > [!TIP]
    > 商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表，並使用符合未指定數位的第一個範圍。 如果您有重迭的範圍，且一個範圍指定了 [最後一個滑雪場] 動作，請確定該範圍位於清單底部。 
  
11. 當您以您想要的順序排列 [未指定的數位範圍] 時，請按一下 [**全部確認**]。
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>使用商務用 Skype Server Management Shell 來設定未指派的電話號碼

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝，如**委派設定許可權**中所述。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 使用 [**新-CsUnassignedNumber** ] 來建立新的 [未指定的數位範圍]。 使用 [**設定] CsUnassignedNumber**來修改現有的未指派數位範圍。
    
    > [!TIP]
    > 如果您有重迭的範圍，且想要以特定順序套用範圍，請包含 Priority 參數。 具有最高優先順序的範圍會套用至通話。 值0代表最高優先順序。
  
    在命令列上，執行下列其中一項操作：
    
   - 若要為宣告服務建立數位範圍，請執行：
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - 或者，若要建立 Exchange UM 自動語音應答的數位範圍，請執行：
    
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

     下列範例顯示如何修改現有未指定的數位範圍中的數位：
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>刪除 unnasigned 的數位範圍

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>使用商務用 Skype Server 的 [控制台] 刪除未指定的數位範圍

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱**委派設定許可權**。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**未指定的號碼**]。
    
4. 在 [**未指定的號碼**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除的未指派數位範圍的全部或部分名稱。
    
5. 在產生的數位範圍清單中，按一下名稱，按一下 [**編輯**]，然後按一下 [**刪除**]。
    
6. 按一下 [**全部確認**]。
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>若要使用商務用 Skype Server Management Shell 來刪除未指定的數位範圍

1. 登入商務用 Skype Server Management Shell 的電腦是以 RTCUniversalServerAdmins 群組的成員或必要的使用者權利來安裝，如**委派設定許可權**中所述。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令列中，輸入：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    例如：
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > 如需更多選項的詳細資訊，請參閱[移除-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps)。 
  
## <a name="see-also"></a>另請參閱

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
