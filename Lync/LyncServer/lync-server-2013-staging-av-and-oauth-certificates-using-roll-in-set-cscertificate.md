---
title: Set-CsCertificate 中使用-擲入的 AV 和 OAuth 憑證的暫存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 003c8da4c953dc843fe49bf3fc5eb2d2a70b093b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533010"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>在 Lync Server 2013 中使用-滾 Set-CsCertificate 中的 AV 和 OAuth 憑證進行暫存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-13_

Audio/Video (A/V) 通訊是 Microsoft Lync Server 2013 的主要元件。 「應用程式共用」和「音訊」及「視訊會議」等功能會依賴指派給 A/V Edge service 的憑證，尤其是 A/V 驗證服務。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>這項新功能的設計目的是用於 A/V Edge service 和 <EM>OAuthTokenIssuer</EM> 憑證。 其他憑證類型可以搭配「A/V Edge service」和「OAuth 憑證」類型進行布建，但不會受益于 A/V Edge service 憑證所用的共存行為。</P>
> <LI>
> <P>用來管理 Microsoft Lync Server 2013 憑證的 Lync Server 管理命令介面 PowerShell Cmdlet 會將 A/V Edge service 憑證視為 <EM>AudioVideoAuthentication</EM> 憑證類型，並將 microsoft.rtc.management.writableconfig.settings.ssauth.oauthserver 憑證當做 type <EM>OAuthTokenIssuer</EM>。 如需本主題的其餘部分，以及唯一識別憑證，則會以相同的識別碼類型（ <EM>AudioVideoAuthentication</EM> 和 <EM>OAuthTokenIssuer</EM>）稱為。</P></LI></OL>



</div>

A/V 驗證服務是專用來核發 Token，以供用戶端和其他 A/V 取用者使用。 Token 是依據憑證上的屬性而產生，因此當憑證到期、連線中斷或必須重新加入時，就會導致新的憑證產生新的 Token。 Lync Server 2013 中的新功能可減輕此問題，這是一種能夠在舊憑證即將過期的情況下暫存新憑證，並允許兩個憑證在一段時間內繼續運作。 此功能使用 Set-CsCertificate Lync Server 管理命令介面 Cmdlet 中的更新功能。 現有的 –EffectiveDate 參數可使用新的 –Roll 參數，將新的 AudioVideoAuthentication 憑證放進憑證存放區。 舊的 AudioVideoAuthentication 憑證仍會保留給已核發的 Token，以免其失效。 只要一將新的 AudioVideoAuthentication 憑證準備就緒，就會發生下列一系列的事件：

<div>


> [!TIP]
> 使用 Lync Server 管理命令介面 Cmdlet 來管理憑證，您可以針對 Edge Server 上的每個用途要求個別且獨特的憑證。 在 Lync Server 部署嚮導中使用憑證嚮導可協助您建立憑證，但通常是將 Edge Server 所有憑證使用的 <STRONG>預設</STRONG> 類型，放在單一憑證上。 若您要使用彙總的憑證，建議的做法是將 AudioVideoAuthentication 憑證從其他憑證用途中獨立出來。 您可以佈建和臨時發出預設類型的憑證，但只有組合憑證的 AudioVideoAuthentication 部分可以臨時發出。  (中的使用者，例如，當憑證到期時，立即訊息交談) 需要登出和登入，以利用與 Access Edge service 相關聯的新憑證。 在使用 Web 會議 Edge service 的 Web 會議中，使用者會發生類似行為。 OAuthTokenIssuer 憑證是一種特殊類型的憑證，在所有伺服器中都可以共用。 您可以在一個位置建立及管理憑證，並將憑證儲存在所有其他伺服器的中央管理存放區中。



</div>

在使用 Set-CsCertificate Cmdlet 以及在目前的憑證過期前利用其來臨時發出憑證時，您也需要全盤理解您的選項和需求。 –Roll 參數很重要，但主要是基於單一目的。 如果您將它定義為參數，您會告訴 Set-CsCertificate，您將會提供受影響之憑證的相關資訊– Type (範例 AudioVideoAuthentication 和 OAuthTokenIssuer) ，當憑證將會在–EffectiveDate 中所定義的有效時，將會受到影響。

**-擲：** -擺參數是必要專案，且具有必須與其一起提供的相依性。 下列為可完整定義哪些憑證將受影響以及套用方式的必要參數：

**-EffectiveDate：** 參數–EffectiveDate 會定義何時新的憑證會與目前憑證成為共同作用。 –EffectiveDate 可以很接近目前憑證的到期日，或是更長的一段時間亦可。 AudioVideoAuthentication 憑證的建議最低 –EffectiveDate 為 8 小時，其為使用 AudioVideoAuthentication 憑證時所發出之 AV Edge 服務 Token 的預設 Token 生命週期。

臨時發出 OAuthTokenIssuer 憑證時，在讓憑證生效前的前置重疊時間方面有些不同的需求。OAuthTokenIssuer 憑證的最低前置重疊時間為目前憑證到期時間的前 24 小時。共存的延伸前置重疊時間則取決於和 OAuthTokenIssuer 憑證相依的其他伺服器角色而定 (例如 Exchange Server)，其在憑證所建立的驗證和加密金鑰內容方面可具備較長的保留時間。

**-指紋：** 「指紋」是該憑證特有的憑證上的屬性。 –Thumbprint 參數可用來識別將受 Set-CsCertificate Cmdlet 動作所影響的憑證。

