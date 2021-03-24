---
title: 在商務用 Skype Server 中建立網路 interregional 路由
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 在商務用 Skype Server 中建立或修改網路 interregional 路由，以供 Enterprise Voice 通話許可控制使用。
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093121"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路 interregional 路由
 
在商務用 Skype Server 中建立或修改網路 interregional 路由，以供 Enterprise Voice 通話許可控制使用。 
  
網路 interregional 路由會定義一對網路地區之間的路由。 通話許可控制部署中的每一對網路地區都需要網路 interregional 路由。 這可讓部署中的每一個網路地區都可以存取所有其他的地區。
  
雖然地區連結設定了區域間連線的頻寬限制，但 interregional 路由會決定連線到另一個地區的連結路徑。
  
在範例拓撲中，必須為三個地區成對定義網路 interregional 路由：北 America/EMEA、EMEA/APAC 及北 America/APAC。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立網路 interregional 路由

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 執行 **New-CsNetworkInterRegionRoute** Cmdlet 以定義所需的路由。 例如，執行：
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 北美 America/APAC 網路 interregional 路由需要兩個網路地區連結，因為兩者之間沒有任何直接的網路地區連結。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立網路 interregional 路由

1. 開啟商務用 Skype Server 控制台。
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 按一下 **[地區路由]** 導覽按鈕。
    
4. 按一下 **[新增]**。
    
5. 在 [ **新增地區路由** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路 interregional 路由的名稱。
    
6. 按一下 **[網路地區 #1]**，再從您要路由轉送至網路地區 #2 的清單中，按一下網路地區。
    
7. 按一下 **[網路地區 #2]**，再從您要路由轉送至網路地區 #1 的清單中，按一下網路地區。
    
8. 按一下 [**網路地區連結**] 欄位旁的 [**新增**]，然後新增網路地區連結，將用於網路 interregional 路由。
    
    > [!NOTE]
    > 如果您即將為尚未擁有直接網路地區連結的兩個網路地區建立路由，請新增所有必要的連結以便完成該路由。 例如，北 America/APAC 網路 interregional 路由需要兩個網路地區連結，因為兩者之間沒有任何直接的網路地區連結。 
  
9. 按一下 **[認可]**。
    
10. 若要完成建立拓撲的網路 interregional 路由，請使用其他網路 interregional 路由的設定重複步驟4到9。
    
## <a name="see-also"></a>另請參閱

[新 CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)