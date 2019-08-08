---
title: '在商務用 Skype Server 中部署整合連絡人存放區 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '摘要: 在商務用 Skype Server 中啟用整合連絡人存放區。'
ms.openlocfilehash: 39317316be6c4590e992c61e91549748f3bf6719
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239315"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>在商務用 Skype Server 中部署整合連絡人存放區
 
**摘要:** 在商務用 Skype Server 中啟用整合連絡人存放區。
  
在商務用 Skype 伺服器中啟用整合連絡人存放區, 不需要任何拓撲設定。 若要為使用者啟用整合連絡人存放區:
  
- 已啟用整合連絡人存放區原則 (預設為啟用)。
    
- 使用者至少使用商務用 Skype 登入一次。
    
在使用者的連絡人已完成遷移之後, 當使用者使用商務用 Skype 登入時, 該使用者可以從商務用 skype、Outlook 2013 或 Outlook Web Access 存取及管理其商務用 skype 連絡人。 使用者不需要登入商務用 Skype, 就可以從 Outlook 或 Outlook Web Access 管理他們的連絡人。
  
> [!IMPORTANT]
> 如果使用者在遷移之後從商務用 Skype 登入, 就可以使用連絡人和群組, 但使用者無法管理 (也就是新增、刪除、移動、標記、將或修改) 這些連絡人。 
  
## <a name="enable-users-for-unified-contact-store"></a>為使用者啟用整合連絡人存放區

當您部署商務用 Skype 伺服器併發布拓撲時, 預設會為所有使用者啟用「整合連絡人存放區」。 在您部署商務用 Skype Server 之後, 您不需要採取任何其他動作即可啟用整合連絡人存放區。 不過, 您可以使用**CsUserServicesPolicy** Cmdlet 來自訂哪些使用者可以使用 [整合的連絡人] 存放區。 您可以在全球、由網站、由租使用者, 或由個人或個人群組來啟用此功能。
  
### <a name="to-enable-users-for-unified-contact-store"></a>若要讓使用者使用整合連絡人存放區

1. 啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**], 然後按一下 [**商務用 skype server 管理命令**介面]。
    
2. 請執行下列任何一項操作:
    
   - 若要針對所有商務用 Skype Server 使用者全域啟用整合式連絡人存放區, 請在 Windows PowerShell 命令列介面上使用下列 Cmdlet:
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 若要針對特定網站的使用者啟用整合連絡人存放區, 請在出現提示時, 輸入:
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   例如：
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 若要啟用租使用者的整合連絡人存放區, 請在提示時輸入:
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   例如：
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 若要針對特定使用者啟用整合連絡人存放區, 請在提示時輸入:
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 您也可以使用使用者別名或 SIP URI, 而不是使用者的顯示名稱。 
  
    例如：
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 在前面的範例中, 第一個命令會建立名為 [UCS] 的新使用者原則, 並將 UcsAllowed 標誌設定為 True。 第二個命令會將原則指派給使用者, 並使用顯示名稱 Ken Myer, 這表示現在已為整合連絡人存放區啟用 Ken Myer。
  
## <a name="migrate-users-to-unified-contact-store"></a>將使用者移轉到整合的連絡人存放區

當使用者在下列情況下, 使用者的連絡人會自動轉移至 Exchange 2013 伺服器:
  
- 已指派 UcsAllowed 設定為 True 的使用者服務原則。
    
- 已使用 Exchange 2013 信箱進行預配, 且至少已在信箱中登入一次。
    
- 使用商務用 Skype 胖用戶端登入。
    
如果使用者使用 Lync 或較舊的用戶端登入, 或者如果使用者未連線至 Exchange 2013 伺服器, 則系統會忽略使用者服務原則, 且使用者的連絡人會保留在商務用 Skype 伺服器中。
  
您可以使用下列其中一種方法來判斷使用者的連絡人是否已被遷移: 
  
- 檢查用戶端電腦上的下列登錄機碼:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    如果使用者的連絡人儲存在 Exchange 2013 中, 此索引鍵會包含值為2165的 InUCSMode 值。
    
- 執行**Test CsUnifiedContactStore** Cmdlet。 在商務用 Skype Server Management Shell 命令列上, 鍵入:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    如果**CsUnifiedContactStore**成功, 則使用者的連絡人已遷移至整合連絡人存放區。
    
## <a name="roll-back-migrated-users"></a>回滾已遷移的使用者

如果您需要回滾 [整合連絡人存放區] 功能, 請只有在您將使用者移回 Exchange 2010 或 Lync Server 2010 時, 才能回滾連絡人。 若要回滾, 請停用使用者的原則, 然後執行**CsUcsRollback** Cmdlet。 僅僅執行**Invoke CsUcsRollback**是無法確保永久復原, 因為如果原則沒有停用, 就會再次啟動整合式連絡人存放區遷移。 例如, 如果使用者因為 Exchange 2013 已回滾至 Exchange 2010, 且使用者的信箱移至 Exchange 2013, 則在回滾之後的7天內就會再次開始進行整合連絡人商店遷移 (只要整合連絡人存放區)在使用者服務原則中, 仍已啟用使用者的。
  
在下列情況下, **move-csuser** Cmdlet 會將使用者的連絡人存放區從 Exchange 2013 自動回滾到商務用 Skype Server:
  
- 當使用者從商務用 Skype Server 移至 Microsoft Lync Server 2013 或 Lync Server 2010 時。 
    
- 使用者被遷移時 (例如, 當使用者從商務用 Skype Online 移至內部部署的商務用 Skype Server), 或相反的情況下。
    
從備份資料庫匯入整合連絡人存放區資料時, 如果在匯出與匯入之間變更了整合連絡人存放區模式, 就會導致整合連絡人存放區資料和使用者資料遭到損毀。 例如：
  
- 如果您先匯出連絡人清單, 然後再將使用者的連絡人遷移至 Exchange 2013, 然後在遷移之後, 將相同的資料匯入, 整合的連絡人商店資料和連絡人清單都會損毀。
    
- 如果您在將使用者遷移至 Exchange 2013 之後匯出使用者資料, 請回滾遷移, 然後, 如果您在遷移之後從某種原因匯入資料, 整合的連絡人商店資料和連絡人清單都會損毀。
    
> [!IMPORTANT]
> 在將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前, Exchange 管理員必須先將商務用 skype Server 系統管理員的 [商務2013用 skype 伺服器] 使用者連絡人回滾至 Skype for商務伺服器。 若要將「整合連絡人存放區」連絡人回滾至商務用 Skype Server, 請參閱本節稍後的程式「將整合的連絡人存放庫連絡人從 Exchange 2013 回滾到商務用 Skype Server」。 
  
 **如何退回使用者連絡人:** 如果您使用**move-csuser** Cmdlet 在商務用 skype server 2015 和 Lync server 2010 之間移動使用者, 您可以略過這些步驟, 因為**move-csuser** Cmdlet 會在使用者從 Skype 移動使用者時, 自動回退整合的連絡人存放區商務伺服器2015至 Lync Server 2010。 **Move-csuser**不會停用整合式連絡人存放區原則, 因此, 如果使用者移回商務用 Skype Server 2015, 就會重複遷移至整合連絡人存放區。
  

