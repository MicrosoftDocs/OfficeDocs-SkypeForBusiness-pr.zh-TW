---
title: 移轉回應群組
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 將使用者移至商務用 Skype Server 2019 集區之後，您可以遷移回應群組。 遷移回應群組包括從舊版部署到商務用 Skype Server 2019 集區，將代理群組、佇列、工作流程、音訊檔及移動回應群組連絡人物件。 遷移舊版回應群組之後，回應群組的呼叫會由商務用 Skype Server 2019 集區中的回應群組應用程式來處理。 舊版集區不會再處理對回應群組的通話。
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113269"
---
# <a name="migrate-response-groups"></a>移轉回應群組

將使用者移至商務用 Skype Server 2019 集區之後，您可以遷移回應群組。 遷移回應群組包括從舊版部署到商務用 Skype Server 2019 集區，將代理群組、佇列、工作流程、音訊檔及移動回應群組連絡人物件。 遷移舊版回應群組之後，回應群組的呼叫會由商務用 Skype Server 2019 集區中的回應群組應用程式來處理。 舊版集區不會再處理對回應群組的通話。
  
> [!NOTE]
> 雖然您可以在將所有使用者移至商務用 Skype Server 2019 集區之前遷移回應群組，但建議您先移動所有使用者。 特別是，回應群組代理程式的使用者在移至商務用 Skype Server 2019 集區之前，不會有新功能的完整功能。 
  
在遷移回應群組之前，您必須已部署包含回應群組應用程式的商務用 Skype Server 2019 集區。 當您部署企業語音時，預設會安裝及啟用回應群組應用程式。 您可以執行 **Get-CsService ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。 
  
> [!NOTE]
> 您可以在遷移舊版回應群組之前，先在商務用 Skype Server 2019 集區中建立新的商務用 Skype Server 2019 回應群組。 
  
若要將回應群組從舊版集區遷移至商務用 Skype Server 2019，您可以執行 **Move-CsRgsConfiguration** Cmdlet。 
  
> [!IMPORTANT]
> 回應群組遷移 Cmdlet 會移動整個集區的回應群組設定。 您無法選取要移轉的特定群組、佇列或工作流程。 
  
遷移回應群組之後，您必須使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面 Cmdlet，確認所有代理人群組、佇列和工作流程都已順利移動。 
  
當您遷移回應群組時，不會移除舊版回應群組。 當您使用商務用 Skype Server 控制台或商務用 skype Server 管理命令介面來管理遷移之後的回應群組時，您可以看到舊版回應群組和商務用 Skype Server 2019 回應群組。 您應該只將更新套用至商務用 Skype Server 2019 回應群組。 舊版回應群組只會保留以供復原之用。 
  
> [!CAUTION]
> 完成遷移並建立新的回應群組之後，商務用 Skype Server 控制台和商務用 skype server 管理命令介面會顯示每個回應群組的舊版和商務用 Skype Server 2019 版本。 請勿使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來移除舊版回應群組。 如果您確實移除其中一個，則在遷移期間所建立的對應回應群組將停止運作。 當您解除委任舊版集區時，將會移除舊版回應群組。 
  
> [!IMPORTANT]
> 建議集區解除委任之後，再移除先前部署的各項資料。 此外，強烈建議移轉後立即匯出回應群組。 如果舊版回應群組應該被移除，您可以從備份還原回應群組，以取得商務用 Skype Server 2019 回應群組。 
  
商務用 Skype Server 2019 引進新的回應群組功能，稱為 **工作流程類型**。 **[工作流程類型]** 可以是 **[已管理]** 或 **[未管理]**。 移轉後的所有回應群組 **[工作流程類型]** 都會設為 **[未管理]**，並附有一份空白的管理員清單。 
  
執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。 如果確實有必要復原舊版集區，必須執行 **Move-CsApplicationEndpoint** Cmdlet 才能將連絡人物件移動到舊版集區。 
  
下列遷移回應群組設定的程式假設您的舊版集區與商務用 Skype Server 2019 集區之間具有一對一的關聯性。 如果您想要在遷移和部署期間整合或分割集區，您必須規劃哪些舊版集區對應至哪一個 Skype Server 2019 集區。
  
## <a name="to-migrate-response-group-configurations"></a>遷移回應群組設定

1. 使用 RTCUniversalServerAdmins 群組的成員帳戶，或具有等同於系統管理員權限的帳戶登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
3. 執行：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    例如：
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. 將回應群組和代理程式遷移至商務用 Skype Server 2019 集區之後，代理人用來登入和登出的 URL 就是商務用 Skype Server 2019 URL，而且可從 [ **工具** ] 功能表中取得。 請提醒代理人將書籤等任何參照更新到新的 URL。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台驗證回應群組遷移

1. 使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [開放式商務用 Skype server 2019 系統管理工具](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. 在左導覽列中，按一下 **[回應群組]**。
    
4. 在 [ **工作流程** ] 索引標籤上，確認您的舊版環境中的所有工作流程都包含在清單中。 
    
5. 按一下 [ **佇列** ] 索引標籤，確認清單中包含舊版環境中的所有佇列。 
    
6. 按一下 [ **群組** ] 索引標籤，並確認您的舊版環境中的所有代理程式群組都包含在清單中。 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來驗證回應群組遷移

1. 使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
    如需下列 Cmdlet 的詳細資料，請執行：
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. 執行：
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. 確認您的舊版環境中的所有代理程式群組都包含在清單中。
    
5. 執行：
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. 確認您的舊版環境中的所有佇列都包含在清單中。
    
7. 執行：
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. 確認您的舊版環境中的所有工作流程都包含在清單中。
