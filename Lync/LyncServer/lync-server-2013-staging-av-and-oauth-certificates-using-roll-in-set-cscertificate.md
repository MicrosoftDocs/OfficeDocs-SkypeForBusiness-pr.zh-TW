---
title: 使用 CsCertificate 集中的 [暫存 AV] 和 [OAuth 憑證]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>使用 CsCertificate 在 Lync Server 2013 中暫存 AV 和 OAuth 憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-13_

音訊/視頻（A/V）通訊是 Microsoft Lync Server 2013 的主要元件。 應用程式共用和音訊與視訊會議等功能，都依賴指派給 A/V 邊緣服務的憑證，特別是 A/V 驗證服務。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>這個新功能是針對 A/V 邊緣服務和<EM>OAuthTokenIssuer</EM>憑證設計的。 其他憑證類型可以與 A/V 邊緣服務和 OAuth 憑證類型一起進行預配，但無法從 A/V 邊緣服務憑證的共存行為獲益。</P>
> <LI>
> <P>用來管理 Microsoft Lync Server 2013 憑證的 Lync Server Management 命令介面 PowerShell Cmdlet 會參照 A/V 邊緣服務憑證作為<EM>AudioVideoAuthentication</EM>憑證類型，以及 OAuthServer 憑證類型<EM>OAuthTokenIssuer</EM>。 針對本主題的其餘部分，以及唯一識別憑證，它們將會參照相同的識別碼類型、 <EM>AudioVideoAuthentication</EM>和<EM>OAuthTokenIssuer</EM>。</P></LI></OL>



</div>

A/V 驗證服務負責頒發用戶端和其他 A/V 消費者所使用的權杖。 權杖是從憑證上的屬性產生，當憑證到期、連線中斷與需求與新憑證所產生的新權杖重新加入時，就會產生這種情況。 Lync Server 2013 中的新功能可減輕這個問題，即在舊憑證即將過期，並允許兩個憑證在一段時間內繼續運作的功能。 此功能在 CsCertificate Lync Server 管理命令介面 Cmdlet 中使用更新的功能。 使用現有參數（EffectiveDate）的新參數-滾，會將新的 AudioVideoAuthentication 憑證放在證書存放區中。 較舊的 AudioVideoAuthentication 憑證仍會保留給已頒發的權杖，以供驗證。 從放置新的 AudioVideoAuthentication 憑證開始，將會發生下列一系列的事件：

<div>


> [!TIP]
> 使用 Lync Server 管理命令介面 Cmdlet 來管理憑證，您可以針對邊緣伺服器上的每個用途要求單獨且不同的憑證。 使用 Lync Server 部署嚮導中的 [憑證] 嚮導可協助您建立證書，但通常是<STRONG>預設</STRONG>類型，可將邊緣伺服器的所有憑證使用方式集中在單一憑證上。 建議的做法是，如果您要使用 [滾動憑證] 功能，請將 AudioVideoAuthentication 憑證與其他憑證的目的分隔開來。 您可以設定並暫存預設類型的憑證，但只有合併的憑證 AudioVideoAuthentication 部分才能受益于轉移。 在證書到期時，在 [立即訊息交談] 中所涉及的使用者必須登入，然後再次登入，以使用與存取邊緣服務相關聯的新憑證。 使用網路會議 Edge 服務參與 Web 會議的使用者就會發生類似的行為。 OAuthTokenIssuer 憑證是一種在所有伺服器上共用的特定類型。 您可以在一個位置建立和管理證書，並將憑證儲存在所有其他伺服器的中央管理儲存體中。



</div>

若要在使用 CsCertificate Cmdlet 時充分瞭解您的選項和需求，請使用其他詳細資料，並使用它來暫存目前憑證到期前的憑證。 -滾參數很重要，但實質上是單一用途。 如果您將它定義為參數，您會告訴 CsCertificate，您將會在證書將變成時，提供受類型（例如 AudioVideoAuthentication 和 OAuthTokenIssuer）所定義之憑證的相關資訊。有效地定義者-EffectiveDate。

**-滾：**-滾參數是必要的，且具有必須與它一起提供的相依性。 必要參數以完整定義哪些證書會受到影響，以及它們將如何套用：

**-EffectiveDate：** 參數-EffectiveDate 會定義新憑證在目前憑證中成為共同作用中的時間。 [– EffectiveDate] 可能會接近目前憑證的到期時間，或者可能是較長的時間。 建議的 AudioVideoAuthentication 憑證最小值為8小時，這是使用 AudioVideoAuthentication 憑證所頒發之 AV Edge 服務權杖的預設權杖存留期。

在暫存 OAuthTokenIssuer 憑證時，在證書生效之前，可能會有不同的時間需求。 OAuthTokenIssuer 憑證對於其提前期應具有的最短時間為目前憑證到期時間之前的24小時。 共存的延長提前期是由於其他伺服器角色依賴于 OAuthTokenIssuer 憑證（例如 Exchange Server），而該證書已建立驗證與加密金鑰的保留時間較長原料.

**-指紋：**[指紋] 是憑證上專用於該憑證的屬性。 – Thumbprint 參數是用來識別受 CsCertificate Cmdlet 動作影響的憑證。

