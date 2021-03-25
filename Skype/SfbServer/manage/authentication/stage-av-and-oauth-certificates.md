---
title: 在商務用 Skype Server 中的階段 AV 和 OAuth 憑證 Set-CsCertificate 中使用-擲入
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
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：為商務用 Skype Server 階段 AV 和 OAuth 憑證。
ms.openlocfilehash: 87527d4bb51a5c38e0f85f72b299b67f235f2cf8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119562"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>在商務用 Skype Server 中的階段 AV 和 OAuth 憑證 Set-CsCertificate 中使用-擲入
 
**摘要：** 階段 AV 和 OAuth 商務用 Skype Server 的憑證。
  
Audio/Video (A/V) 通訊是商務用 Skype Server 的主要元件。 「應用程式共用」和「音訊」及「視訊會議」等功能會依賴指派給 A/V Edge service 的憑證，尤其是 A/V 驗證服務。
  
> [!IMPORTANT]
> 這項新功能的設計目的是用於 A/V Edge service 和 OAuthTokenIssuer 憑證。 其他憑證類型可以搭配「A/V Edge service」和「OAuth 憑證」類型進行布建，但不會受益于 A/V Edge service 憑證所用的共存行為。
  
商務用 Skype Server 管理命令介面 PowerShell 用來管理商務用 Skype Server 憑證的指令程式是指 A/V Edge service 憑證作為 AudioVideoAuthentication 憑證類型和 Microsoft.rtc.management.writableconfig.settings.ssauth.oauthserver 憑證做為 typeOAuthTokenIssuer。 如需本主題的其餘部分，以及唯一識別憑證，則會使用相同的識別碼類型，AudioVideoAuthentication andOAuthTokenIssuer。
  
A/V 驗證服務是專用來核發 Token，以供用戶端和其他 A/V 取用者使用。 Token 是依據憑證上的屬性而產生，因此當憑證到期、連線中斷或必須重新加入時，就會導致新的憑證產生新的 Token。 商務用 Skype Server 中的新功能會緩解這項問題，也就是在舊憑證即將到期，並且允許兩個憑證在一段時間內繼續運作的能力。 此功能使用 Set-CsCertificate 商務用 Skype Server 管理命令介面 Cmdlet 中的更新功能。 新的參數滾（-EffectiveDate 現有的參數）會將新的 AudioVideoAuthentication 憑證放置於憑證存放區中。 舊的 AudioVideoAuthentication 憑證仍會保留給已核發的 Token，以免其失效。 只要一將新的 AudioVideoAuthentication 憑證準備就緒，就會發生下列一系列的事件：
  
> [!TIP]
> 使用商務用 Skype Server 管理命令介面 Cmdlet 來管理憑證，您可以針對 Edge Server 上的每個用途要求個別且獨特的憑證。 在商務用 Skype 伺服器部署中使用憑證嚮導可協助您建立憑證，但通常是將 Edge Server 所有憑證使用的 **預設** 類型，放在單一憑證上。 若您要使用彙總的憑證，建議的做法是將 AudioVideoAuthentication 憑證從其他憑證用途中獨立出來。 您可以佈建和臨時發出預設類型的憑證，但只有組合憑證的 AudioVideoAuthentication 部分可以臨時發出。  (中的使用者，例如，當憑證到期時，立即訊息交談) 需要登出和登入，以利用與 Access Edge service 相關聯的新憑證。 在使用 Web 會議 Edge service 的 Web 會議中，使用者會發生類似行為。 OAuthTokenIssuer 憑證是一種特殊類型的憑證，在所有伺服器中都可以共用。 您可以在一個位置建立及管理憑證，並將憑證儲存在所有其他伺服器的中央管理存放區中。
  
