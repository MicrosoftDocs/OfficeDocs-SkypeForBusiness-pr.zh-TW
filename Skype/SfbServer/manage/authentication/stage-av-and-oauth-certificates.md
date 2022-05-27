---
title: 使用 -Roll in Set-CsCertificate，在 商務用 Skype Server 中暫存 AV 和 OAuth 憑證
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：暫存 AV 和 OAuth 憑證商務用 Skype Server。
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674605"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>使用 -Roll in Set-CsCertificate，在 商務用 Skype Server 中暫存 AV 和 OAuth 憑證

**總結：** 暫存 AV 和 OAuth 憑證商務用 Skype Server。

音訊/視訊 (A/V) 通訊是商務用 Skype Server的重要元件。 應用程式共用和音訊和視訊會議等功能依賴指派給 A/V Edge 服務的憑證，特別是 A/V 驗證服務。

> [!IMPORTANT]
> 這項新功能的設計適用于 A/V Edge 服務和 OAuthTokenIssuer 憑證。 其他憑證類型可以連同 A/V Edge 服務和 OAuth 憑證類型一起布建，但不會受益于 A/V Edge 服務憑證的共存行為。

用來管理商務用 Skype Server憑證的商務用 Skype Server管理命令介面 PowerShell Cmdlet 會將 A/V Edge 服務憑證稱為 AudioVideoAuthentication 憑證類型，而 OAuthServer 憑證則是 typeOAuthTokenIssuer。 針對本主題的其餘部分，若要唯一識別憑證，則會以相同的識別碼類型 AudioVideoAuthentication 和OAuthTokenIssuer 來參考這些憑證。

A/V 驗證服務是專用來核發 Token，以供用戶端和其他 A/V 取用者使用。 Token 是依據憑證上的屬性而產生，因此當憑證到期、連線中斷或必須重新加入時，就會導致新的憑證產生新的 Token。 商務用 Skype Server的新功能可減輕此問題 - 能夠在舊憑證到期之前暫存新憑證，並允許這兩個憑證繼續運作一段時間。 這項功能會在 Set-CsCertificate 商務用 Skype Server 管理命令介面 Cmdlet 中使用更新的功能。 具有現有參數 -EffectiveDate 的新參數 -Roll 會將新的 AudioVideoAuthentication 憑證放在憑證存放區中。 舊的 AudioVideoAuthentication 憑證仍會保留給已核發的 Token，以免其失效。 只要一將新的 AudioVideoAuthentication 憑證準備就緒，就會發生下列一系列的事件：

> [!TIP]
> 使用 商務用 Skype Server 管理命令介面 Cmdlet 來管理憑證，您可以針對 Edge Server 上的每個用途要求個別和不同的憑證。 在 [商務用 Skype Server 部署精靈] 中使用 [憑證精靈] 可協助您建立憑證，但通常是 **預設** 類型，會將 Edge Server 的所有憑證都與單一憑證搭配使用。 若您要使用彙總的憑證，建議的做法是將 AudioVideoAuthentication 憑證從其他憑證用途中獨立出來。 您可以佈建和臨時發出預設類型的憑證，但只有組合憑證的 AudioVideoAuthentication 部分可以臨時發出。 例如，參與 (的使用者在憑證到期時) 立即訊息交談，就必須登出並重新登入，才能使用與 Access Edge 服務相關聯的新憑證。 使用 Web Conferencing Edge 服務參與 Web 會議的使用者也會發生類似的行為。 OAuthTokenIssuer 憑證是一種特殊類型的憑證，在所有伺服器中都可以共用。 您可以在一個位置建立和管理憑證，而該憑證會儲存在所有其他伺服器的中央管理存放區中。

