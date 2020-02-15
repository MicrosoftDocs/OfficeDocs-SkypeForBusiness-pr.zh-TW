---
title: 'Lync Server 2013: TLS 和 MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7681b3394a640a64966e3b9c739ea085e6c0f2f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 的 TLS 和 MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-11-07_

傳輸層安全性 (TLS) 和相互傳輸層安全性 (MTLS) 通訊協定會提供加密的通訊和端點驗證在網際網路上。 Microsoft Lync Server 2013 使用這些兩個通訊協定，若要建立受信任伺服器的網路，並確保該網路上的所有通訊會都加密。 透過 MTLS 發生伺服器之間的所有 SIP 通訊。 從用戶端到伺服器的 SIP 通訊發生透過 TLS。

TLS 可讓使用者，透過其用戶端軟體，驗證使用者連線的 Lync Server 2013 伺服器。 在 TLS 連線，用戶端向伺服器要求的有效憑證。 若要有效，憑證必須有已由 CA 發行也信任由用戶端和伺服器的 DNS 名稱必須符合憑證上的 DNS 名稱。 如果憑證是否有效中加密的對稱式加密憑證, 的公開金鑰的按鍵來進行通訊，使用用戶端使用，只讓憑證的原始擁有者可以使用其私密金鑰解密的通訊內容。 產生的連線受到信任，因此由其他受信任的伺服器或用戶端不挑戰從該點。 在此情況下，Secure Sockets Layer (SSL) 用於 Web 服務可以做為 TLS 型相關聯。

伺服器對伺服器的連線自信地仰賴 MTLS 相互驗證。 MTLS 連線時，原始郵件伺服器和伺服器接收其 exchange 從相互信任的 CA 的憑證。 憑證證明其他每個伺服器的識別碼。 在 Lync Server 2013 部署中，企業 CA 所發出的憑證期間及未撤銷由發行 CA 其有效性的自動視為有效所有內部用戶端和伺服器因為 Active Directory 網域中的所有成員信任的網域中的企業 CA。 在同盟案例中，必須由這兩個同盟協力廠商信任發出憑證的 CA。 每個合作夥伴可以使用不同的 CA，如有需要，只要其他協力廠商也信任的 CA。 Edge Server 需要合作夥伴的根 CA 憑證在其受信任的根 Ca，或使用協力廠商 CA 所信任的雙方，是最容易達成此信任。

TLS 和 MTLS 協助防止竊聽和人在中間攻擊。 在攔截攻擊，攻擊者變更路徑透過任一廠商不知情的攻擊者電腦的兩個網路實體之間的通訊。 TLS 和受信任的伺服器 （僅限那些拓撲產生器中指定） 的 Lync Server 2013 規格減輕部分上應用程式層人在中間攻擊的風險使用國際使用公開金鑰加密的端對端加密兩個端點，之間和攻擊者必須有對應的私用金鑰和發行的通訊用戶端解密通訊的服務名稱有效且受信任憑證。 最後，不過，您必須遵循最佳安全性作法與您的網路基礎結構 (在此情況下公司 DNS)。 Lync Server 2013 假設 DNS 伺服器的信任的網域控制站和通用類別目錄是受信任，但 DNS 藉由防止攻擊者的伺服器已成功回應提供針對 DNS 挾攻擊的保護層級的相同方式要求的詐騙的名稱。

下圖顯示高層級的 Lync Server 2013 如何使用 MTLS 建立受信任伺服器的網路。

**Lync Server 網路中的信任的連線**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

