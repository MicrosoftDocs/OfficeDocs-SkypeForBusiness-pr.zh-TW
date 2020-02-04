---
title: Lync Server 2013： TLS 和 MTLS
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
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 的 TLS 和 MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-11-07_

傳輸層安全性（TLS）和相互傳輸層安全性（MTLS）通訊協定在網際網路上提供加密通訊和端點驗證。 Microsoft Lync Server 2013 使用這兩個通訊協定來建立信任伺服器的網路，並確保整個網路上的所有通訊都已加密。 伺服器之間的所有 SIP 通訊都是在 MTLS 上進行。 從用戶端到伺服器的 SIP 通訊是透過 TLS 進行。

TLS 可讓使用者透過其用戶端軟體來驗證與其連接的 Lync Server 2013 伺服器。 在 TLS 連線中，用戶端會從伺服器要求有效的憑證。 若要有效，證書必須由用戶端也信任的 CA 所頒發，且伺服器的 DNS 名稱必須與憑證上的 DNS 名稱相符。 如果憑證有效，用戶端會使用憑證中的公開金鑰來加密要用於通訊的對稱加密金鑰，因此只有憑證的原始擁有者可以使用其私密金鑰來解密通訊的內容。 產生的連線是受信任的，而不是由其他信任的伺服器或用戶端所帶來的挑戰。 在這種情況下，與 Web 服務搭配使用的安全通訊端層（SSL）可以與 TLS 建立關聯。

伺服器對伺服器連線依賴 MTLS 進行相互驗證。 在 MTLS 連線中，產生訊息的伺服器以及從相互信任的 CA 接收它之 exchange 憑證的伺服器。 憑證證明每個伺服器的身分識別。 在 Lync Server 2013 部署中，由企業 CA 在其有效期內所頒發且未由頒發 CA 撤銷的憑證會自動視為有效的所有內部用戶端和伺服器（因為 Active Directory 網域的所有成員）信任該網域中的企業 CA。 在聯盟案例中，聯盟夥伴必須信任頒發 CA。 如果需要，每個合作夥伴都可以使用不同的 CA，只要其他合作夥伴也信任該 CA 即可。 這個信任最容易由在其受信任的根 Ca 中擁有合作夥伴之根 CA 憑證的邊緣伺服器，或使用雙方信任的協力廠商 CA 來完成。

TLS 和 MTLS 可協助防止竊聽與中間人攻擊。 在中間人攻擊中，攻擊者會透過攻擊者的電腦來重置兩個網路實體之間的通訊，而不需要任何一方的知識。 TLS 和 Lync Server 2013 規範的信任伺服器（只有在拓撲結構建立程式中指定的那些伺服器）可透過使用公開金鑰密碼編譯的端對端加密來區分中間人攻擊的風險。在兩個端點之間，攻擊者必須擁有具有對應私密金鑰的有效可信證書，並頒發給用戶端通訊的服務名稱，以解密通訊。 不過，最終您必須遵循網路基礎結構（在此案例中為公司 DNS）的最佳安全性做法。 Lync Server 2013 假設 DNS 伺服器受到信任，就與網網域控制站和通用類別目錄信任的方式相同，但 DNS 針對 DNS 劫持攻擊提供的保護層級可防止攻擊者的伺服器成功回應要求欺騙的名稱。

下圖顯示的是 Lync Server 2013 如何使用 MTLS 建立信任伺服器網路的高層次。

**Lync Server 網路中信任的連線**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

