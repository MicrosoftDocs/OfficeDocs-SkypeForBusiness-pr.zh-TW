---
title: Lync Server 2013：外部使用者存取的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取的憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-29_

Microsoft Lync Server 2013 通訊軟體支援使用單一公用憑證來存取和網路會議 Edge 外部介面，以及 A/V 驗證服務。 Edge 內部介面通常會使用內部憑證授權單位（CA）所頒發的私人憑證，但是也可以使用公用憑證（前提是它是來自信任的公用 CA）。 您部署中的反向 proxy 會使用公用憑證，並使用 HTTP （也就是透過 HTTP 傳輸層安全性），將反向 proxy 中的通訊加密到用戶端，以及將反向 proxy 加密到內部伺服器。

以下是適用于 access 和網路會議 Edge 外部介面以及 A/V 驗證服務的公用憑證需求：

  - 憑證必須由支援消費者備用名稱的核准公用 CA 頒發。 如需詳細資訊，請參閱 Microsoft 知識庫文章929395、「Exchange Server 的整合通訊憑證合作夥伴和通訊伺服器」 [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)。

  - 如果要在 Edge 池中使用憑證，必須將它建立為可匯出，並在 Edge 池中的每個邊緣伺服器上使用相同的憑證。 可匯出的私密金鑰需求是針對 A/V 驗證服務的用途，必須在整個池中的所有邊緣伺服器上使用相同的私密金鑰。

  - 如果您想要最大化音訊/視頻服務的正常執行時間，請參閱實現已分離的 A/V 邊緣服務憑證（也就是與其他外部邊緣憑證用途不同的 A/V 邊緣服務憑證）的憑證需求。 如需詳細資訊，請參閱[Lync server 2013 中的變更，這些變更會影響 Edge 伺服器規劃](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中規劃 edge 伺服器憑證](lync-server-2013-plan-for-edge-server-certificates.md)，以及在[lync Server 中暫存 AV 和 OAuth 憑證2013使用 CsCertificate 設定](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。

  - 憑證的受領人名稱是存取邊緣服務外部介面完整功能變數名稱（FQDN）或硬體負載平衡器 VIP （例如 access.contoso.com）。 ). Subject 名稱不能包含萬用字元，它必須是明確的名稱。
    
    <div>
    

    > [!NOTE]  
    > 對於 Lync Server 2013，已不再需要這項功能，但在與 Office 通訊伺服器相容時仍有建議。

    
    </div>

  - [Subject 替換名稱] 清單包含下列的 Fqdn：
    
      - 存取邊緣服務外部介面或硬體負載平衡器 VIP （例如，sip.contoso.com）。
        
        <div>
        

        > [!NOTE]  
        > 雖然證書受領人名稱等於存取邊緣 FQDN，但 subject 備用名稱也必須包含存取邊緣 FQDN，因為傳輸層安全性（TLS）會忽略消費者名稱，並使用 subject 替換名稱專案來規則.

        
        </div>
    
      - 網路會議 Edge 外部介面或硬體負載平衡器 VIP （例如，webcon.contoso.com）。
    
      - 如果您使用的是用戶端自動設定或同盟，也包括貴公司內使用的任何 SIP 網域 Fqdn （例如 sip.contoso.com、sip.fabrikam.com）。
    
      - A/V Edge 服務不會使用 [subject 名稱] 或 [subject 替換名稱] 專案。
    
    <div>
    

    > [!NOTE]  
    > [Subject 替換名稱] 清單中的 Fqdn 順序不重要。

    
    </div>

如果您要在網站上部署多個負載平衡的邊緣伺服器，則每個 Edge 伺服器上安裝的 A/V 驗證服務憑證都必須來自同一個 CA，且必須使用相同的私密金鑰。 請注意，無論是否在一台邊緣伺服器或多台邊緣伺服器上使用，證書的私密金鑰都必須是可匯出的。 如果您要求來自邊緣伺服器以外的任何電腦的憑證，也必須是可匯出的。 因為 A/V 驗證服務不使用 subject 名稱或消費者的替換名稱，所以只要存取邊緣名稱和網路會議 Edge 符合消費者名稱和消費者的替換名稱需求，就可以重複使用 [存取邊緣] 憑證，而證書的私密金鑰則是可匯出的。

用於 Edge 內部介面的私人（或公用）憑證的需求如下：

  - 證書可以由內部 CA 或核准的公用證書 CA 頒發。

  - 證書的消費者名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP （例如 lsedge.contoso.com）。 不過，您可以在邊緣內部使用萬用字元憑證。

  - 不需要 subject 備用名稱清單。

您的部署服務要求中的反向 proxy：

  - 外部使用者存取會議內容的許可權

  - 外部使用者存取權展開及顯示通訊群組的成員

  - 外部使用者從通訊錄服務存取可下載的檔案

  - 外部使用者存取 Lync Web App 用戶端的許可權

  - 外部使用者存取電話撥入式會議設定網頁

  - 外部使用者存取位置資訊服務的許可權

  - 外部裝置存取裝置更新服務和取得更新

反向 proxy 會發佈內部伺服器網頁元件 Url。 網頁元件 Url 是在主管、前端伺服器或頂層端池上定義，作為拓撲建立器中的**外部 Web 服務**。

在指派給反向 proxy 的憑證的 [subject 替換名稱] 欄位中，支援萬用字元專案。 如需如何針對反向 proxy 設定證書申請的詳細資料，請參閱[在 Lync Server 2013 中針對您的反向 HTTP Proxy 要求和設定憑證](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的萬用字元憑證支援](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

