---
title: 設定商務用 Skype 中的通話駐留設定
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改商務用 Skype Server 企業語音中的通話駐留設定。
---

# <a name="configure-call-park-settings-in-skype-for-business"></a>設定商務用 Skype 中的通話駐留設定

修改商務用 Skype Server 企業語音中的通話駐留設定。

如果您不想要使用預設的通話駐留設定，可以進行自訂。 當您安裝通話駐留應用程式時，系統會預設設定全域設定。 您可以修改全域設定，也可以指定網站特定設定。 使用 **New-CsCpsConfiguration** Cmdlet 可建立新的網站特定設定。 使用 **Set-CsCpsConfiguration** Cmdlet 可修改現有設定。

> [!NOTE]
> 建議您至少設定 **OnTimeoutURI** 選項，作為當駐留通話逾時且回撥失敗時的後援目的地。

使用 **New-CsCpsConfiguration** Cmdlet 或 **Set-CsCpsConfiguration** Cmdlet 進行下列任何一項設定：


| **此選項：**                     | **指定：**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | 從駐留通話之後到回撥原先接聽該通話的電話之前，需經過的時間長度。  <br/> 此值必須以 hh:mm:ss 格式輸入，以指定小時、分鐘和秒數。最小值為 10 秒，最大值為 10 分鐘。預設值為 00:01:30。  <br/> |
| **EnableMusicOnHold** <br/>          | 駐留通話時是否對來電者播放音樂。  <br/> 值為 True 或 False。預設為 True。  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | 在將駐留通話轉接至 **OnTimeoutURI** 指定的後援統一資源識別元 (URI) 之前，需將駐留通話回撥至當初接聽該通話的次數。預設值為 1。<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | 在超過 **MaxCallPickupAttempts** 時，將未接聽的駐留通話路由至的使用者或回應群組的 SIP 位址。 <br/> 值必須是以字串 sip: 開頭的 SIP URI。例如，sip:bob@contoso.com。預設沒有轉接位址。<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>設定通話駐留設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

2. 運行：

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > 使用 **Get-CsSite** Cmdlet 來識別網站。 如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。

    例如：

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>另請參閱

[自訂通話駐留 inSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)