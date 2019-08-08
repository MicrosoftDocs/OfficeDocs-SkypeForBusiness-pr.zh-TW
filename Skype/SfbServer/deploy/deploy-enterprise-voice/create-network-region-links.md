---
title: 在商務用 Skype Server 中建立網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 在商務用 Skype Server 中建立或修改 [企業語音通話許可控制] 所使用的網路區域連結。
ms.openlocfilehash: 2b2eb99fa59125c93d97b902b6fbaad122ffdcdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233691"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路區域連結
 
在商務用 Skype Server 中建立或修改 [企業語音通話許可控制] 所使用的網路區域連結。 
  
網路中的區域是透過物理 WAN 連線來連結。 [網路區域] 連結會建立兩個設定為 [呼叫許可控制] (CAC) 的區域之間的連結, 並設定這些區域之間音訊與視頻流量的頻寬限制。
  
此範例拓撲在北美與 APAC 區域之間有連結, 以及 EMEA 與 APAC 區域之間的連結。 上述每一個區域連結都受 WAN 頻寬的限制, 如地區連結頻寬資訊資料表中所述[: 在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立網路區域連結

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行新的 CsNetworkRegionLink Cmdlet 來建立區域連結, 並套用適當的頻寬原則設定檔。 例如，執行：
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立網路區域連結

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中, 按一下 [**網路**設定]。
    
3. 按一下 [**地區] 連結**瀏覽按鈕。
    
4. 按一下 [**新增**]。
    
5. 在 [**新增區域連結**] 頁面上, 按一下 [**名稱**], 然後輸入網路區域連結的名稱。
    
6. 按一下 [**網路區域 #1**], 然後按一下清單中您要連結至 [網路區域] 的網路區域 #2。
    
7. 按一下 [**網路區域 #2**], 然後在清單中按一下您想要連結至 [網路區域] 的網路區域 #1。
    
8. 或者, 按一下 [**頻寬原則**], 然後選取您要套用到 [網路區域] 連結的頻寬原則設定檔。
    
    > [!NOTE]
    > 只有在 [網路區域] 連結受到頻寬限制且您想要使用 CAC 來控制該連結上的媒體流量時, 才能套用頻寬原則。 
  
9. 按一下 [認可]****。
    
10. 若要為您的拓撲建立網路區域連結, 請重複步驟4到 9, 以及其他地區的設定。
    
## <a name="see-also"></a>另請參閱

[新-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[移除-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
