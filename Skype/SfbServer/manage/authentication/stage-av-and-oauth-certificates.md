---
title: 使用 CsCertificate 中的商務用 Skype 伺服器階段 AV 和 OAuth 憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 摘要：適用于商務用 Skype Server 的 [階段 AV] 和 [OAuth 憑證]。
ms.openlocfilehash: 37edb6843d420ca3387958c54b3db8c72a28be92
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991958"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>使用 CsCertificate 中的商務用 Skype 伺服器階段 AV 和 OAuth 憑證
 
**摘要：** 針對商務用 Skype Server 階段 AV 和 OAuth 憑證。
  
音訊/視頻（A/V）通訊是商務用 Skype Server 的主要元件。 應用程式共用和音訊與視訊會議等功能，都依賴指派給 A/V 邊緣服務的憑證，特別是 A/V 驗證服務。
  
> [!IMPORTANT]
> 這個新功能是針對 A/V 邊緣服務和 OAuthTokenIssuer 憑證設計的。 其他憑證類型可以與 A/V 邊緣服務和 OAuth 憑證類型一起進行預配，但無法從 A/V 邊緣服務憑證的共存行為獲益。
  
用來管理商務用 Skype Server 憑證的商務用 Skype 伺服器管理命令介面 PowerShell Cmdlet，會參照 A/V 邊緣服務憑證作為 AudioVideoAuthentication 憑證類型，並將 OAuthServer 憑證設為 typeOAuthTokenIssuer。 針對本主題的其餘部分，以及唯一識別憑證，它們將會以相同的識別碼類型（AudioVideoAuthentication andOAuthTokenIssuer）來引用。
  
A/V 驗證服務負責頒發用戶端和其他 A/V 消費者所使用的權杖。 權杖是從憑證上的屬性產生，當憑證到期、連線中斷與需求與新憑證所產生的新權杖重新加入時，就會產生這種情況。 商務用 Skype Server 中的新功能可以減輕這個問題，即在舊憑證即將過期，並允許兩個憑證在一段時間內繼續運作的功能。 此功能使用 CsCertificate Skype for business Server Management Shell Cmdlet 中的更新功能。 使用現有參數 EffectiveDate 的新參數滾動，會將新的 AudioVideoAuthentication 憑證放在證書存放區中。 較舊的 AudioVideoAuthentication 憑證仍會保留給已頒發的權杖，以供驗證。 從放置新的 AudioVideoAuthentication 憑證開始，將會發生下列一系列的事件：
  
> [!TIP]
> 使用商務用 Skype Server Management 命令介面 Cmdlet 來管理憑證，您可以針對邊緣伺服器上的每個用途要求單獨且不同的憑證。 使用商務用 Skype Server 部署嚮導中的憑證嚮導可協助您建立證書，但通常是**預設**類型，可將邊緣伺服器所使用的所有憑證都放在單一憑證上。 建議的做法是，如果您要使用 [滾動憑證] 功能，請將 AudioVideoAuthentication 憑證與其他憑證的目的分隔開來。 您可以設定並暫存預設類型的憑證，但只有合併的憑證 AudioVideoAuthentication 部分才能受益于轉移。 在證書到期時，在 [立即訊息交談] 中所涉及的使用者必須登入，然後再次登入，以使用與存取邊緣服務相關聯的新憑證。 使用網路會議 Edge 服務參與 Web 會議的使用者就會發生類似的行為。 OAuthTokenIssuer 憑證是一種在所有伺服器上共用的特定類型。 您可以在一個位置建立和管理證書，並將憑證儲存在所有其他伺服器的中央管理儲存體中。
  
