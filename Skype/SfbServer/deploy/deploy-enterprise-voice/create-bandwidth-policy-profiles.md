---
title: 在商務用 Skype Server 中建立頻寬原則設定檔
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 在商務用 Skype Server 中建立或修改頻寬原則，以供 Enterprise Voice 通話許可控制使用。
ms.openlocfilehash: 9458c5576d2c89254c4ee6477ede33c010cb4a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093241"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>在商務用 Skype Server 中建立頻寬原則設定檔 
 
在商務用 Skype Server 中建立或修改頻寬原則，以供 Enterprise Voice 通話許可控制使用。 
  
頻寬原則定義即時音訊和影片形式的頻寬使用量限制。 頻寬原則會套用至 tobandwidth 原則設定檔，可套用至多個網站以取得通話許可控制。
  
如需您在 CAC 部署中應該設定什麼頻寬限制的指導方針，請參閱 [在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
下列程式中建立的範例原則，會設定整體音訊流量、個別音訊會話、整體影片流量和個別影片的限制。 例如，5Mb_Link 頻寬原則設定檔會設定下列限制： 
  
- 音訊限制： 2000 kbps
    
- 音訊會話限制： 200 kbps
    
- 影片限制： 1400 kbps
    
- 影片會話限制： 700 kbps
    
> [!NOTE]
> 最小音訊會話限制值為 40 kbps。 最小影片會話限制值為 100 kbps。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面建立頻寬原則設定檔

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。
    
2. 針對您要建立的每個頻寬原則設定檔，執行 New-CsNetworkBandwidthPolicyProfile Cmdlet。 例如，執行：
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立頻寬原則設定檔

1. 開啟商務用 Skype Server 控制台。
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 按一下 [ **原則設定檔** ] 瀏覽按鈕。
    
4. 按一下 [ **新增**]。
    
5. 在 [ **新增原則設定檔** ] 頁面上，按一下 [ **名稱** ]，然後輸入頻寬原則設定檔的名稱。
    
6. 按一下 [ **音訊限制**]，然後輸入允許所有音訊會話組合的最大 kbps 數。
    
7. 按一下 [ **音訊會話限制**]，然後輸入每個個別音訊會話允許的最大 kbps 數。
    
8. 按一下 [ **影片限制**]，然後輸入要允許所有視頻會話組合的最大 kbps 數。
    
9. 按一下 [ **影片會話限制**]，然後輸入每個個別影片會話允許的最大 kbps 數。
    
10. （選用）按一下 [ **描述**]，然後輸入其他資訊以描述此頻寬原則設定檔。
    
11. 按一下 **[認可]**。
    
12. 若要完成建立拓撲的頻寬原則設定檔，請使用其他頻寬原則設定檔的設定重複步驟4到11。
    
## <a name="see-also"></a>另請參閱

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)