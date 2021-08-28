---
title: 商務用 Skype Server：測試 SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要：瞭解如何使用商務用 Skype Server 管理命令介面來測試 SIP 主幹設定設定。
ms.openlocfilehash: 08bcbc0548af42b7242047ce9c848f00f1af7096
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616999"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>商務用 Skype Server：測試 SIP 主幹設定設定
 
**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面來測試 SIP 主幹設定設定。
  
SIP 主幹設定設定定義轉送伺服器和公用交換電話網路 (PSTN) 閘道、IP-Public 分支 eXchange (PBX) 或會話邊界控制器（在服務提供者上 (SBC) ）之間的關聯性和功能。 這些設定將指定下列項目：
  
- 是否應該在主幹上啟用媒體旁路
    
- 在哪個條件下會傳送即時傳輸控制通訊協定 (RTCP) 封包
    
- 每個主幹是否需要安全即時傳輸通訊協定 (SRTP) 加密
    
當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (為 PSTN 閘道服務建立自訂設定集合，只會) 。 管理員也可以使用 Test-CsTrunkConfiguration Cmdlet 來驗證主幹是否可將使用者所撥打的號碼轉換為閘道可以處理的號碼。
  
您只能使用 Windows PowerShell 和[Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration) Cmdlet 來測試主幹設定設定。 您可以從商務用 Skype Server 管理命令介面或從商務用 Skype Server 管理命令介面的遠端會話執行此 Cmdlet。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>測試 SIP 主幹設定設定

- 這個命令會驗證 Redmond 網站的主幹設定設定是否可以正確地轉換撥打的號碼4255551212。
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