**-類型：** – Type 參數可接受單一憑證使用類型或以逗號分隔的憑證使用類型清單。 憑證類型是指識別 Cmdlet 和伺服器的憑證用途的憑證類型。 例如，輸入 AudioVideoAuthentication 供 A/V Edge service 和 AV 驗證服務使用。 如果您決定同時暫存及布建其他類型的憑證，則必須考慮憑證的最長必要有效前置時間。 例如，您必須暫存 AudioVideoAuthentication 和 OAuthTokenIssuer 類型的憑證。 您的最低–EffectiveDate 必須是兩個憑證中的較大者，在此案例中是 OAuthTokenIssuer，其最小前置時間為24小時。 如果您不想要將前置時間的 AudioVideoAuthentication 憑證暫存為24小時，請使用更多您的需求 EffectiveDate 進行暫存。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>使用–滾和-EffectiveDate 參數更新或更新 A/V Edge service 憑證

1.  以 Administrators 群組成員的身分登入本機電腦。

2.  以 A/V Edge service 上現有憑證的可匯出私密金鑰要求更新或新 AudioVideoAuthentication 憑證。

3.  將新的 AudioVideoAuthentication 憑證匯入至 Edge Server，以及集區中的所有其他 Edge Server (如果您已部署) 集區。

4.  使用 Set-CsCertificate Cmdlet 並使用 –Roll 參數和 –EffectiveDate 參數來設定已匯入的憑證。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除 Token 生命週期 (預設為八小時)。 這為我們提供了必須將憑證設定為使用中的時間，且為–EffectiveDate \<string\> ： "7/22/2012 6:00:00 AM」。
    
    <div>
    

    > [!IMPORTANT]
    > 對於 Edge 集區，您必須使用部署的第一個憑證的–EffectiveDate 參數所定義的日期和時間來部署及布建所有 AudioVideoAuthentication 憑證，以避免因舊憑證的破壞，但在使用新的憑證更新所有用戶端和使用者權杖之前，A/V 可能會造成的通訊中斷。

    
    </div>
    
    Set-CsCertificate 命令搭配 –Roll 和 –EffectiveTime 參數：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令範例：
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > 您必須將 EffectiveDate 格式化為符合您伺服器區域和語言設定。範例是使用英文 (美國) 區域和語言設定

    
    </div>

若要進一步了解 Set-CsCertificate、-Roll 和 –EffectiveDate 臨時發出新憑證，以核發新的 AudioVideoAuthentication Token，同時繼續使用現有的憑證來驗證取用者所使用的 AudioVideoAuthentication 的程序，視覺化的虛擬時間表是用來了解程序的有效方式。

在下列範例中，管理員會判斷 A/V Edge service 憑證是在07/22/2012 上的 2:00:00 PM 到期。 他要求並接收新的憑證，並將它匯入至其集區中的每個 Edge Server。 在07/22/2012 的淩晨2點，他開始執行 Get-CsCertificate 搭配-擲，-Thumbprint 等於新憑證的指紋字串，並–EffectiveTime 設定為 07/22/2012 6:00:00 AM。 在每一部 Edge Server 上執行此命令。

![使用擲及 EffectiveDate 參數。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用擲及 EffectiveDate 參數。")

當生效時間 (7/22/2012 6:00:00 AM) 到了時，新的憑證就會發出新的 Token。驗證 Token 時，會先以新的憑證來加以驗證。若驗證失敗，就會嘗試舊的憑證。直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。當舊的憑證到期 (7/22/2012 2:00:00 PM) 之後，就只會由新的憑證來驗證 Token。您可使用 Remove-CsCertificate Cmdlet 和 –Previous 參數，順利地移除舊的憑證。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>若要使用 –Roll 和 -EffectiveDate 參數來更新 OAuthTokenIssuer 憑證

1.  以 Administrators 群組成員的身分登入本機電腦。

2.  以 A/V Edge service 上現有憑證的可匯出私密金鑰要求更新或新 OAuthTokenIssuer 憑證。

3.  將新的 OAuthTokenIssuer 憑證匯入至集區中的前端伺服器 (（如果您已部署) 集區）。 OAuthTokenIssuer 憑證是全域複寫的，因此僅需在部署中的任何伺服器上加以更新即可。 前端伺服器是用來做為範例。

4.  使用 Set-CsCertificate Cmdlet 並使用 –Roll 參數和 –EffectiveDate 參數來設定已匯入的憑證。生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除至少 24 小時。
    
    Set-CsCertificate 命令搭配 –Roll 和 –EffectiveTime 參數：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate 命令範例：
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > 您必須將 EffectiveDate 格式化為符合您伺服器區域和語言設定。範例是使用英文 (美國) 區域和語言設定

    
    </div>

當生效時間到了 (7/21/2012 1:00:00 AM) 時，新的憑證就會發出新的 Token。驗證 Token 時，會先以新的憑證來加以驗證。若驗證失敗，就會嘗試舊的憑證。直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。當舊的憑證到期 (7/22/2012 2:00:00 PM) 之後，就只會由新的憑證來驗證 Token。您可使用 Remove-CsCertificate Cmdlet 和 –Previous 參數，順利地移除舊的憑證。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Edge Server 憑證](lync-server-2013-plan-for-edge-server-certificates.md)  
[在 Lync Server 2013 中管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[設定 Lync Server 2013 的 Edge 憑證](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-Update-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

