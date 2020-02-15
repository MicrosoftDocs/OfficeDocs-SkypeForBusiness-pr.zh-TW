---
title: 移轉回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您的使用者移到 Skype for Business Server 2019 集區之後，您可以移轉回應群組。 移轉回應群組包含複製代理人群組、 佇列、 工作流程、 音訊檔案，並將回應群組連絡人物件從舊版部署移至 Skype for Business Server 2019 集區。 在移轉舊版回應群組之後，呼叫回應群組是由 Skype for Business Server 2019 集區的回應群組應用程式處理。 舊版集區不會再處理對回應群組的通話。
ms.openlocfilehash: 2d439462fa103cc16fd7ae70b79364be7d79803a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016104"
---
# <a name="migrate-response-groups"></a>移轉回應群組

您的使用者移到 Skype for Business Server 2019 集區之後，您可以移轉回應群組。 移轉回應群組包含複製代理人群組、 佇列、 工作流程、 音訊檔案，並將回應群組連絡人物件從舊版部署移至 Skype for Business Server 2019 集區。 在移轉舊版回應群組之後，呼叫回應群組是由 Skype for Business Server 2019 集區的回應群組應用程式處理。 舊版集區不會再處理對回應群組的通話。
  
> [!NOTE]
> 雖然您可以移轉回應群組，您將所有使用者都移至 Skype for Business Server 2019 集區之前，建議您先都移動所有使用者。 特別是，回應群組代理程式的使用者將不會有新功能的完整功能，直到他們移 skype for Business Server 2019 集區。 
  
移轉回應群組之前，您必須部署 Skype for Business Server 2019 集區，其中包含的回應群組應用程式。 回應群組應用程式已安裝並啟用根據預設，當您部署企業語音。 您可以確定回應群組應用程式安裝的是執行**Get-csservice ApplicationServer**指令程式。 
  
> [!NOTE]
> 移轉舊版回應群組之前，您可以在 Skype for Business Server 2019 集區中建立新 Skype for Business Server 2019 的回應群組。 
  
若要移轉回應群組從舊版集區用 skype for Business Server 2019，您可以執行**Move-csrgsconfiguration** cmdlet。 
  
> [!IMPORTANT]
> 回應群組移轉 cmdlet 移動整個集區的回應群組組態。 您無法選取要移轉的特定群組、佇列或工作流程。 
  
在移轉回應群組之後，您需要使用 Skype 商務 Server Control Panel 或 Skype Business Server 管理命令介面指令程式來驗證所有代理人群組、 佇列及工作流程成功都移動。 
  
當您移轉回應群組時，不會移除舊版回應群組。 當您管理回應群組，您可以在移轉之後使用任一 Skype 商務 Server Control Panel 或 Skype for Business Server 管理命令介面時，您可以看到舊版回應群組與 Skype for Business Server 2019 的回應群組。 您應該更新僅適用於 Skype for Business Server 2019 的回應群組。 僅針對復原用途，會保留舊版回應群組。 
  
> [!CAUTION]
> Skype for Business Server Control Panel 與 Skype for Business Server 管理命令介面完成移轉，並已建立新的回應群組之後，會顯示傳統與 Skype for Business Server 2019 版本的每個回應群組。 請勿 Skype for Business Server Control Panel 或 Skype for Business Server 管理命令介面來移除舊版回應群組。 如果您不要移除其中，移轉期間所建立的對應回應群組會停止運作。 當您解除委任舊版集區時，將會移除舊版回應群組。 
  
> [!IMPORTANT]
> 建議集區解除委任之後，再移除先前部署的各項資料。 此外，強烈建議移轉後立即匯出回應群組。 如果應取得移除舊版回應群組，您就可以從 Skype 取得 Business Server 2019 的回應群組，再執行一次備份，然後還原您的回應群組。 
  
Skype 商務 Server 2019 引進新的回應群組功能，稱為**工作流程類型**。 **[工作流程類型]** 可以是 **[已管理]** 或 **[未管理]**。 移轉後的所有回應群組 **[工作流程類型] **都會設為 **[未管理]**，並附有一份空白的管理員清單。 
  
執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。 如果確實有必要復原舊版集區，必須執行 **Move-CsApplicationEndpoint** Cmdlet 才能將連絡人物件移動到舊版集區。 
  
移轉回應群組組態的下列程序假設您在舊版的集區與 Skype for Business Server 2019 集區之間有一對一的關係。 如果您計劃合併或分割備份集區移轉和部署期間，您需要哪些舊版集區會對應至哪一個 Skype for Business Server 2019 集區的計劃。
  
## <a name="to-migrate-response-group-configurations"></a>移轉回應群組設定

1. 使用 RTCUniversalServerAdmins 群組的成員帳戶，或具有等同於系統管理員權限的帳戶登入電腦。
    
2. 啟動 Skype for Business Server 管理命令介面： 按一下 [**開始]**、 [**所有程式]**、 按一下**Microsoft Skype for Business Server 2019**，，然後按一下**Skype for Business Server 管理命令介面**。
    
3. 執行：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 在移轉 Skype for Business Server 2019 集區的回應群組和代理程式之後，代理程式用來登入和登出的 URL 是 Skype for Business Server 2019 URL，可從 [**工具**] 功能表。 請提醒代理人將書籤等任何參照更新到新的 URL。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>若要使用 Skype for Business Server 控制台驗證回應群組移轉

1. 使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。
    
2. 開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Skype for Business Server Control Panel。 如需您可以用來啟動 Skype for Business Server Control Panel 不同方法的詳細資訊，請參閱[開啟 Skype for Business Server 2019 系統管理工具](https://technet.microsoft.com/library/gg195741(v=ocs.15).aspx)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左導覽列中，按一下 **[回應群組]**。
    
4. 在 [**工作流程**] 索引標籤，確認清單中包含舊版環境中的所有工作流程。 
    
5. 按一下 [**佇列**] 索引標籤，確認清單中包含舊版環境中的所有佇列。 
    
6. 按一下 [**群組**] 索引標籤，確認清單中包含舊版環境中的所有代理程式群組。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>若要使用 Skype for Business Server 管理命令介面驗證回應群組移轉

1. 使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。
    
2. 啟動 Skype for Business Server 管理命令介面： 按一下 [**開始]**、 [**所有程式]**、 按一下**Microsoft Skype for Business Server 2019**，，然後按一下**Skype for Business Server 管理命令介面**。
    
    如需下列 Cmdlet 的詳細資料，請執行：
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 執行：
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 確認清單中包含舊版環境中的所有代理程式群組。
    
5. 執行：
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 確認清單中包含舊版環境中的所有佇列。
    
7. 執行：
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 確認清單中包含舊版環境中的所有工作流程。
    

