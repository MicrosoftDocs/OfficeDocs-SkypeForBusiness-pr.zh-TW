---
title: 商務用 Skype Server-刪除現有的 SIP 主幹設定的集合
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
description: 'SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。 '
ms.openlocfilehash: 09e51dd54401b761c448872545111e8bebf01599
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760611"
---
# <a name="skype-for-business-server---delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>商務用 Skype Server-刪除現有的 SIP 主幹設定的集合

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

- 主幹是否啟用媒體旁路。
- 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。
- 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此設定的全域集合無法刪除。 不過，您可以使用 [商務用 Skype ServerControl] 面板或[Remove-get-cstrunkconfiguration 指令程式](/powershell/module/skype/Remove-CsTrunkConfiguration)，將全域集合中的屬性「重設」為其預設值。 例如，如果已將 Enable3pccRefer 屬性設為 True，則在重設全域集合時，Enable3pccRefer 屬性會還原為預設值 False。

管理員也可建立網站範圍或服務範圍 (針對個別 PSTN 閘道) 的自訂主幹組態設定；這些自訂設定是可移除的。移除這些自訂設定時，請注意下列事項：

- 如移除服務範圍設定，原先這些設定所管理的 SIP 主幹會由套用網站的設定來管理 (如果存在的話)。如果網站設定不存在，這些主幹將會由主幹組態設定的全域集合來管理。
- 如移除網站範圍設定，則所有原先這些設定管理的 SIP 主幹將會由主幹組態設定的全域集合來管理。

**使用商務用 Skype Server 控制台移除主幹設定設定** 

1. 在 [商務用 Skype Server 控制台] 中，按一下 [**語音路由**]，然後按一下 [**主幹** 設定]。
2. 在 [ **主幹** 設定] 索引標籤上，選取要刪除的 SIP 主幹設定的集合，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。 如要在同一個操作中刪除多個集合，先按一下要刪除的第一個集合，然後按住 Ctrl 鍵，再按一下其他任何要移除的集合。
3. 集合的 **[狀態]** 屬性將會更新為 **[未認可]**。如要認可變更並刪除集合，請按一下 **[認可]**，然後按一下 **[全部認可]**。
4. 在 **[未認可的語音組態設定]** 對話方塊中，按一下 **[確定]**。
5. 在 [**商務用 Skype Server 控制台**] 對話方塊中，按一下 **[確定]**。
6. 如果您變更主意並決定不刪除集合，請按一下 [ **認可**]，然後按一下 [ **取消所有未** 認可的變更]。 出現 **商務用 Skype Server 控制台**] 對話方塊時，按一下 **[確定]**。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除主幹設定設定


您可以使用 Windows PowerShell 和 **get-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 

**移除指定的設定集合**

以下命令會移除已套用至 Redmond 網站的主幹組態設定：

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**若要移除所有套用至網站範圍的集合**

以下命令會移除所有已套用至服務範圍的主幹組態設定：

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**移除啟用媒體旁路的所有集合**

以下命令會移除所有已啟用媒體旁路的主幹組態設定：

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

如需詳細資訊，請參閱 [get-cstrunkconfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) Cmdlet 的 [說明] 主題。
