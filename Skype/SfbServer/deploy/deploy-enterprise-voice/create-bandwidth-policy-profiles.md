---
title: 在商務用 Skype Server 中建立頻寬原則設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 建立或修改在商務用 Skype Server 的 [企業語音通話許可控制] 中所使用的頻寬原則。
ms.openlocfilehash: c7fecafe5f036405088a3c6c62b70774b779e266
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191341"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>在商務用 Skype Server 中建立頻寬原則設定檔 
 
建立或修改在商務用 Skype Server 的 [企業語音通話許可控制] 中所使用的頻寬原則。 
  
頻寬原則定義即時音訊與視頻形式的頻寬使用量限制。 頻寬原則會套用至 tobandwidth 原則設定檔, 可套用至多個網路網站以進行通話許可控制。
  
如需在 CAC 部署中應設定哪些頻寬限制的相關指導方針, 請參閱[在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
下列程式中建立的範例原則設定了整體音訊流量、個別音訊會話、整體影片流量, 以及個別的視頻會話限制。 例如, 5Mb_Link 頻寬原則設定檔會設定下列限制: 
  
- 音訊限制: 2000 kbps
    
- 音訊會話限制: 200 kbps
    
- 影片限制: 1400 kbps
    
- 影片會話限制: 700 kbps
    
> [!NOTE]
> 最小音訊會話限制值為 40 kbps。 最小的視頻會話限制值為 100 kbps。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 建立頻寬原則設定檔

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 針對您想要建立的每一個頻寬原則設定檔, 執行新的 CsNetworkBandwidthPolicyProfile Cmdlet。 例如，執行：
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立頻寬原則設定檔

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中, 按一下 [**網路**設定]。
    
3. 按一下 [**原則設定檔**] 導覽按鈕。
    
4. 按一下 [**新增**]。
    
5. 在 [**新增原則設定檔**] 頁面上, 按一下 [**名稱**], 然後輸入頻寬原則設定檔的名稱。
    
6. 按一下 [**音訊限制**], 然後輸入允許所有音訊會話合併的最大 kbps 數。
    
7. 按一下 [**音訊會話限制**], 然後輸入每個個別音訊會話允許的最大 kbps 數。
    
8. 按一下 [**影片限制**], 然後輸入允許所有視頻會話合併的最大 kbps 數。
    
9. 按一下 [**視頻會話限制**], 然後輸入每個個別影片會話允許的最大 kbps 數。
    
10. 或者, 按一下 [**描述**], 然後輸入其他資訊來描述此頻寬原則設定檔。
    
11. 按一下 [認可]****。
    
12. 若要完成建立拓撲的頻寬原則設定檔, 請重複步驟4到 11, 以及其他頻寬策略設定檔的設定。
    
## <a name="see-also"></a>另請參閱

[新-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[移除-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
