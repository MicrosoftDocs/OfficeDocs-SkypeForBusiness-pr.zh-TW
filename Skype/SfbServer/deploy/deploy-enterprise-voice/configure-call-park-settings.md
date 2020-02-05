---
title: 在商務用 Skype 中設定通話寄存設定
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
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 在商務用 Skype Server Enterprise Voice 中修改通話駐留設定。
ms.openlocfilehash: e9410d3b088e5978588de991aeaa9da73327f50a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768126"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>在商務用 Skype 中設定通話寄存設定

在商務用 Skype Server Enterprise Voice 中修改通話駐留設定。

如果您不想使用預設的通話駐留設定，您可以進行自訂。 當您安裝 [通話駐留] 應用程式時，系統會根據預設設定全域設定。 您可以修改全域設定，也可以指定網站專用的設定。 使用**新的 CsCpsConfiguration** Cmdlet 來建立新的網站特定設定。 使用**CsCpsConfiguration** Cmdlet 來修改現有的設定。

> [!NOTE]
> 我們建議您針對備用目的地設定**OnTimeoutURI**選項，以便在停用通話超時和 ringback 失敗時使用。

使用**新的 CsCpsConfiguration** Cmdlet 或**CsCpsConfiguration** Cmdlet 來設定下列任何設定：


| **此選項：**                     | **指定：**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 通話結束之後，在撥打電話給接聽電話的電話之前所經過的時間長度。  <br/> 此值必須以 hh： mm： ss 格式輸入，以指定小時、分鐘和秒。 最小值為10秒，最大值為10分鐘。 預設值為00:01:30。  <br/> |
| **EnableMusicOnHold** <br/>          | 通話停用時，是否會在來電者中播放音樂。  <br/> 值為 True 或 False。 預設值為 True。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 寄存來電在轉寄到指定給**OnTimeoutURI**的回退統一資源識別項（URI）之前，響鈴給應答電話的次數。 預設值為1。  <br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | 在超過**MaxCallPickupAttempts**時傳送未應答之暫停呼叫的使用者或回應群組的 SIP 位址。 <br/> Value 必須是以 [字串 SIP：] 開頭的 SIP URI。 例如，sip:bob@contoso.com。 預設值為 [沒有轉寄位址]。  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a>若要設定通話寄存設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。

2. 用盡

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 使用**CsSite** Cmdlet 來識別網站。 如需詳細資訊，請參閱商務用 Skype Server Management 命令介面檔。

    例如：

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>另請參閱

[在保留 inSkype for Business 2015 上自訂通話寄存音樂](customize-call-park-music-on-hold.md)

[新-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