在使用 Set-CsCertificate Cmdlet 以及在目前的憑證過期前利用其來臨時發出憑證時，您也需要全盤理解您的選項和需求。 -擺參數很重要，但實質上只是單一用途。 如果您將它定義為參數，您會告訴 Set-CsCertificate，您將會提供受影響之憑證的相關資訊，例如 AudioVideoAuthentication 和 OAuthTokenIssuer) ，當憑證將會在-EffectiveDate 中所定義時，將會 (受到影響。
  
 **-** 滾參數是必要的，且具有必須與其一起提供的相依性。 下列為可完整定義哪些憑證將受影響以及套用方式的必要參數：
  
 **-EffectiveDate**：此參數-EffectiveDate 會定義何時新的憑證會使用目前憑證成為共同作用。 -EffectiveDate 可以接近目前憑證的到期時間，也可以是較長的一段時間。 AudioVideoAuthentication 憑證的建議最低-EffectiveDate 為8小時，也就是使用 AudioVideoAuthentication 憑證發行之 AV Edge service 權杖的預設權杖存留時間。
  
臨時發出 OAuthTokenIssuer 憑證時，在讓憑證生效前的前置重疊時間方面有些不同的需求。OAuthTokenIssuer 憑證的最低前置重疊時間為目前憑證到期時間的前 24 小時。共存的延伸前置重疊時間則取決於和 OAuthTokenIssuer 憑證相依的其他伺服器角色而定 (例如 Exchange Server)，其在憑證所建立的驗證和加密金鑰內容方面可具備較長的保留時間。
  
 **-Thumbprint**：指紋是憑證上的一種屬性，且是唯一的。 -Thumbprint 參數是用來識別 Set-CsCertificate Cmdlet 的動作會影響的憑證。
  
 **-Type**：-type 參數可接受單一憑證使用類型或以逗號分隔的憑證使用類型清單。 憑證類型是指識別 Cmdlet 和伺服器的憑證用途的憑證類型。 例如，輸入 AudioVideoAuthentication 供 A/V Edge service 和 AV 驗證服務使用。 如果您決定同時暫存及布建其他類型的憑證，則必須考慮憑證的最長必要有效前置時間。 例如，您必須暫存 AudioVideoAuthentication 和 OAuthTokenIssuer 類型的憑證。 您的最低-EffectiveDate 必須是兩個憑證中的較大者，在此案例中是 OAuthTokenIssuer，其最小前置時間為24小時。 如果您不想要將前置時間的 AudioVideoAuthentication 憑證暫存為24小時，請使用更多您的需求 EffectiveDate 進行暫存。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用滾及-EffectiveDate 參數更新或更新 A/V Edge service 憑證

1. 以 Administrators 群組成員的身分登入本機電腦。
    
2. 以 A/V Edge service 上現有憑證的可匯出私密金鑰要求更新或新 AudioVideoAuthentication 憑證。
    
3. 將新的 AudioVideoAuthentication 憑證匯入至 Edge Server，以及集區中的所有其他 Edge Server (如果您已部署) 集區。
    
4. 使用 Set-CsCertificate Cmdlet 來設定匯入的憑證，並使用-擲參數搭配-EffectiveDate 參數。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除 Token 生命週期 (預設為八小時)。 這為我們提供了必須將憑證設定為使用中的時間，且為-EffectiveDate \<string\> ： "7/22/2015 6:00:00 AM」。 
    
    > [!IMPORTANT]
    > 對於 Edge 集區，您必須使用部署的第一個憑證的-EffectiveDate 參數所定義的日期和時間來部署及布建所有 AudioVideoAuthentication 憑證，以避免因舊憑證的破壞，但在使用新的憑證更新所有用戶端和使用者權杖之前，A/V 可能會造成的通訊中斷。 
  
    具有-滾及-EffectiveTime 參數的 Set-CsCertificate 命令：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Set-CsCertificate 命令範例：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate 必須設定格式，以符合伺服器的區域及語言設定。 範例是使用英文 (美國) 區域和語言設定 
  
若要進一步瞭解 Set-CsCertificate、滾及-EffectiveDate 使用現有憑證以驗證消費者所使用之 AudioVideoAuthentication 的新憑證 AudioVideoAuthentication 的處理常式，則 visual 時程表是瞭解該程式所使用之的有效方法。 在下列範例中，管理員會判斷 A/V Edge service 憑證是在07/22/2015 上的 2:00:00 PM 到期。 他要求並接收新的憑證，並將它匯入至其集區中的每個 Edge Server。 在07/22/2015 的淩晨2點，他開始執行 Get-CsCertificate，並以與新憑證的指紋字串相等的方式執行，並將-EffectiveTime 設定為 07/22/2015 6:00:00 AM。 在每一部 Edge Server 上執行此命令。
  
![使用擲及 EffectiveDate 參數。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stage**|
|:-----|:-----|
|1  <br/> |開始： 7/22/2015 12:00:00 AM  <br/> 目前的 AudioVideoAuthentication 憑證是由於7/22/2015 于 2:00:00 PM 到期。 這取決於憑證上到期的時間戳記。 規劃您的憑證取代和翻轉，以計算8小時的重疊 (預設權杖存留期) 在現有憑證達到到期時間之前。 在此範例中，會使用 2:00:00 AM 前置時間，讓系統管理員有足夠的時間來預先設定新憑證，並在6:00:00 上午的時間前進行布建。  <br/> |
|2   <br/> |7/22/2015 2:00:00 AM-7/22/2015 5:59:59 AM  <br/> 在 Edge Server 上設定憑證，有效期為 6:00:00 AM (4 小時內推時間為此範例，但可使用 Set-CsCertificate 類型 \<certificate usage type\> 的指紋-EffectiveDate) 更長的時間。 \<thumbprint of new certificate\>\<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |7/22/2015 6:00 AM-7/22/2015 2:00 下午  <br/> 若要驗證權杖，請先嘗試新的憑證，如果新的憑證無法驗證權杖，就會嘗試舊的憑證。 此程式適用于8小時 (預設權杖存留期) 重疊期間內的所有標記。  <br/> |
|4   <br/> |結束： 7/22/2015 2:00:01 PM  <br/> 舊憑證已過期，且已取得新憑證。 舊憑證可以安全地移除，使用 Remove-CsCertificate 類型 \<certificate usage type\> 先前版本  <br/> |
   
當達到有效時間時 (7/22/2015 6:00:00 AM) ，所有新的權杖都會以新的憑證發出。 驗證 Token 時，會先以新的憑證來加以驗證。 若驗證失敗，就會嘗試舊的憑證。 直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。 一旦舊憑證到期 (7/22/2015 2:00:00 PM) ，權杖只會由新的憑證驗證。 舊憑證可以使用具有-上一個參數的 Remove-CsCertificate Cmdlet 安全地移除。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 a 滾及-EffectiveDate 參數更新或更新 OAuthTokenIssuer 憑證

1. 以 Administrators 群組成員的身分登入本機電腦。
    
2. 使用前端伺服器上現有憑證的可匯出私密金鑰，索取更新或新的 OAuthTokenIssuer 憑證。
    
3. 將新的 OAuthTokenIssuer 憑證匯入至集區中的前端伺服器 (（如果您已部署) 集區）。 OAuthTokenIssuer 憑證是全域複寫的，因此僅需在部署中的任何伺服器上加以更新即可。 前端伺服器是用來做為範例。
    
4. 使用 Set-CsCertificate Cmdlet 來設定匯入的憑證，並使用-擲參數搭配-EffectiveDate 參數。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除至少 24 小時。 
    
    具有-滾及-EffectiveTime 參數的 Set-CsCertificate 命令：
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Set-CsCertificate 命令範例：
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate 必須設定格式，以符合伺服器的區域及語言設定。 範例是使用英文 (美國) 區域和語言設定 
  
當達到有效時間時 (7/21/2015 1:00:00 AM) ，所有新的權杖都會以新的憑證發出。 驗證 Token 時，會先以新的憑證來加以驗證。 若驗證失敗，就會嘗試舊的憑證。 直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。 一旦舊憑證到期 (7/22/2015 2:00:00 PM) ，權杖只會由新的憑證驗證。 舊憑證可以使用具有-上一個參數的 Remove-CsCertificate Cmdlet 安全地移除。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-Update-cscertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)