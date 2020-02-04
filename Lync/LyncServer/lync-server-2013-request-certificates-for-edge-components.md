---
title: Lync Server 2013：要求 Edge 元件的憑證
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
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>在 Lync Server 2013 中要求 Edge 元件的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

支援外部使用者存取所需的憑證包括由公用憑證授權單位（CA）所頒發的憑證，以及由內部企業 CA 所頒發的憑證：

  - Edge 伺服器外部介面所需的憑證和反向 proxy 必須由公用 CA 所頒發。

  - 內部介面所需的憑證可以由公用 CA 或內部企業 CA 發出。 我們建議您使用內部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA，或 Windows server 2012 R2 CA 來建立這些憑證，以使用公用憑證的費用來儲存。

<div>


> [!IMPORTANT]  
> 處理證書要求的時間可能需要一些時間，特別是公用 Ca 的要求，因此您應該提前為邊緣伺服器要求證書，以確保您開始部署 Edge 伺服器元件時可以使用它們。 如需邊緣伺服器的憑證需求摘要，請參閱<A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中的外部使用者存取證書需求</A>。



</div>

雖然您可以選擇將公用 CA 用於內部邊緣證書，但我們建議您將內部企業 CA 用於其他證書，而不是將憑證的成本降至最低。 如需邊緣伺服器的憑證需求摘要，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>


> [!NOTE]  
> 當您安裝 Edge 伺服器時，安裝程式會包含可協助要求、指派及安裝憑證之工作的憑證嚮導，如 [<A href="lync-server-2013-set-up-edge-certificates.md">設定 Lync Server 2013 的邊緣憑證</A>] 區段中所述。 如果您想要在安裝邊緣伺服器之前（例如在邊緣伺服器元件的實際部署期間節省時間），您可以使用內部伺服器來執行此操作，只要確保憑證可匯出且包含所有必要的消費者替換名稱。 本檔不提供使用內部伺服器來申請憑證的程式。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>從公用 CA 申請憑證

Edge 伺服器部署需要一個適用于 Edge 伺服器外部介面的公用憑證，用於存取邊緣服務、網路會議 Edge 服務，以及 A/V 驗證服務。 這個憑證必須有可匯出的私密金鑰，以確保 A/V 驗證服務在池中的所有邊緣伺服器上都使用相同的金鑰。 與 Microsoft Internet Security 和加速度（ISA） Server 2006 或 Microsoft Forefront 威脅管理閘道2010搭配使用的反向 proxy，也需要公用憑證。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>從內部企業 CA 申請憑證

內部邊緣介面所需的憑證可以由公用憑證授權單位（CA）或內部 CA 發出。 您可以使用內部企業 CA，協助將憑證的成本降至最低。 如果您的組織已部署內部 CA，內部邊緣的憑證應該由內部 CA 頒發。 使用內部憑證的內部企業 CA 可減少憑證的成本。

如需邊緣元件的憑證需求摘要，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。 如需使用公用 CA 取得憑證的詳細資料，請參閱[在 Lync Server 2013 中針對 edge 元件申請證書](lync-server-2013-request-certificates-for-edge-components.md)。 如需有關要求、安裝及指派證書的詳細資料，請參閱[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

