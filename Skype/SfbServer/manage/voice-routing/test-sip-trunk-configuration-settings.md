---
title: 在商務用 Skype Server 中測試 SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。 '
ms.openlocfilehash: 1489fe1e45223bac6b62ed23a09212a569ea7838
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826183"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中測試 SIP 主幹設定設定

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

- 主幹是否啟用媒體旁路。
- 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。
- 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。 管理員也可以使用 [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) Cmdlet 來驗證主幹是否可將使用者所撥打的號碼轉換為閘道可以處理的號碼。

您只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration Cmdlet 來測試主幹設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 

**測試 SIP 主幹設定設定**

這個命令會驗證 Redmond 網站的主幹設定設定是否可以正確地轉換撥打的號碼4255551212。

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
