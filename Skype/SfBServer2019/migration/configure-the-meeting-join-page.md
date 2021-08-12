---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。 若已安裝用戶端，將會開啟該用戶端，然後加入會議。 若未安裝用戶端，則預設會開啟 Web 應用程式。
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295120"
---
# <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。 若已安裝用戶端，將會開啟該用戶端，然後加入會議。 若未安裝用戶端，則預設會開啟 Web 應用程式。
  
如果您想要允許使用者加入會議，您可以修改會議加入頁面的行為。 這些設定選項已從 [控制台] 中移除，但您使用 CsWebServiceConfiguration Cmdlet 進行設定。
  
**會議加入頁面的 CsWebServiceConfiguration 參數**

|**CsWebServiceConfiguration 參數**|**描述**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |若設為 True，使用 Lync 以外的用戶端應用程式加入會議的使用者，將會獲得加入會議的機會。 預設值為 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |設為 True 時，加入線上會議的替代選項會自動展開並顯示給使用者。 設為 False 時 (預設值) ，這些選項將可供使用，但使用者必須自行顯示選項清單。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面設定會議加入頁面

1. 啟動商務用 Skype Server 2019 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 Skype Server 2019**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列 Cmdlet： 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    此 Cmdlet 會傳回 Web 服務設定。
    
3. 執行下列命令，並將參數設定為 True 或 False，這取決於您的喜好設定 (如需此 Cmdlet 之參數的詳細資訊，請參閱[商務用 Skype Server 管理命令](../../SfbServer/manage/management-shell.md)介面檔) ：
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