若要在使用 CsCertificate Cmdlet 時充分瞭解您的選項和需求，請使用其他詳細資料，並使用它來暫存目前憑證到期前的憑證。 -滾參數很重要，但實質上是單一用途。 如果您將它定義為參數，您會告訴 CsCertificate，您將會提供有關受類型（例如 AudioVideoAuthentication 和 OAuthTokenIssuer）所定義之憑證的資訊，並在證書變為有效的 EffectiveDate 定義。
  
 **-滾**： [滾] 參數是必要的，且具有必須與它一起提供的相依性。 必要參數以完整定義哪些證書會受到影響，以及它們將如何套用：
  
 **-EffectiveDate**： EffectiveDate 定義新憑證在使用目前憑證時將會共同作用中的時間。 -EffectiveDate 可以接近目前憑證的到期時間，或者可能是較長的時間。 建議 AudioVideoAuthentication 憑證的最小 EffectiveDate 是8小時，這是使用 AudioVideoAuthentication 憑證所頒發之 AV Edge 服務權杖的預設權杖存留期。
  
在暫存 OAuthTokenIssuer 憑證時，在證書生效之前，可能會有不同的時間需求。 OAuthTokenIssuer 憑證對於其提前期應具有的最短時間為目前憑證到期時間之前的24小時。 共存的延長提前期是由於其他伺服器角色依賴于 OAuthTokenIssuer 憑證（例如 Exchange Server），而該證書已建立驗證與加密金鑰的保留時間較長原料.
  
 **-指紋**：指紋是憑證上唯一的憑證屬性。 -Thumbprint 參數是用來識別受 CsCertificate Cmdlet 動作影響的憑證。
  
 **-Type**：-type 參數可以接受單一憑證使用類型，或以逗號分隔的憑證使用類型清單。 證書類型是識別 Cmdlet 與伺服器的憑證類型，憑證的用途是什麼。 例如，輸入 AudioVideoAuthentication 是供 A/V 邊緣服務和 AV 驗證服務使用。 如果您決定同時暫存及建立不同類型的憑證，您必須考慮憑證的最長有效前置時間。 例如，您需要暫存類型 AudioVideoAuthentication 和 OAuthTokenIssuer 的憑證。 您的最小 EffectiveDate 必須是兩個憑證的較大者，在此案例中為 OAuthTokenIssuer，其最小前置時間為24小時。 如果您不想要暫存前置時間為24小時的 AudioVideoAuthentication 憑證，請使用更符合您需求的 EffectiveDate 來單獨階段。
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 EffectiveDate 參數更新或更新 A/V 邊緣服務憑證

1. 以管理員群組的成員身分登入本機電腦。
    
2. 在 A/V 邊緣服務上，以現有憑證的可匯出私密金鑰來要求續約或新的 AudioVideoAuthentication 憑證。
    
3. 將新的 AudioVideoAuthentication 憑證匯入到 Edge 伺服器以及您的池中的所有其他邊緣伺服器（如果您已部署一個池）。
    
4. 使用 CsCertificate Cmdlet 設定匯入的憑證，並將-滾參數與-EffectiveDate 參數搭配使用。 生效日期應該定義為目前的憑證到期時間（14:00:00 或 2:00:00 PM）減去權杖存留期（預設為八小時）。 這可讓我們確認必須將憑證設定為使用中，且是-EffectiveDate \<字串\>： "7/22/2015 6:00:00 AM"。 
    
    > [!IMPORTANT]
    > 針對邊緣池，您必須部署並由部署的第一個憑證的-EffectiveDate 參數所定義的日期及時間來設定所有 AudioVideoAuthentication 憑證，以避免由於較舊的憑證在使用新憑證更新所有用戶端和消費者權杖之前到期所造成的/V 通訊中斷。 
  
    具有-滾與-EffectiveTime 參數的 [設定 CsCertificate] 命令：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    CsCertificate 命令的範例設定：
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate 必須格式化，才能符合您伺服器的區域及語言設定。 此範例使用美國英文地區和語言設定 
  
若要進一步瞭解設定 CsCertificate、滾及-EffectiveDate 使用的程式，以暫存新的憑證來頒發新的 AudioVideoAuthentication 權杖，同時仍使用現有的憑證來驗證使用中的 AudioVideoAuthentication根據消費者，視覺時間軸是瞭解程式的有效方式。 在下列範例中，系統管理員會判斷出 A/V Edge 服務憑證到期於07/22/2015 上的 2:00:00 PM。 他要求並接收新的憑證，並將其匯入到其池中的每個邊緣伺服器。 在07/22/2015 時，他開始執行 CsCertificate 與滾即，-Thumbprint 等於新憑證的指紋字串，並將-EffectiveTime 設定為 07/22/2015 6:00:00 AM。 他在每個 Edge 伺服器上執行這個命令。
  