在使用 Set-CsCertificate Cmdlet 以及在目前的憑證過期前利用其來臨時發出憑證時，您也需要全盤理解您的選項和需求。 -Roll 參數很重要，但基本上是單一用途。 如果您將它定義為參數，您會告訴Set-CsCertificate您將提供 -Type (所定義之憑證的相關資訊，例如 AudioVideoAuthentication 和 OAuthTokenIssuer) ，憑證將在 -EffectiveDate 定義時生效。

 **-Roll**：-Roll 參數是必要的，而且具有必須與其一起提供的相依性。 下列為可完整定義哪些憑證將受影響以及套用方式的必要參數：

 **-EffectiveDate**：參數 -EffectiveDate 會定義新憑證與目前憑證共同作用的時機。 -EffectiveDate 可能接近目前憑證的到期時間，或是時間較長。 針對 AudioVideoAuthentication 憑證，建議的最小 -EffectiveDate 為 8 小時，這是使用 AudioVideoAuthentication 憑證發行的 AV Edge 服務權杖的預設權杖存留期。

臨時發出 OAuthTokenIssuer 憑證時，在讓憑證生效前的前置重疊時間方面有些不同的需求。OAuthTokenIssuer 憑證的最低前置重疊時間為目前憑證到期時間的前 24 小時。共存的延伸前置重疊時間則取決於和 OAuthTokenIssuer 憑證相依的其他伺服器角色而定 (例如 Exchange Server)，其在憑證所建立的驗證和加密金鑰內容方面可具備較長的保留時間。

 **-Thumbprint**：指紋是憑證上的一種屬性，且是唯一的。 -Thumbprint 參數可用來識別受 Set-CsCertificate Cmdlet 動作影響的憑證。

 **-Type**：-Type 參數可以接受單一憑證使用類型或以逗號分隔的憑證使用類型清單。 憑證類型是向 Cmdlet 和伺服器識別憑證用途的憑證類型。 例如，類型 AudioVideoAuthentication 可供 A/V Edge 服務和 AV 驗證服務使用。 如果您決定同時暫存和布建不同類型的憑證，您必須考慮憑證所需的最長最小有效前置時間。 例如，您需要暫存 AudioVideoAuthentication 和 OAuthTokenIssuer 類型的憑證。 您的最小 -EffectiveDate 必須是兩個憑證中較大的憑證，在此案例中為 OAuthTokenIssuer，其最小前置時間為 24 小時。 如果您不想要預備前置時間為 24 小時的 AudioVideoAuthentication 憑證，請使用更符合您需求的 EffectiveDate 個別暫存憑證。

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 參數更新或更新 A/V Edge 服務憑證

1. 以 Administrators 群組的成員身分登入本機電腦。

2. 使用 A/V Edge 服務上現有憑證的可匯出私密金鑰要求更新或新的 AudioVideoAuthentication 憑證。

