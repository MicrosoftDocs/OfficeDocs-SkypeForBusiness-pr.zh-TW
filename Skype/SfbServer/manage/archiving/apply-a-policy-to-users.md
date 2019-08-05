---
title: 將存檔原則套用到商務用 Skype Server 中的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '摘要: 瞭解如何將存檔原則指派給商務用 Skype Server 中的使用者。'
ms.openlocfilehash: 895a7fac34fcac0a4a7e39756796f6b7d2fc6377
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189358"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>將存檔原則套用到商務用 Skype Server 中的使用者

**摘要:** 瞭解如何將存檔原則指派給商務用 Skype Server 中的使用者。
  
如果您已經針對駐留在商務用 Skype Server 上的使用者建立一或多個使用者原則, 您可以將適當的原則套用至這些使用者或使用者群組, 以實現特定使用者的歸檔支援。 例如, 如果您建立的原則支援內部通訊的歸檔, 您可以將它套用至至少一個使用者或使用者群組, 以支援使用者的商務用 Skype 伺服器通訊。
  
> [!NOTE]
> 如果您已針對您的部署啟用 Microsoft Exchange 整合, Exchange 就地保留原則會控制是否針對託管于 Exchange 的使用者啟用封存, 並將其信箱放在就地保留中。 如需詳細資訊, 請參閱[在商務用 Skype server 中進行](../../plan-your-deployment/archiving/archiving.md)封存的規劃, 以及[設定與商務用 Skype server 的 Exchange 儲存體整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用 [控制台] 套用使用者原則

若要使用 [控制] 面板來套用使用者原則:
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [**使用者**], 然後搜尋您要設定的使用者帳戶。 
    
4. 在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。
    
5. 在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中, 選取您要套用的存檔使用者原則。
    
    > [!NOTE]
    > [ ** \<自動\> **設定] 會套用預設伺服器安裝設定。 伺服器會自動套用這些設定。
  
6. 按一下 [認可]****。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 套用使用者原則

您也可以使用 Windows PowerShell**授與 CsArchivingPolicy** Cmdlet 來套用使用者原則。
  
下列命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

這個命令會將每個使用者的存檔原則 RedmondArchivingPolicy 指派給擁有 [註冊機] 池 atl-cs-001.contoso.com 之帳戶的所有使用者。 如需此命令中使用之篩選參數的詳細資訊, 請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 檔。
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

下列命令會移除先前指派給 Ken Myer 的任何每使用者存檔原則。 移除每個使用者原則之後, 就會使用全域原則 (如果有的話) 自動管理 Ken Myer, 或使用其本機網站原則。 網站原則的優先順序高於全域原則。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

如需詳細資訊, 請參閱[Grant CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlet 檔。
  

