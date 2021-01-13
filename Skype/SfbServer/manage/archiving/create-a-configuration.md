---
title: 在商務用 Skype Server 中建立封存設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：瞭解如何為商務用 Skype 伺服器建立封存設定。
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817653"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>在商務用 Skype Server 中建立封存設定

**摘要：** 瞭解如何為商務用 Skype 伺服器建立封存設定。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制台設定封存選項

若要設定特定網站或集區的封存選項： 
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 在 [ **封存** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項操作： 
    
   - 若要建立網站封存設定，請按一下 [ **網站** 設定]，然後在 [ **選取網站**] 中，選取要設定封存的網站。
    
   - 若要建立集區封存設定，請按一下 [ **集** 區設定]，然後在 [ **選取集** 區] 中，選取要設定封存的集區。
    
5. 在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：
    
   - 若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。
    
   - 若要同時啟用 IM 會話和 web 會議的封存，請按一下 [封存 **im 和 web 會議會話**]。
    
   - 若要停用此設定的封存，請按一下 [ **停** 用封存]。
    
6. 此外，在 **[建立新的封存設定]** 中，執行下列動作：
    
   - 若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。
    
   - 若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。
    
   - 若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：
    
     - 若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
    
     - 若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。
    
7. 按一下 **[認可]**。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 設定封存選項

您也可以使用 **New-CsArchivingConfiguration** Cmdlet 來設定特定網站或集區的封存選項。
  
下列命令會為 Redmond 網站建立新的封存配置設定集合：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。 
  
若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。 下列範例會建立封存設定的集合，根據預設，只允許封存立即訊息會話：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

多項屬性值可透過加入多個參數加以修改。 例如，此命令會將新設定設定為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

如需詳細資訊，請參閱 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
