---
title: 刪除商務用 Skype Server 中現有的 SIP 幹線設定集合
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '摘要: 瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。'
ms.openlocfilehash: 830f5c42e26c4ef7a5ffca0a57fc7e70c2509f83
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189037"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>刪除商務用 Skype Server 中現有的 SIP 幹線設定集合
 
**摘要:** 瞭解如何使用商務用 Skype Server [控制台] 刪除主幹設定的集合。
  
SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 eXchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。 這些設定會以指定的方式執行以下操作:
  
- 是否應該在 trunks 上啟用媒體旁路。
    
- 傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。
    
- 每個幹線是否都需要安全的即時傳輸通訊協定 (SRTP) 加密。
    
當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。 這個全域設定集合無法刪除。 不過, 您可以使用商務用 Skype Server 的 [控制台] 或 [ [new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) ] Cmdlet, 將全域集合中的屬性 "reset" 成預設值。 例如, 如果您已將 Enable3pccRefer 屬性設為 True, 當您重設全域集合時, Enable3pccRefer 屬性將會還原為預設值 False。
  
系統管理員也可以在網站範圍或服務範圍 (針對個別 PSTN 閘道) 建立自訂主幹設定設定。您可以移除這些自訂設定。 移除這些自訂設定時, 請記住下列事項:
  
- 如果您移除服務範圍設定, 這些設定所管理的 SIP 幹線將由套用至其網站的設定來管理 (如果存在的話)。 如果網站設定不存在, 這些 trunks 就會受到中繼設定設定的全域集合的管理。
    
- 如果您移除網站範圍的設定, 由這些設定所管理的任何 SIP trunks 現在都將由「中繼設定」全域集合來管理。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>若要在商務用 Skype Server 控制台中移除主幹設定設定

1. 在商務用 Skype Server 的 [控制台] 中, 按一下 [**語音路由**], 然後按一下 [**幹線配置**]。
    
2. 在 [**幹線**設定] 索引標籤上, 選取要刪除的 SIP 中繼設定的集合, 按一下 [**編輯**], 然後按一下 [**刪除**]。 若要在相同的作業中刪除多個集合, 請按一下要刪除的第一個集合, 然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。
    
3. 集合的**State**屬性會更新為**未提交**。 若要確認變更, 並刪除收藏, 請按一下 [**認可**], 然後按一下 [**全部確認**]。
    
4. 在 [**未提交的語音設定**] 對話方塊中, 按一下 **[確定]**。
    
5. 在**商務用 Skype Server**的 [控制台] 對話方塊中, 按一下 **[確定]**。
    
6. 如果您改變主意, 並決定不刪除收藏, 請按一下 [**認可**], 然後按一下 [**取消所有未提交的變更**]。 當**商務用 Skype Server [控制台**] 對話方塊出現時, 請按一下 **[確定]**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用商務用 Skype Server Management Shell Cmdlet 移除主幹設定設定

您可以使用商務用 Skype Server Management 命令介面和**new-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。 您可以從商務用 Skype Server Management 命令介面或從商務用 Skype Server Management Shell 的遠端會話執行此 Cmdlet。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>移除指定的設定集合

- 下列命令會移除套用至雷德蒙網站的幹線設定設定:
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的集合

- 這個命令會移除所有已套用至服務範圍的中繼設定設定:
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>若要移除已啟用媒體旁路的所有集合

- 下列命令會移除已啟用媒體略過的所有主幹設定設定:
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

如需詳細資訊, 請參閱[Remove new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) Cmdlet 的說明主題。
  

