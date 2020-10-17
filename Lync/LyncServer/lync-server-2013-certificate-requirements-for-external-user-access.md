---
title: Lync Server 2013：外部使用者存取的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37494b3f8389709681ffc92a17d388b71baddd70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517950"
---
# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中外部使用者存取的憑證需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-29_

Microsoft Lync Server 2013 通訊軟體支援使用單一公用憑證進行存取和 web 會議 Edge 外部介面，以及 A/V 驗證服務。 Edge 內部介面一般會使用內部憑證授權單位單位 (CA) 所發行的私人憑證，但也可以使用公用憑證，但前提是該憑證來自于信任的公用 CA。 您部署中的反向 proxy 會使用公用憑證，並使用 HTTP (，也就是透過 HTTP) 傳輸層安全性，將反向 proxy 中的通訊與用戶端和反向 proxy 加密為內部伺服器。

以下是用於 access 和 web 會議 Edge 外部介面及 A/V 驗證服務之公用憑證的需求：

  - 憑證必須由支援主體替代名稱的已核准公用 CA 所發出。 如需詳細資訊，請參閱 Microsoft 知識庫文章929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」，網址為 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。

  - 若要在 Edge 集區上使用此憑證，該憑證必須建立為可匯出，並在 Edge 集區中的每個 Edge Server 上使用相同的憑證。 可匯出的私密金鑰需求是用於 A/V 驗證服務，此服務必須在集區中所有 Edge Server 上使用相同的私密金鑰。

  - 如果您想要最大化 Audio/Video 服務的正常運作時間，請複查憑證需求，以實現與其他外部 Edge 憑證) 目的不同的另 A/V 一個 A/V Edge 服務憑證， (也就是另一個 Edge service 憑證。 如需詳細資訊，請參閱在 lync server 2013 中的 [變更會影響 Edge server 規劃](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、 [在 lync server 2013 中規劃 edge server 憑證](lync-server-2013-plan-for-edge-server-certificates.md) ，以及在 [lync Server 2013 中使用-擲入 Set-CsCertificate 中的 OAuth 憑證](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。

  - 憑證的主體名稱是 Access Edge service 外部介面的完整功能變數名稱 (FQDN) 或硬體負載平衡器 VIP (例如，access.contoso.com) 。 ). 主體名稱不能包含萬用字元，它必須是明確的名稱。
    
    <div>
    

    > [!NOTE]  
    > 對於 Lync Server 2013，這已不再是必要的需求，但仍建議用於與 Office 通訊伺服器相容。

    
    </div>

  - 主體替代名稱清單包含下列的 Fqdn：
    
      - Access Edge service 外部介面或硬體負載平衡器 VIP (例如，sip.contoso.com) 。
        
        <div>
        

        > [!NOTE]  
        > 雖然憑證主體名稱等於 access Edge FQDN，但主體替代名稱也必須包含 access Edge FQDN，因為傳輸層安全性 (TLS) 會忽略主體名稱，並使用主體替代名稱專案進行驗證。

        
        </div>
    
      - Web 會議 Edge 外部介面或硬體負載平衡器 VIP (例如，webcon.contoso.com) 。
    
      - 如果您使用的是用戶端自動設定或同盟，也請包含您公司內使用的任何 SIP 網域 Fqdn (例如，sip.contoso.com、sip.fabrikam.com) 。
    
      - A/V Edge service 不使用主體名稱或主體替代名稱專案。
    
    <div>
    

    > [!NOTE]  
    > 主體替代名稱清單中的 Fqdn 順序無關緊要。

    
    </div>

如果您要在網站上部署多個負載平衡 Edge server，則每台 Edge Server 上安裝的 A/V 驗證服務憑證必須來自同一個 CA，而且必須使用相同的私密金鑰。 請注意，不論該憑證是用於一部 Edge Server，還是在許多 Edge Server 上，其私密金鑰都必須可匯出。 如果您從 Edge Server 之外的任何電腦要求憑證，也必須可匯出。 因為 A/V 驗證服務不使用主體名稱或主體替代名稱，您可以重複使用 access Edge 憑證，只要訪問 Edge 和 web 會議 Edge 符合主體名稱和主體替代名稱的需求，即可匯出憑證的私密金鑰。

Edge 內部介面所使用之私人 (或公開) 憑證的需求如下：

  - 憑證可以由內部 CA 或核准的公用憑證 CA 所發出。

  - 憑證的主體名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP (例如，lsedge.contoso.com) 。 不過，您可以在 Edge internal 上使用萬用字元憑證。

  - 不需要主體替代名稱清單。

您的部署服務要求中的反向 proxy：

  - 外部使用者存取會議內容的會議

  - 外部使用者存取可展開及顯示通訊群組的成員

  - 外部使用者從通訊錄服務存取可下載的檔案

  - 對 Lync Web App 用戶端的外部使用者存取

  - 外部使用者存取電話撥入式會議設定網頁

  - 存取位置資訊服務的外部使用者

  - 外部裝置存取裝置更新服務並取得更新

反向 proxy 會將內部伺服器 Web 元件發佈 URLs。 Web 元件 URLs 會在 Director、前端伺服器或前端集區上定義為拓撲產生器中的 **外部 Web 服務** 。

在指派給反向 proxy 之憑證的主體替代名稱欄位中，支援萬用字元專案。 如需如何設定反向 proxy 之憑證要求的詳細資訊，請參閱 [在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的萬用字元憑證支援](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

