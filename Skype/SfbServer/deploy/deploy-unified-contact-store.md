---
title: '在商務用 Skype Server 中部署整合連絡人存放區 '
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要：在商務用 Skype Server 中啟用整合連絡人存放區。
ms.openlocfilehash: 459626fe40f76cc19534aaff67d1b1b39c268469
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748829"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>在商務用 Skype Server 中部署整合連絡人存放區
 
**摘要：** 在商務用 Skype Server 中啟用整合連絡人存放區。
  
在商務用 Skype Server 中啟用整合連絡人存放區時，不需要任何拓撲設定。 若要為使用者啟用整合連絡人存放區：
  
- 啟用整合連絡人存放區原則 (預設為啟用)。
    
- 使用者使用商務用 Skype 至少一次登入。
    
在使用者的連絡人已遷移之後，當使用者使用商務用 Skype 登入時，使用者可以從商務用 Skype、Outlook 2013 或 Outlook 網頁存取中存取和管理商務用 Skype 連絡人。 使用者不必登入商務用 Skype 以從 Outlook 或 Outlook Web 存取管理其連絡人。
  
> [!IMPORTANT]
> 如果使用者在遷移之後從商務用 Skype 登入，則連絡人和群組可供使用且是最新的，但是使用者無法管理 (，例如新增、刪除、移動、標記、untag 或修改) 這些連絡人。 
  
## <a name="enable-users-for-unified-contact-store"></a>為使用者啟用整合連絡人存放區

當您部署商務用 Skype Server 及發行拓撲時，預設會為所有使用者啟用整合連絡人存放區。 您在部署商務用 Skype Server 後，不需要採取任何其他動作來啟用整合連絡人存放區。 不過，您可以使用 **Set-CsUserServicesPolicy** Cmdlet 自訂哪些連絡人有整合連絡人存放區可用。 您可以全域、依網站、依承租人或依個人或個人群組啟用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>啟用整合連絡人存放區的使用者

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列任一項作業：
    
   - 若要為所有商務用 Skype Server 使用者全域啟用整合連絡人存放區，請在 Windows PowerShell 命令列介面上進行下列指令程式：
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 若要為特定網站上的使用者啟用整合連絡人存放區，請在提示中輸入：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 若要依租使用者啟用整合連絡人存放區，請在提示中輸入：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例如：
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 若要為特定使用者啟用整合連絡人存放區，請在提示中輸入：
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 您也可以使用使用者別名或 SIP URI，而不使用使用者顯示名稱。 
  
    例如：
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 在上一個範例中，第一個命令建立名稱為「UCS 已啟用使用者」 的新個別使用者原則，而且將 UcsAllowed 旗標設定為 True。第二個指令將該原則指派給顯示名稱為 Ken Myer 的使用者，這表示目前已針對 Ken Myer 啟用整合連絡人存放區。
  
## <a name="migrate-users-to-unified-contact-store"></a>將使用者遷移至整合連絡人存放區

當使用者執行下列動作時，使用者的連絡人會自動遷移至 Exchange 2013 server：
  
- 已指派了 UcsAllowed 設為 True 的使用者服務原則。
    
- 已布建 Exchange 2013 信箱，且至少登入至信箱一次。
    
- 使用商務用 Skype 豐富型用戶端登入。
    
如果使用者登入 Lync 或舊版用戶端，或使用者未連線至 Exchange 2013 伺服器，則會忽略使用者服務原則，且使用者的連絡人仍會保留在商務用 Skype Server 中。
  
您可使用下列方法之一，來判斷使用者的連絡人是否已移轉： 
  
- 檢查用戶端電腦上的下列登錄機碼：
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL \> \UCS
    
    如果使用者的連絡人儲存在 Exchange 2013 中，則此機碼會包含值為2165的 InUCSMode。
    
- 執行 **Test-CsUnifiedContactStore** Cmdlet。 在商務用 Skype Server 管理命令介面命令列上輸入：
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。
    
## <a name="roll-back-migrated-users"></a>回退遷移的使用者

如果您需要回復整合連絡人存放區功能，請僅在將使用者移回 Exchange 2010 或 Lync Server 2010 時，才復原連絡人。 若要回退，請停用使用者的原則，然後執行 **Invoke-CsUcsRollback** Cmdlet。 只執行 **Invoke-CsUcsRollback** 僅能確保永久復原，因為若未停用原則，將會再次啟動整合連絡人存放區遷移。 例如，如果使用者因為 Exchange 2013 復原回 Exchange 2010，然後將使用者的信箱移至 Exchange 2013，只要在使用者服務原則中仍為使用者啟用整合連絡人存放區，就會重新開機整合的連絡人存放區遷移，這會在復原後的七天內重新開機。
  
**Move-CsUser** Cmdlet 會在下列情況下自動將使用者的連絡人存放區從 Exchange 2013 回復至商務用 Skype Server：
  
- 當使用者從商務用 Skype Server 移至 Microsoft Lync server 2013 或 Lync server 2010 時。 
    
- 當使用者遷移跨單位部署時，例如，當使用者從商務用 Skype Online 移至商務用 Skype Server 內部部署時，或相反。
    
從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和使用者資料在匯出與匯入間的統一連絡人存放區模式變更時損毀。 例如：
  
- 如果您在將使用者的連絡人遷移至 Exchange 2013 之前匯出連絡人清單，然後在遷移之後，匯入相同的資料，整合的連絡人存放區資料和連絡人清單會損毀。
    
- 如果您在將使用者遷移至 Exchange 2013 之後匯出使用者資料，請先復原遷移，然後在遷移之後從某些原因匯入資料，整合的連絡人存放區資料和連絡人清單會損毀。
    
> [!IMPORTANT]
> 將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 系統管理員必須先將商務用 Skype Server 的使用者連絡人第一次還原至商務用 Skype Server 2013 至 Exchange。 若要將整合連絡人存放區連絡人回復至商務用 Skype Server，請參閱本節稍後的程式「回退整合連絡人存放區連絡人 Exchange 2013 至商務用 Skype Server」。 
  
 **如何退回使用者連絡人：** 如果您使用 **Move-CsUser** 指令移動商務用 Skype Server 2015 和 Lync server 2010 之間的使用者，則可以略過這些步驟，因為 **Move-CsUser** Cmdlet 會在將使用者從商務用 Skype Server 2015 移至 Lync Server 2010 時，自動回復整合的連絡人存放區。 **Move-CsUser** 不會停用整合連絡人存放區原則，所以如果使用者移回商務用 Skype Server 2015，便會重複遷移至整合連絡人存放區。
  