3. 如果您已將集區部署) ，請將新的 AudioVideoAuthentication 憑證匯入至集區 (中的 Edge Server 和所有其他 Edge Server。

4. 使用 Set-CsCertificate Cmdlet 設定匯入的憑證，並搭配 -EffectiveDate 參數使用 -Roll 參數。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除 Token 生命週期 (預設為八小時)。 這可讓我們有時間讓憑證必須設定為使用中，而 是 -EffectiveDate \<string\> ：「7/22/2015 6：00：00 AM」。

   > [!IMPORTANT]
   > 針對 Edge 集區，您必須以部署之第一個憑證的 -EffectiveDate 參數所定義的日期和時間來部署和布建所有 AudioVideoAuthentication 憑證，以避免在所有用戶端和取用者權杖都使用新憑證更新之前，因為較舊的憑證到期而可能造成 A/V 通訊中斷。

   具有 -Roll 和 -EffectiveTime 參數的 Set-CsCertificate 命令：

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Set-CsCertificate 命令範例：

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate 必須格式化，以符合您伺服器的區域和語言設定。 範例是使用英文 (美國) 區域和語言設定

若要進一步瞭解 Set-CsCertificate、-Roll 和 -EffectiveDate 用來暫存發行新 AudioVideoAuthentication 權杖的新憑證，同時仍然使用現有的憑證來驗證取用者所使用的 AudioVideoAuthentication 的程式，視覺時間軸是瞭解程式的有效方式。 在下列範例中，系統管理員判斷 A/V Edge 服務憑證將于 2015 年 7 月 22 日下午 2：00：00 到期。 他要求並接收新的憑證，並將其匯入至其集區中的每個 Edge Server。 在 2015 年 7 月 22 日上午 2 點開始執行 Get-CsCertificate，其中 -Roll、 -Thumbprint 等於新憑證的指紋字串，而 -EffectiveTime 設定為 2015 年 7 月 22 日上午 6：00：00。 他在每部 Edge Server 上執行此命令。

![使用 Roll 和 EffectiveDate 參數。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|Callout|階段|
|:-----|:-----|
|1|開始時間：2015 年 7 月 22 日上午 12：00：00  <br/> 目前的 AudioVideoAuthentication 憑證將于 2015 年 7 月 22 日下午 2：00：00 到期。 這取決於憑證的到期時間戳記。 規劃憑證取代和變換，以在現有憑證達到到期時間之前，將預設權杖存留期 (重迭 8 小時) 。 此範例會使用 2：00：00 AM 前置時間，讓系統管理員有足夠的時間在上午 6：00：00 生效時間之前放置和布建新的憑證。|
|2|7/22/2015 上午 2：00：00 - 7/22/2015 上午 5：59：59  <br/> 在此範例中，設定 Edge Server 上有效時間為上午 6：00：00 (4 小時前置時間的憑證，但使用 Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate 可能較長) \<datetime string of the effective time for new certificate\>|
|3|7/22/2015 上午 6：00 - 7/22/2015 下午 2：00  <br/> 若要驗證權杖，會先嘗試新的憑證，如果新憑證無法驗證權杖，則會嘗試舊憑證。 此程式用於預設權杖存留期) 重迭期間的 8 小時 (所有權杖。|
|4 |結束：7/22/2015 下午 2：00：01  <br/> 舊憑證已過期，而新的憑證已接管。 您可以使用 Remove-CsCertificate -Type \<certificate usage type\> -Previous 安全地移除舊憑證|

當有效時間 (2015 年 7 月 22 日上午 6：00：00) 時，所有新的權杖都會由新的憑證發出。 驗證 Token 時，會先以新的憑證來加以驗證。 若驗證失敗，就會嘗試舊的憑證。 直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。 舊憑證 (在 2015 年 7 月 22 日下午 2：00：00) 過期後，只有新的憑證才會驗證權杖。 您可以使用 Remove-CsCertificate Cmdlet 搭配 -Previous 參數安全地移除舊憑證。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 -Roll 和 -EffectiveDate 參數更新或更新 OAuthTokenIssuer 憑證

1. 以 Administrators 群組的成員身分登入本機電腦。

2. 使用前端伺服器上現有憑證的可匯出私密金鑰要求更新或新的 OAuthTokenIssuer 憑證。

3. 如果您已將集區部署) ，請將新的 OAuthTokenIssuer 憑證匯入集區 (的前端伺服器。 OAuthTokenIssuer 憑證是全域複寫的，因此僅需在部署中的任何伺服器上加以更新即可。 前端伺服器會作為範例使用。

4. 使用 Set-CsCertificate Cmdlet 設定匯入的憑證，並搭配 -EffectiveDate 參數使用 -Roll 參數。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除至少 24 小時。

    具有 -Roll 和 -EffectiveTime 參數的 Set-CsCertificate 命令：

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Set-CsCertificate 命令範例：

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> EffectiveDate 必須格式化，以符合您伺服器的區域和語言設定。 範例是使用英文 (美國) 區域和語言設定

當有效時間 (2015 年 7 月 21 日上午 1：00：00) 時，所有新的權杖都會由新的憑證發出。 驗證 Token 時，會先以新的憑證來加以驗證。 若驗證失敗，就會嘗試舊的憑證。 直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。 舊憑證 (在 2015 年 7 月 22 日下午 2：00：00) 過期後，只有新的憑證才會驗證權杖。 您可以使用 Remove-CsCertificate Cmdlet 搭配 -Previous 參數安全地移除舊憑證。

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>另請參閱

[在 商務用 Skype Server 中管理 OAuth) 和夥伴應用程式 (伺服器對伺服器驗證](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
