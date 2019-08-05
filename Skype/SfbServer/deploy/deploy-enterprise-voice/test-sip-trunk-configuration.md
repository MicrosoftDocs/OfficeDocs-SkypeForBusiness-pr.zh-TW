---
title: 在商務用 Skype Server 中測試 SIP 幹線設定設定
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
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '摘要: 瞭解如何使用商務用 Skype Server Management Shell 來測試 SIP 幹線設定設定。'
ms.openlocfilehash: aec88300341f42d5f228c3c13f1a0925b71ce855
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193262"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中測試 SIP 幹線設定設定
 
**摘要:** 瞭解如何使用商務用 Skype Server Management Shell 來測試 SIP 幹線設定設定。
  
SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 eXchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。 這些設定會以指定的方式執行以下操作:
  
- 是否應該在 trunks 上啟用媒體旁路。
    
- 傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。
    
- 每個幹線是否都需要安全的即時傳輸通訊協定 (SRTP) 加密。
    
當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。 此外, 管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 上建立自訂設定集合。 系統管理員也可以使用 New-cstrunkconfiguration Cmdlet 來驗證主幹能將使用者撥出的號碼轉換成可由閘道處理的數位。
  
只能使用 Windows PowerShell 和[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) Cmdlet 來測試幹線設定設定。 這個 Cmdlet 可以從商務用 Skype Server Management 命令介面或從商務用 Skype Server Management Shell 的遠端會話執行。
  
### <a name="to-test-sip-trunk-configuration-settings"></a>測試 SIP 幹線設定設定

- 這個命令會驗證雷德蒙網站的幹線設定設定可以正確地轉換撥打的號碼4255551212。
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


