---
title: 將封存原則套用至商務用 Skype Server 中的使用者
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：瞭解如何將封存原則指派給商務用 Skype Server 中的使用者。
ms.openlocfilehash: 343afcca74947f4a9e40830775c2149adcbc58af
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765561"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>將封存原則套用至商務用 Skype Server 中的使用者

**摘要：** 瞭解如何將封存原則指派給商務用 Skype Server 中的使用者。
  
如果您已為位於商務用 Skype Server 的使用者建立一或多個使用者原則，您可以將適當的原則套用至那些使用者或使用者群組，以對特定使用者執行封存支援。 例如，如果您建立原則來支援內部通訊的封存，您可以將它套用至至少一個使用者或使用者群組，以支援封存使用者的商務用 Skype Server 通訊。
  
> [!NOTE]
> 如果您已對部署啟用 Microsoft Exchange 整合，請 Exchange In-Place 保留原則控制是否為位於 Exchange 的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。 如需詳細資訊，請參閱[Plan for 封存 in 商務用 Skype Server](../../plan-your-deployment/archiving/archiving.md)和[設定與 Exchange 儲存體搭配商務用 Skype Server 的整合](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用控制台套用使用者原則

若要使用 [控制台] 套用使用者原則：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。 
    
4. 在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。
    
5. 在 [封存 **原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。
    
    > [!NOTE]
    > **\<Automatic\>** 設定將套用預設伺服器安裝設定。 伺服器會自動套用這些設定。
  
6. 按一下 **[認可]**。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 套用使用者原則

您也可以使用 Windows PowerShell **Grant-CsArchivingPolicy** Cmdlet 來套用使用者原則。
  
下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

這個命令會將個別使用者的封存原則 RedmondArchivingPolicy 指派給所有具有位於註冊機構集區 atl-cs-001.contoso.com 之帳戶的使用者。 如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 檔。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

下列命令會移除先前指派給 Ken Myer 的任何個別使用者封存原則。 移除每一使用者原則之後，就會使用全域原則（如果有的話）或其本機網站原則來管理 Ken Myer。 網站原則優先順序高於全域原則。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) Cmdlet 檔。
