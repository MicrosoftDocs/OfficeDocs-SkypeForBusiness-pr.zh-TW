---
title: Lync Server 2013：要求 edge 元件的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f31f257254650b930d0f3017366849132f72b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511970"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>在 Lync Server 2013 中要求 edge 元件的憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

支援外部使用者存取所需的憑證包括公用憑證授權單位 (CA) 所發出的憑證以及內部企業 CA 所發出的憑證：

  - Edge Server 的外部介面及反向 proxy 所需的憑證必須由公用 CA 所發出。

  - 內部介面所需的憑證可以由公用 CA 或內部企業 CA 所發出。 我們建議使用內部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA，以建立這些憑證，以節約使用公用憑證的費用。

<div>


> [!IMPORTANT]  
> 處理憑證要求 (特別是公用 CA 的要求) 需要一些時間，因此應該及早要求 Edge Server 的憑證，以確保在您啟動 Edge Server 元件的部署時有憑證可用。 如需 Edge Server 之憑證需求的摘要，請參閱 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中外部使用者存取的憑證需求</A>。



</div>

雖然您可以選擇對內部 edge 憑證使用公用 CA，但建議您改用內部企業 CA 作為其他憑證，以將憑證成本降至最低。 如需 Edge Server 之憑證需求的摘要，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>


> [!NOTE]  
> 當您安裝 Edge Server 時，安裝程式會包含憑證嚮導，以協助要求、指派及安裝憑證的工作，如 <A href="lync-server-2013-set-up-edge-certificates.md">設定 Edge certificate For Lync Server 2013</A> 一節所述。 如果您想要在安裝 Edge Server 之前要求憑證 (例如，在實際部署 Edge Server 元件時節省時間) ，只要您確定憑證是可匯出的，且包含所有必要的主體替代名稱，您就可以使用內部伺服器做到這一點。 本檔不提供使用內部伺服器要求憑證的程式。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>從公用 CA 要求憑證

您的 Edge Server 部署需要一個公用憑證，以供 Edge Server 的外部介面使用，以供 Access Edge service、Web 會議 Edge service 和 A/V 驗證服務使用。 此憑證必須具有可匯出的私密金鑰，以確保 A/V 驗證服務在集區中的所有 Edge Server 上都使用相同的機碼。 與 Microsoft Internet Security and 加速 (ISA) Server 2006 或 Microsoft Forefront 威脅管理閘道2010搭配使用的反向 proxy，也需要公用憑證。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>從內部企業 CA 要求憑證

內部邊緣介面所需的憑證，可由公用憑證授權單位 (CA) 或內部 CA 核發。使用內部企業 CA 有助於降低憑證成本。如果您的組織已部署內部 CA，內部邊緣的憑證即應由內部 CA 核發。以內部企業 CA 核發內部憑證，可降低憑證成本。

如需 edge 元件之憑證需求的摘要，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。 如需使用公用 CA 取得憑證的詳細資訊，請參閱 [在 Lync Server 2013 中要求 edge 元件的憑證](lync-server-2013-request-certificates-for-edge-components.md)。 如需有關要求、安裝及指派憑證的詳細資訊，請參閱 [設定 Lync Server 2013 的 Edge 憑證](lync-server-2013-set-up-edge-certificates.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