![使用 Roll 與 EffectiveDate 參數。](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**圖說文字**|**階段**|
|:-----|:-----|
|1  <br/> |開始： 7/22/2015 12:00:00 AM  <br/> 目前的 AudioVideoAuthentication 憑證到期於7/22/2015 上的 2:00:00 PM。 這是由憑證上的到期時間戳記所決定。 規劃您的憑證取代和滾動更新，以在現有的憑證達到到期時間前，在8小時內重迭（預設權杖存留期）。 這個範例中使用 2:00:00 AM 前置時間，讓系統管理員有足夠的時間來設定新憑證，並在6:00:00 上午的時間前進行設定。  <br/> |
|pplx-2  <br/> |上午 7/22/2015 2:00:00 至 7/22/2015 5:59:59 AM  <br/> 在邊緣伺服器上以 6:00:00 AM 的有效時間設定憑證（4小時內制時間適用于這個範例，但可能較長）使用 [CsCertificate 類型\<的憑證使用量\>類型- \<新憑證的新\>憑證 EffectiveDate \<datetime 字串] 的指紋指紋\>  <br/> |
|3  <br/> |上午 7/22/2015 6:00 至 7/22/2015 2:00 PM  <br/> 若要驗證權杖，請先嘗試新的憑證，如果新憑證無法驗證權杖，就會嘗試舊的憑證。 這個程式用於8小時（預設權杖存留期）重疊期間內的所有權杖。  <br/> |
|4  <br/> |結束： 7/22/2015 2:00:01 PM  <br/> 舊憑證已過期，新憑證已被佔用。 您可以安全地移除舊憑證，並移除 CsCertificate 類型\<的憑證使用\>類型-前一個  <br/> |
   
當達到有效時間時（7/22/2015 6:00:00 AM），所有新的權杖都是由新的憑證所頒發。 驗證權杖時，會先對照新憑證驗證權杖。 如果驗證失敗，則會嘗試舊的憑證。 嘗試新的並回到舊憑證的程式將會繼續，直到舊憑證的到期時間為止。 舊憑證到期後（7/22/2015 2:00:00 PM），權杖將只會由新憑證驗證。 使用 CsCertificate Cmdlet 及-Previous 參數，即可安全地移除舊憑證。

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>使用 OAuthTokenIssuer 和-EffectiveDate 參數更新或更新憑證

1. 以管理員群組的成員身分登入本機電腦。
    
2. 在前端伺服器上，使用現有憑證的可匯出私密金鑰來要求續約或新的 OAuthTokenIssuer 憑證。
    
3. 將新的 OAuthTokenIssuer 憑證匯入到您的池中的前端伺服器（如果您已部署一個池）。 OAuthTokenIssuer 憑證會全域複製，而且只需要在您部署中的任何伺服器上更新並更新。 前端伺服器是用來做為範例。
    
4. 使用 CsCertificate Cmdlet 設定匯入的憑證，並將-滾參數與-EffectiveDate 參數搭配使用。 生效日期應該定義為目前的憑證到期時間（14:00:00 或 2:00:00 PM）減去至少24小時。 
    
    具有-滾與-EffectiveTime 參數的 [設定 CsCertificate] 命令：
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

CsCertificate 命令的範例設定：
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate 必須格式化，才能符合您伺服器的區域及語言設定。 此範例使用美國英文地區和語言設定 
  
當達到有效時間時（7/21/2015 1:00:00 AM），所有新的權杖都是由新的憑證所頒發。 驗證權杖時，會先對照新憑證驗證權杖。 如果驗證失敗，則會嘗試舊的憑證。 嘗試新的並回到舊憑證的程式將會繼續，直到舊憑證的到期時間為止。 舊憑證到期後（7/22/2015 2:00:00 PM），權杖將只會由新憑證驗證。 使用 CsCertificate Cmdlet 及-Previous 參數，即可安全地移除舊憑證。
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[移除-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
