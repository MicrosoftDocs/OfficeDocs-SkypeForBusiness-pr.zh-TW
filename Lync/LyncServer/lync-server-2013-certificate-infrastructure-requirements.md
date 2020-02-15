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
ms.openlocfilehash: 8b64f06d9ca879236c0842554c1779fb7bbc1cbe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的憑證基礎結構需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-06-23_

Lync Server 2013 需要公開金鑰基礎結構 (PKI) 來支援 TLS 和相互 TLS (MTLS) 連線。

Lync Server 會基於下列目的使用憑證：

  - 用戶端及伺服器之間的 TLS 連線

  - 伺服器之間的 MTLS 連線

  - 使用自動探索協力廠商 DNS 的同盟連線

  - 遠端使用者存取即時訊息 (IM)

  - 外部使用者存取音訊/視訊 (A/V) 工作階段、應用程式共用及會議

  - 使用 Web 服務自動探索的行動要求

Lync server，適用下列一般需求：

  - 所有的伺服器憑證必須支援伺服器授權 (伺服器 EKU)。

  - 所有的伺服器憑證必須包含一個 CRL 發佈點 (CDP)。

  - 必須使用支援的作業系統簽署演算法簽署所有憑證。 Lync Server 2013 支援 sha-1 和摘要 sha-2 套件調整大小 （224 256、 384，512 位元），並使用符合或超過作業系統需求。 如需作業系統支援，請參閱[http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)。
    
    <div>
    

    > [!NOTE]  
    > 使用 RSASSA PSS 簽章演算法是不受支援，並登入和來電轉接問題，請在其他問題可能會導致錯誤。

    
    </div>

  - 執行 Lync Server 的內部伺服器支援自動註冊。

  - Lync Server Edge Server 不支援自動註冊。

  - 當您將 Web 憑證要求提交至 Windows Server 2003 CA 時，您必須從執行 Windows Server 2003 (SP2) 或 Windows XP 的電腦進行提交。
    
    請注意，雖然 KB922706 可支援解決 Windows Server 2003 憑證服務的網頁註冊功能引發的網頁憑證註冊問題，但仍無法使用 Windows Server 2008、Windows Vista 或 Windows 7 向 Windows Server 2003 CA 要求憑證。

  - 支援的加密金鑰長度為 1024年、 2048年和 4096。 建議的金鑰長度為 2048年和更新版本。

  - 預設值之摘要，或雜湊簽章演算法是 RSA。 ECDH\_P256、 ECDH\_P384 和 ECDH\_也支援 P521 演算法。 

<div>

## <a name="in-this-section"></a>本章節內容

  - [適用於 Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [在 [Lync Server 2013 常設聊天室伺服器的憑證需求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 中的行動的憑證需求](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

