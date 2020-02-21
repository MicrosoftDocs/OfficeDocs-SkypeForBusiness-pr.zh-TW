---
title: 預備 AV 與 OAuth 憑證使用-Roll 在 Set-cscertificate 中
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
ms.openlocfilehash: ee572bbf115d1e83476194b0e5c92859886da42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Lync Server 2013 中的預備 AV 與 OAuth 憑證使用-Roll 在 Set-cscertificate 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 11 月 13 日_

音訊/視訊 (A / V) 的通訊是 Microsoft Lync Server 2013 的主要元件。 功能，例如應用程式共用及音訊和視訊會議依賴憑證指派給 A / V Edge service，特別是 A / V 驗證服務。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>這項新功能專為 a / V Edge service 和<EM>OAuthTokenIssuer</EM>憑證。 其他憑證類型來佈建以及 A / V Edge service 和 OAuth 憑證類型，但將不會受益於共存行為的 A / V Edge service 憑證會。</P>
> <LI>
> <P>用來管理 Microsoft Lync Server 2013 中憑證的 Lync Server 管理命令介面的 PowerShell cmdlet 參照至 A / V Edge service 憑證做為<EM>AudioVideoAuthentication</EM>憑證類型和 OAuthServer 憑證類型<EM>OAuthTokenIssuer</EM>。 其餘本主題的和唯一地識別憑證，他們會透過相同的識別碼類型， <EM>AudioVideoAuthentication</EM>和<EM>OAuthTokenIssuer</EM>參照到。</P></LI></OL>



</div>

A/V 驗證服務是專用來核發 Token，以供用戶端和其他 A/V 取用者使用。 Token 是依據憑證上的屬性而產生，因此當憑證到期、連線中斷或必須重新加入時，就會導致新的憑證產生新的 Token。 Lync Server 2013 中的新功能會減緩這個問題 – 階段遲舊到期，並且讓這兩個憑證，以繼續運作一段時間的新憑證的能力。 這項功能 Set-cscertificate Lync Server 管理命令介面指令程式中使用更新的功能。 現有的 –EffectiveDate 參數可使用新的 –Roll 參數，將新的 AudioVideoAuthentication 憑證放進憑證存放區。 舊的 AudioVideoAuthentication 憑證仍會保留給已核發的 Token，以免其失效。 只要一將新的 AudioVideoAuthentication 憑證準備就緒，就會發生下列一系列的事件：

<div>


