---
title: 設定會議加入頁面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。 如果已安裝用戶端，該用戶端會開啟並加入會議。 如果沒有安裝用戶端，則預設會開啟 Web 應用程式。
ms.openlocfilehash: 35b8b816d5c01f3061dc697cf7f37a4314a5f083
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813791"
---
# <a name="configure-the-meeting-join-page"></a>設定會議加入頁面

當使用者按一下會議邀請中的會議連結時，[會議加入] 頁面會偵測使用者電腦上已安裝的用戶端。 如果已安裝用戶端，該用戶端會開啟並加入會議。 如果沒有安裝用戶端，則預設會開啟 Web 應用程式。
  
如果您想要允許使用者加入會議，您可以修改會議加入頁面的行為。 這些設定選項已從 [控制台] 中移除，但您可以使用 CsWebServiceConfiguration Cmdlet 加以設定。
  
**會議加入頁面 CsWebServiceConfiguration 參數**

|**CsWebServiceConfiguration 參數**|**說明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |如果設為 True，則使用者使用 Lync 以外的用戶端應用程式加入會議時，系統會提供加入會議的機會。 預設值為 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |當設定為 True 時，加入線上會議的替代選項會自動展開並向使用者顯示。 當設定為 False （預設值）時，將會提供這些選項，但使用者將必須針對自己顯示選項清單。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>使用商務用 Skype Server 2019 管理命令介面設定會議加入頁面

1. 啟動商務用 Skype Server 2019 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype server Management Shell**]。
    
2. 執行下列 Cmdlet： 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    這個 Cmdlet 會傳回 web 服務配置設定。
    
3. 根據您的喜好設定（如需此 Cmdlet 之參數的詳細資料，請參閱[商務用 Skype Server 管理命令](../../SfbServer/manage/management-shell.md)介面檔），執行下列命令，並將參數設定為 True 或 False。
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


