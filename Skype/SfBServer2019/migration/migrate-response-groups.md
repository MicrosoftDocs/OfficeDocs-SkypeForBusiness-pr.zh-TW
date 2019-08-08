---
title: 遷移回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 當您的使用者移至商務用 Skype Server 2019 池之後, 您就可以遷移您的回應群組。 遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案, 以及將回應群組連絡人物件從舊版部署移至商務用 Skype Server 2019 池。 在您遷移舊版回應群組之後, 回應群組的呼叫會由商務用 Skype Server 2019 池中的回應群組應用程式來處理。 舊版池已不再處理回應群組的呼叫。
ms.openlocfilehash: b8d49205f4f54ca7c00a9aed0b6ac176c11cd617
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238461"
---
# <a name="migrate-response-groups"></a>遷移回應群組

當您的使用者移至商務用 Skype Server 2019 池之後, 您就可以遷移您的回應群組。 遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案, 以及將回應群組連絡人物件從舊版部署移至商務用 Skype Server 2019 池。 在您遷移舊版回應群組之後, 回應群組的呼叫會由商務用 Skype Server 2019 池中的回應群組應用程式來處理。 舊版池已不再處理回應群組的呼叫。
  
> [!NOTE]
> 雖然您可以在將所有使用者移至商務用 Skype Server 2019 池之前先遷移回應群組, 但我們建議您先移動所有使用者。 特別是, 回應群組代理的使用者在移至商務用 Skype Server 2019 池之前, 將不會有新功能的完整功能。 
  
在您遷移回應群組之前, 您必須已部署包含回應群組應用程式的商務用 Skype Server 2019 池。 當您部署企業語音時, 系統會預設安裝並啟用回應群組應用程式。 您可以執行**CsService-ApplicationServer** Cmdlet, 以確保已安裝回應群組應用程式。 
  
> [!NOTE]
> 在您遷移舊版回應群組之前, 您可以在商務用 Skype Server 2019 池中建立新的商務用 Skype Server 2019 回應群組。 
  
若要將回應群組從舊版池遷移到商務用 Skype Server 2019, 您可以執行**CsRgsConfiguration** Cmdlet。 
  
> [!IMPORTANT]
> 回應群組遷移 Cmdlet 會移動整個池的回應群組設定。 您無法選取要遷移的特定群組、佇列或工作流程。 
  
在您遷移回應群組之後, 您必須使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面 Cmdlet], 確認所有代理群組、佇列和工作流程已順利移動。 
  
當您遷移回應群組時, 不會移除舊版回應群組。 如果您是使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面, 在遷移之後管理回應群組, 您可以看到舊版回應群組和商務用 Skype Server 2019 回應群組。 您只能將更新套用到商務用 Skype Server 2019 回應群組。 舊版回應群組只會保留供回滾之用。 
  
> [!CAUTION]
> 完成遷移並建立新的回應群組之後, 商務用 Skype Server 的 [控制台] 和 [商務用 skype 伺服器] 管理命令介面會顯示舊版及商務用 Skype server 的2019版本。群組. 請勿使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來移除舊版回應群組。 如果您移除其中一個專案, 則在遷移期間建立的對應回應群組就會停止運作。 當您解除授權舊版池時, 會移除舊版回應群組。 
  
> [!IMPORTANT]
> 我們建議您不要從先前的部署移除任何資料, 除非您解除該池。 此外, 我們強烈建議您在遷移後立即匯出回應群組。 如果傳統回應群組應該被移除, 您可以從備份還原回應群組, 以取得商務用 Skype Server 2019 回應群組再次執行。 
  
商務用 Skype Server 2019 引入了稱為「**工作流程類型**」的新回應群組功能。 **工作流程類型**可以是**託管**或**非託管**。 [所有回應群組] 都將 [**工作流程類型**] 設定為 [**非託管**], 並使用空的管理員清單進行遷移 
  
當您執行**CsRgsConfiguration** Cmdlet 時, 系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案, 以供回滾之用。 不過, 如果您需要回滾到舊版池, 您必須執行**CsApplicationEndpoint** Cmdlet, 以將連絡人物件移回舊版資源區。 
  
下列程式適用于遷移回應群組設定, 假設您的舊版池與商務用 Skype Server 2019 池之間有一對一關聯性。 如果您打算在您的遷移和部署期間合併或分割池, 您需要規劃哪些舊版池會對應到哪個商務用 Skype Server 2019 池。
  
## <a name="to-migrate-response-group-configurations"></a>若要遷移回應群組設定

1. 以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦, 或擁有同等的系統管理員許可權和許可權。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。
    
3. 用盡
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 在您將回應群組和代理程式遷移到商務用 Skype Server 2019 文件庫之後, 代理程式用來登入和登出的 URL 就是商務用 Skype Server 2019 URL, 且可從 [**工具**] 功能表取得。 提醒代理程式將任何參照 (例如書簽) 更新為新的 URL。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 驗證回應群組遷移

1. 使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦, 或最少是 CsViewOnlyAdministrator 角色的成員。
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[開啟商務用 Skype server 2019 系統管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左側功能窗格中, 按一下 [**回應群組**]。
    
4. 在 [**工作流程**] 索引標籤上, 確認您的舊版環境中的所有工作流程都包含在清單中。 
    
5. 按一下 [**佇列**] 索引標籤, 並確認您的舊版環境中的所有佇列都包含在清單中。 
    
6. 按一下 [**群組**] 索引標籤, 並確認您的舊版環境中的所有代理群組都包含在清單中。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 驗證回應群組遷移

1. 使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦, 或最少是 CsViewOnlyAdministrator 角色的成員。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。
    
    如需有關下列 Cmdlet 的詳細資訊, 請執行:
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. 用盡
    
   ```
   Get-CsRgsAgentGroup
   ```

4. 確認您舊版環境中的所有代理群組都包含在清單中。
    
5. 用盡
    
   ```
   Get-CsRgsQueue
   ```

6. 確認您的舊版環境中的所有佇列都包含在清單中。
    
7. 用盡
    
   ```
   Get-CsRgsWorkflow
   ```

8. 確認您的舊版環境中的所有工作流程都包含在清單中。
    