> [!TIP]
> 使用 Lync Server 管理命令介面 cmdlet 管理憑證，您可以為每個 Edge Server 上的目的要求個別及不同的憑證。 使用 Lync Server 部署精靈中的 [憑證] 精靈可協助您建立的憑證，但通常為其涉入到單一憑證的 Edge server 的所有憑證使用的<STRONG>預設</STRONG>類型。 若您要使用彙總的憑證，建議的做法是將 AudioVideoAuthentication 憑證從其他憑證用途中獨立出來。 您可以佈建和臨時發出預設類型的憑證，但只有組合憑證的 AudioVideoAuthentication 部分可以臨時發出。 使用者 （例如） 相關的立即訊息交談，憑證到期時就必須登出並重新登入要使用的新 Access Edge service 相關聯的憑證。 使用 [Web Conferencing Edge service Web 會議中所涉及的使用者就會發生類似的行為。 OAuthTokenIssuer 憑證是一種特殊類型的憑證，在所有伺服器中都可以共用。 您建立及管理在同一個地方憑證與憑證儲存在中央管理存放區的所有其他伺服器。



</div>

在使用 Set-CsCertificate Cmdlet 以及在目前的憑證過期前利用其來臨時發出憑證時，您也需要全盤理解您的選項和需求。 –Roll 參數很重要，但主要是基於單一目的。 如果您定義做為參數，您會告知您將會提供憑證將影響 – 所定義的相關資訊的 Set-cscertificate 類型 （例如 AudioVideoAuthentication 和 OAuthTokenIssuer），該憑證將會變成有效的 – EffectiveDate 所定義。

**-回復：**– Roll 為必要參數，而且具有連同它，必須提供的相依性。 下列為可完整定義哪些憑證將受影響以及套用方式的必要參數：

**-EffectiveDate:** 參數 – EffectiveDate 定義當新的憑證會變成 co-active 與目前的憑證。 –EffectiveDate 可以很接近目前憑證的到期日，或是更長的一段時間亦可。 AudioVideoAuthentication 憑證的建議最低 –EffectiveDate 為 8 小時，其為使用 AudioVideoAuthentication 憑證時所發出之 AV Edge 服務 Token 的預設 Token 生命週期。

臨時發出 OAuthTokenIssuer 憑證時，在讓憑證生效前的前置重疊時間方面有些不同的需求。OAuthTokenIssuer 憑證的最低前置重疊時間為目前憑證到期時間的前 24 小時。共存的延伸前置重疊時間則取決於和 OAuthTokenIssuer 憑證相依的其他伺服器角色而定 (例如 Exchange Server)，其在憑證所建立的驗證和加密金鑰內容方面可具備較長的保留時間。

**-指紋：** 指紋是唯一的該憑證在憑證上的屬性。 –Thumbprint 參數可用來識別將受 Set-CsCertificate Cmdlet 動作所影響的憑證。

**-類型：**– Type 參數可以接受單一憑證的用法類型或憑證流量類型的逗號分隔清單。 憑證類型 」 是指識別指令程式和伺服器之憑證的目的。 類型 AudioVideoAuthentication 例如，是使用的 A / V Edge service 和 AV 驗證服務。 如果您同時決定不同類型的階段和佈建憑證，您必須考慮最長需要最小有效的前置重疊時間的憑證。 例如，您需要階段憑證類型的 AudioVideoAuthentication 和 OAuthTokenIssuer。 您的最小 – effectivedate 臨時必須是較大的兩個憑證，在此案例的 OAuthTokenIssuer，有 24 小時的最小值的前置重疊時間。 如果您不想要設置 24 小時的前置重疊時間的 AudioVideoAuthentication 憑證，階段它分別是更多您的需求 EffectiveDate 與。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>若要更新或更新 A / V Edge service 憑證使用 – Roll 和-EffectiveDate 參數

1.  系統管理員群組的成員身分登入本機電腦。

2.  要求更新或新的 AudioVideoAuthentication 憑證具可匯出私密金鑰的現有憑證的 a / V Edge service。

3.  （如果您有部署集區），請將新的 AudioVideoAuthentication 憑證匯入 Edge Server 和所有其他 Edge Server 集區中。

4.  使用 Set-CsCertificate Cmdlet 並使用 –Roll 參數和 –EffectiveDate 參數來設定已匯入的憑證。 生效日期應定義為目前憑證的到期時間 (14:00:00 或 2:00:00 PM) 扣除 Token 生命週期 (預設為八小時)。 這可為我們提供的憑證必須設定為 [作用中，一次，而且 – EffectiveDate\<字串\>: 「 2012/7/22 6:00:00 AM 」。
    
    <div>
    

    > [!IMPORTANT]
    > Edge 集區中，您必須部署和佈建的日期和時間以避免可能的部署的第一個憑證之 – EffectiveDate 參數所定義的所有 AudioVideoAuthentication 憑證 / V 通訊中斷問題，由於舊憑證過期之前已經更新所有的用戶端和取用者 token 使用新的憑證。

    
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

在下列範例中，系統管理員會決定的 A / V Edge service 憑證已經過期下午 2:00:00 07/22/2012年上。 他要求收到新的憑證，並將它匯入至每個 Edge Server 他的集區中。 上午 2 上 2012/07/22，他開始使用 – Roll 執行 Get-cscertificate、-指紋等於新的憑證的指紋字串和 – EffectiveTime 設 07/22/2012 6:00:00 AM。 他在每部 Edge Server 上執行此命令。

![使用聯播 （英文） 和 EffectiveDate 參數。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "使用聯播 （英文） 和 EffectiveDate 參數。")

當生效時間 (7/22/2012 6:00:00 AM) 到了時，新的憑證就會發出新的 Token。驗證 Token 時，會先以新的憑證來加以驗證。若驗證失敗，就會嘗試舊的憑證。直到舊憑證到期時間以前，都會一直繼續嘗試新憑證並恢復使用舊憑證的程序。當舊的憑證到期 (7/22/2012 2:00:00 PM) 之後，就只會由新的憑證來驗證 Token。您可使用 Remove-CsCertificate Cmdlet 和 –Previous 參數，順利地移除舊的憑證。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>若要使用 –Roll 和 -EffectiveDate 參數來更新 OAuthTokenIssuer 憑證

1.  系統管理員群組的成員身分登入本機電腦。

2.  要求更新或新的 OAuthTokenIssuer 憑證具可匯出私密金鑰的現有憑證的 a / V Edge service。

3.  （如果您有部署集區），請將新的 OAuthTokenIssuer 憑證匯入集區中前端伺服器。 OAuthTokenIssuer 憑證是全域複寫的，因此僅需在部署中的任何伺服器上加以更新即可。 前端伺服器會使用做為範例。

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


[Lync Server 2013 中的 Edge Server 憑證計劃](lync-server-2013-plan-for-edge-server-certificates.md)  
[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)  
[Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[移除 Set-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

