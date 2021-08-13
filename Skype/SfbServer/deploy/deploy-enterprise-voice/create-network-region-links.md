---
title: 在商務用 Skype Server 中建立網路地區連結
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 建立或修改網路地區連結，這些連結是由商務用 Skype Server 中企業語音通話許可控制使用。
ms.openlocfilehash: a332d3cb966247118d951626ac305c4a9f85e21d4b90b6011a07a1220f01170a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325460"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路地區連結
 
建立或修改網路地區連結，這些連結是由商務用 Skype Server 中企業語音通話許可控制使用。 
  
網路中的區域是透過實體 WAN 連線相互連結。 網路地區連結會在設定為通話許可控制的兩個地區之間建立連結 (CAC) 並設定這些地區之間音訊和影片流量的頻寬限制。
  
這個範例拓撲有一個北美和 APAC 地區之間的連結，以及 EMEA 和 APAC 地區之間的連結。 每個地區連結都受 WAN 頻寬限制，如地區連結頻寬資訊表格中所述[：在商務用 Skype Server 中收集通話許可控制的需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立網路地區連結

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行 New-CsNetworkRegionLink Cmdlet 來建立地區連結，並套用適當的頻寬原則設定檔。 例如，執行：
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立網路地區連結

1. 開啟商務用 Skype Server 控制台]。
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 按一下 [ **地區連結** ] 導覽按鈕。
    
4. 按一下 [ **新增**]。
    
5. 在 [ **新增地區連結** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路地區連結的名稱。
    
6. 按一下 [ **網路地區 #1**]，然後按一下清單中要連結至 [網路地區] 的網路地區 #2。
    
7. 按一下 [ **網路地區 #2**]，然後按一下清單中要連結至 [網路地區] 的網路地區 #1。
    
8. （選用）按一下 [ **頻寬原則**]，然後選取您要套用到網路地區連結的頻寬原則設定檔。
    
    > [!NOTE]
    > [！注意事項] 只有在網路地區連結受到頻寬限制，且您想要使用 CAC 來控制該連結上的媒體流量時，才套用頻寬原則。 
  
9. 按一下 **[認可]**。
    
10. 若要完成建立拓撲的網路地區連結，請使用其他地區的設定重複步驟4到9。
    
## <a name="see-also"></a>另請參閱

[新 CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)