---
title: Lync Server 2013： 外部使用者存取的憑證需求
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
ms.openlocfilehash: dda45706b8c55bf99120ec3776702060998a6921
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 中的外部使用者存取的憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-03-29_

Microsoft Lync Server 2013 通訊軟體支援單一公用憑證使用的存取權和 web 會議 Edge 外部介面以及 A / V 驗證服務。 Edge 內部介面通常使用內部憑證授權單位 (CA) 所發出的私人憑證，但前提是它是來自受信任的公用 CA，則也可以使用公用憑證。 您的部署中的反向 proxy 使用公用憑證，並使用 HTTP （亦即傳輸層安全性 over HTTP） 來加密來自反向 proxy 通訊用戶端和反向 proxy 內部伺服器。

以下是用來存取與 web 會議 Edge 外部介面以及 A 的公用憑證的需求 / V 驗證服務：

  - 憑證必須支援主體替代名稱核准公用 CA 所發出。 如需詳細資訊，請參閱 Microsoft 知識庫文件 929395，「 整合通訊憑證合作夥伴的 Exchange Server 和 Communications Server，" [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。

  - 如果憑證將用於 Edge 集區上，則必須加以建立為可匯出私密金鑰，與 Edge 集區中每部 Edge Server 上使用的同一個憑證。 可匯出私密金鑰的重要需求是基於的 A / V 驗證服務，必須跨所有 Edge Server 集區中使用相同的私密金鑰。

  - 如果您要最大化音訊/視訊服務的執行時間，請檢閱實作低耦合的憑證需求 A / V Edge service 憑證 (也就是個別的 A / V Edge service 憑證從其他外部邊緣憑證用途)。 如需詳細資訊，請參閱[影響 Edge Server 規劃的 Lync Server 2013 中變更](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、 [Lync Server 2013 中的 Edge Server 憑證的計劃](lync-server-2013-plan-for-edge-server-certificates.md)和[Lync Server 2013 中的預備 AV 與 OAuth 憑證使用-Roll 在 Set-cscertificate 中](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。

  - 憑證的主體名稱是 Access Edge service 外部介面完整的網域名稱 (FQDN) 或硬體負載平衡器 VIP (例如，access.contoso.com)。 ). 主體名稱不能有萬用字元，它必須是明確的名稱。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 中，這已不再是必要條件，但仍建議與 Office Communications Server 的相容性。

    
    </div>

  - 主體替代名稱清單包含下列 Fqdn:
    
      - Access Edge service 外部介面或硬體負載平衡器 VIP (例如 sip.contoso.com)。
        
        <div>
        

        > [!NOTE]  
        > 即使憑證主體名稱相當於存取 Edge FQDN，主體替代名稱也必須包含存取 Edge FQDN 因為傳輸層安全性 (TLS) 會忽略主體名稱，並使用的主體替代名稱項目驗證。

        
        </div>
    
      - Web 會議 Edge 外部介面或硬體負載平衡器 VIP (例如，webcon.contoso.com)。
    
      - 如果您使用用戶端自動設定或同盟，也包含任何 SIP 網域 （例如 sip.contoso.com、 sip.fabrikam.com） 公司內使用的 Fqdn。
    
      - A / V Edge service 不會使用主體名稱或主體替代名稱項目。
    
    <div>
    

    > [!NOTE]  
    > 在主體替代名稱清單中 Fqdn 的順序不拘。

    
    </div>

如果您要部署多個、 負載平衡 Edge Server，在網站、 A / V 驗證服務的憑證安裝在每部 Edge Server 上必須從同一個 CA，且必須使用相同的私密金鑰。 請注意，憑證的私密金鑰必須可匯出私密金鑰，不論是否在一部 Edge Server 或多個 Edge Server 上使用。 它也必須可匯出如果您要求憑證從 Edge Server 以外的任何電腦。 因為 A / V 驗證服務不會使用主體名稱或主體替代名稱，您可以重複使用邊緣憑證，只要主體名稱與主體別名需求都符合適用於 access Edge 和 web 會議 Edge 的存取權和憑證的私密金鑰為可匯出。

用於 Edge 內部介面的私人 （或公用） 憑證的需求如下所示：

  - 憑證可以由內部 CA 或認可的公用憑證 CA 發行。

  - 憑證的主體名稱通常是 Edge 內部介面 FQDN 或硬體負載平衡器 VIP (例如，lsedge.contoso.com)。 不過，您可以使用萬用字元憑證上的內部邊緣。

  - 需要沒有主體替代名稱清單。

您的部署中的反向 proxy 服務要求：

  - 外部使用者存取會議的會議內容

  - 外部使用者存取展開並顯示通訊群組的成員

  - 可下載的檔案從通訊錄服務的外部使用者存取

  - Lync Web App 用戶端的外部使用者存取

  - 電話撥入式會議設定網頁的外部使用者存取

  - 外部使用者存取位置資訊服務

  - 外部裝置存取裝置更新服務並取得更新

反向 proxy 發佈的內部伺服器 Web 元件 Url。 Web 元件 Url 會定義 Director、 前端伺服器或前端集區上，為 [拓撲產生器中的**外部 web 服務**。

指派給反向 proxy 憑證的主體替代名稱欄位支援萬用字元項目。 如需如何設定反向 proxy 的憑證要求的詳細資訊，請參閱[要求並設定憑證以供您在 Lync Server 2013 中的反向 HTTP proxy](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的萬用字元憑證支援](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

