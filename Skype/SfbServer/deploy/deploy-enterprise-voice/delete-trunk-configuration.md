---
title: 商務用 Skype Server：刪除現有的 SIP 主幹設定的集合
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要：瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。
ms.openlocfilehash: 8927b06c3945be48685f13f33dcee83ff08ae653ade5b2d51228407a3554ef70
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307844"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>商務用 Skype Server：刪除現有的 SIP 主幹設定的集合 
 
**摘要：** 瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。
  
SIP 主幹設定設定定義轉送伺服器和公用交換電話網路 (PSTN) 閘道、IP-Public 分支 eXchange (PBX) 或會話邊界控制器（在服務提供者上 (SBC) ）之間的關聯性和功能。 這些設定將指定下列項目：
  
- 是否應該在主幹上啟用媒體旁路
    
- 在哪個條件下會傳送即時傳輸控制通訊協定 (RTCP) 封包
    
- 在每個主幹上是否需要 (SRTP) 加密的安全即時傳輸通訊協定
    
當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此設定的全域集合無法刪除。 不過，您可以使用商務用 Skype Server 控制台或[get-cstrunkconfiguration 指令程式](/powershell/module/skype/remove-cstrunkconfiguration)，將全域集合中的屬性「重設」為其預設值。 例如，如果已將 Enable3pccRefer 屬性設為 True，則在重設全域集合時，Enable3pccRefer 屬性會還原為預設值 False。
  
管理員也可建立網站範圍或服務範圍 (針對個別 PSTN 閘道) 的自訂主幹組態設定；這些自訂設定是可移除的。 移除這些自訂設定時，請記住下列事項：
  
- 如移除服務範圍設定，原先這些設定所管理的 SIP 主幹會由套用網站的設定來管理 (如果存在的話)。如果網站設定不存在，這些主幹將會由主幹組態設定的全域集合來管理。
    
- 如果您移除網站範圍的設定，則這些設定所管理的任何 SIP 主幹現在都會由主幹設定設定的全域集合來管理。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台移除主幹設定設定

1. 在商務用 Skype Server 控制台] 中，按一下 [**語音路由**]，然後按一下 [**主幹** 設定]。
    
2. 在 [ **主幹** 設定] 索引標籤上，選取要刪除的 SIP 主幹設定的集合，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。 若要在相同的作業中刪除多個集合，請按一下要刪除的第一個集合，然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。
    
3. 集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。
    
4. 在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。
    
5. 在 [**商務用 Skype Server 控制台**] 對話方塊中，按一下 **[確定]**。
    
6. 如果您改變心意決定不要刪除集合，請按一下 **[認可]**，然後按一下 **[取消所有未認可的變更]**。 出現 **商務用 Skype Server 控制台**] 對話方塊時，按一下 **[確定]**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用商務用 Skype Server 管理命令介面 Cmdlet 移除主幹設定設定

您可以使用商務用 Skype Server 管理命令介面和 **get-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。 您可以從商務用 Skype Server 管理命令介面或從商務用 Skype Server 管理命令介面的遠端會話中執行此指令程式。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>移除指定的設定集合

- 以下命令會移除已套用至 Redmond 網站的主幹組態設定：
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的集合

- 以下命令會移除所有已套用至服務範圍的主幹組態設定：
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>移除啟用媒體旁路的所有集合

- 以下命令會移除所有已啟用媒體旁路的主幹組態設定：
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

如需詳細資訊，請參閱 [get-cstrunkconfiguration](/powershell/module/skype/remove-cstrunkconfiguration) Cmdlet 的 [說明] 主題。
