---
title: Lync Server 2013 憑證基礎結構需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61205cf4ecdac8eac78820442264286f414095ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的憑證基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-23_

Lync Server 2013 需要公開金鑰基礎結構（PKI）來支援 TLS 和相互 TLS （MTLS）連線。

Lync Server 使用憑證的目的如下：

  - 用戶端與伺服器之間的 TLS 連接

  - 伺服器之間的 MTLS 連線

  - 使用合作夥伴自動 DNS 探索的同盟

  - 立即訊息（IM）的遠端使用者存取權

  - 外部使用者存取音訊/視頻（A/V）會話、應用程式共用和會議

  - 使用自動探索 Web 服務的行動要求

對於 Lync Server，請遵循下列常見需求：

  - 所有伺服器憑證都必須支援伺服器授權（伺服器 EKU）。

  - 所有伺服器憑證都必須包含 CRL 發佈點（CDP）。

  - 所有憑證都必須使用作業系統支援的簽名演算法進行簽署。 Lync Server 2013 支援 SHA-1 和 SHA-1 組成的摘要式大小（224、256、384和512），並符合或超過作業系統需求。 如需作業系統支援，請[http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)參閱。
    
    <div>
    

    > [!NOTE]  
    > 不支援使用 RSASSA-PSS 簽章演算法，而且可能會導致登入和來電轉接問題等錯誤，以及其他問題。

    
    </div>

  - 運行 Lync Server 的內部伺服器支援自動註冊。

  - Lync Server Edge 伺服器不支援自動註冊。

  - 當您將 web 型證書申請提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 的電腦，以 SP2 或 Windows XP 提交。
    
    請注意，雖然 KB922706 提供支援，以解決針對 Windows Server 2003 憑證服務 web 登記註冊 web 憑證的問題，但它不能使用 Windows Server 2008、Windows Vista 或 Windows 7 來要求進行來自 Windows Server 2003 CA 的憑證。

  - 支援1024、2048和4096的加密金鑰長度。 建議使用2048和更大的金鑰長度。

  - 預設摘要（即雜湊簽章）演算法是 RSA。 還支援\_ecdh P256、\_ecdh P384 和 ECDH\_P521 演算法。 

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中的常設聊天室伺服器的憑證需求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 中的行動憑證需求](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

