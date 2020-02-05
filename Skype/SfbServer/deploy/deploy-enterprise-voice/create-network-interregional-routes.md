---
title: 在商務用 Skype Server 中建立網路 interregional 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在商務用 Skype Server 中建立或修改企業語音通話許可控制所使用的網路 interregional 路由。
ms.openlocfilehash: 2a55e3e2028494a8bc9dc25164eaa67b08d35f83
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767926"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路 interregional 路由
 
在商務用 Skype Server 中建立或修改企業語音通話許可控制所使用的網路 interregional 路由。 
  
網路 interregional 路由定義一對網路區域之間的路由。 通話許可控制部署中的每一組網路區域都需要有網路 interregional 路由。 這可讓部署中的每個網路區域存取每一個其他區域。
  
雖然區域連結會針對區域之間的連線設定頻寬限制，但 interregional 路由決定了連線將從一個區域傳遞到另一個區域的連結路徑。
  
在範例拓朴中，您必須為三個地區對中的每一組定義網路 interregional 路由：北美/EMEA、EMEA/APAC，以及北美/APAC。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立網路 interregional 路由

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行**新的 CsNetworkInterRegionRoute** Cmdlet，以定義所需的路由。 例如，執行：
    
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
    > 北美/APAC 網路 interregional 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立網路 interregional 路由

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中，按一下 [**網路**設定]。
    
3. 按一下 [**地區路線**] 導覽按鈕。
    
4. 按一下 [**新增**]。
    
5. 在 [**新增地區路線**] 頁面上，按一下 [**名稱**]，然後輸入網路 interregional 路由的名稱。
    
6. 按一下 [**網路區域 #1**]，然後按一下清單中您要路由至 [網路區域] 的網路區域 #2。
    
7. 按一下 [**網路區域 #2**]，然後按一下清單中您要路由至 [網路區域] 的網路區域 #1。
    
8. 按一下 [**網路區域連結**] 欄位旁的 [**新增**]，然後新增將在網路 interregional 路由中使用的 [網路區域] 連結。
    
    > [!NOTE]
    > 如果您要為兩個網路區域建立路線，而這些區域之間沒有直接的網路區域連結，您必須新增所有必要的連結，才能完成路線。 例如，北美/APAC 網路 interregional 路由需要兩個網路區域連結，因為它們之間沒有直接的網路區域連結。 
  
9. 按一下 [認可]****。
    
10. 若要為您的拓撲完成建立網路 interregional 路由，請重複步驟4到9，並設定其他網路 interregional 路由。
    
## <a name="see-also"></a>另請參閱

[新-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[移除-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