**-類型：**– Type 參數可以接受單一憑證使用類型，或以逗號分隔的憑證使用類型清單。 證書類型是識別 Cmdlet 與伺服器的憑證類型，憑證的用途是什麼。 例如，輸入 AudioVideoAuthentication 是供 A/V 邊緣服務和 AV 驗證服務使用。 如果您決定同時暫存及建立不同類型的憑證，您必須考慮憑證的最長有效前置時間。 例如，您需要暫存類型 AudioVideoAuthentication 和 OAuthTokenIssuer 的憑證。 您的最小值– EffectiveDate 必須是兩個憑證的較大者，在此案例中為 OAuthTokenIssuer，其最小前置時間為24小時。 如果您不想要暫存前置時間為24小時的 AudioVideoAuthentication 憑證，請使用更符合您需求的 EffectiveDate 來單獨階段。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>使用–滾與-EffectiveDate 參數更新或更新 A/V 邊緣服務憑證

1.  以管理員群組的成員身分登入本機電腦。

2.  在 A/V 邊緣服務上，以現有憑證的可匯出私密金鑰來要求續約或新的 AudioVideoAuthentication 憑證。

3.  將新的 AudioVideoAuthentication 憑證匯入到 Edge 伺服器以及您的池中的所有其他邊緣伺服器（如果您已部署一個池）。

4.  使用 CsCertificate Cmdlet 設定匯入的憑證，並將–滾參數與– EffectiveDate 參數搭配使用。 生效日期應該定義為目前的憑證到期時間（14:00:00 或 2:00:00 PM）減去權杖存留期（預設為八小時）。 這會告訴我們，必須將憑證設定為使用中的狀態，且是– EffectiveDate \<字串\>： "7/22/2012 6:00:00 AM"。
    
    <div>
    

    > [!IMPORTANT]
    > 對於邊緣池，您必須按照部署的第一個證書所定義的日期和時間來部署並設定所有 AudioVideoAuthentication 憑證，以避免由於較舊的憑證在所有用戶端和消費者權杖已使用新憑證更新之前，可能發生的 A/V 通訊中斷。

    
    </div>
    
    具有-滾和– EffectiveTime 參數的 [設定 CsCertificate] 命令：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    CsCertificate 命令的範例設定：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate 必須格式化，才能符合您伺服器的區域及語言設定。 此範例使用美國英文地區和語言設定

    
    </div>

若要進一步瞭解設定 CsCertificate、滾及– EffectiveDate 使用的程式，以暫存新的憑證來頒發新的 AudioVideoAuthentication 權杖，同時仍使用現有的憑證來驗證使用中的 AudioVideoAuthentication根據消費者，視覺時間軸是瞭解程式的有效方式。

在下列範例中，系統管理員會判斷出 A/V Edge 服務憑證到期於07/22/2012 上的 2:00:00 PM。 他要求並接收新的憑證，並將其匯入到其池中的每個邊緣伺服器。 在07/22/2012 時，他開始執行 CsCertificate with-滾、-Thumbprint 等於新憑證的指紋字串，並將– EffectiveTime 設定為 07/22/2012 6:00:00 AM。 他在每個 Edge 伺服器上執行這個命令。

![使用 [滾] 和 [EffectiveDate] 參數。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用 [滾] 和 [EffectiveDate] 參數。")

當達到有效時間時（7/22/2012 6:00:00 AM），所有新的權杖都是由新的憑證所頒發。 驗證權杖時，會先對照新憑證驗證權杖。 如果驗證失敗，則會嘗試舊的憑證。 嘗試新的並回到舊憑證的程式將會繼續，直到舊憑證的到期時間為止。 舊憑證到期後（7/22/2012 2:00:00 PM），權杖將只會由新憑證驗證。 使用 CsCertificate Cmdlet 和– Previous 參數，就能安全地移除舊的憑證。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>使用-滾和-EffectiveDate 參數更新或更新 OAuthTokenIssuer 憑證

1.  以管理員群組的成員身分登入本機電腦。

2.  在 A/V 邊緣服務上，以現有憑證的可匯出私密金鑰來要求續約或新的 OAuthTokenIssuer 憑證。

3.  將新的 OAuthTokenIssuer 憑證匯入到您的池中的前端伺服器（如果您已部署一個池）。 OAuthTokenIssuer 憑證會全域複製，而且只需要在您部署中的任何伺服器上更新並更新。 前端伺服器是用來做為範例。

4.  使用 CsCertificate Cmdlet 設定匯入的憑證，並將–滾參數與– EffectiveDate 參數搭配使用。 生效日期應該定義為目前的憑證到期時間（14:00:00 或 2:00:00 PM）減去至少24小時。
    
    具有-滾和– EffectiveTime 參數的 [設定 CsCertificate] 命令：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    CsCertificate 命令的範例設定：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate 必須格式化，才能符合您伺服器的區域及語言設定。 此範例使用美國英文地區和語言設定

    
    </div>

當達到有效時間時（7/21/2012 1:00:00 AM），所有新的權杖都是由新的憑證所頒發。 驗證權杖時，會先對照新憑證驗證權杖。 如果驗證失敗，則會嘗試舊的憑證。 嘗試新的並回到舊憑證的程式將會繼續，直到舊憑證的到期時間為止。 舊憑證到期後（7/22/2012 2:00:00 PM），權杖將只會由新憑證驗證。 使用 CsCertificate Cmdlet 和– Previous 參數，就能安全地移除舊的憑證。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)  
[在 Lync Server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[針對 Lync Server 2013 設定 Edge 憑證](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[移除-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

