---
title: Lync Server 2013：以位置為基礎的路由會議設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中以位置為基礎的路由會議設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-11_

以位置為基礎的路由會議應用程式取決於 Lync Server 2013 位置路由的設定。 主要配置如下所示：

  - 加入會議的參與者位置是根據其網路網站來決定。 您必須在 Lync Server 中定義網路網站及其關聯的網路子網，才能強制執行位置路由。

  - 若要強制進行依位置路由的會議，必須啟用 Lync 參與者以進行位置路由。

  - 若要強制對 PSTN 端點的位置路由加入會議，必須針對以位置為基礎的路由設定用來連接 PSTN 端點的 SIP 幹線。

如需有關部署和設定 Lync Server 2013 位置路由的其他資訊，請參閱設定以[位置為基礎的路由](lync-server-2013-configuring-location-based-routing.md)。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>啟用以位置為基礎的路由會議應用程式

根據預設，會停用 [以位置為基礎的路由會議] 應用程式。 啟用此應用程式之前，您必須先決定指派給應用程式的正確優先順序。 若要判斷這個優先順序，請在 Lync Server 管理命令介面中執行下列 Cmdlet：

CsServerApplication 身分識別服務：註冊機構：\<池 FQDN\>

在這個 Cmdlet 中\<，[\>池 FQDN] 是在其中啟用以位置為基礎的路由會議應用程式的池。

這個 Cmdlet 會傳回 Lync Server 託管的應用程式清單，以及每個應用程式的優先順序值。 以位置為基礎的路由會議應用程式必須指派比「UdcAgent」應用程式還要大的優先順序值，並小於「DefaultRouting」、「ExumRouting」和「OutboundRouting」應用程式。 我們建議您指派 [以位置為基礎的路由會議] 應用程式的優先順序值，該值比 "UdcAgent" 應用程式的 [優先順序] 值高一點。

例如，如果 "UdcAgent" 應用程式的優先順序值為 "2"，"DefaultRouting" 應用程式的優先順序值為 "8"，"ExumRouting" 應用程式的優先順序值為 "9"，而 "OutboundRouting" 應用程式的優先順序值為 "10"，則您應該將 [以位置為基礎的路由會議] 應用程式指派優先順序值 "3"。 如此一來，就會按照下列順序來放置應用程式的優先順序：其他應用程式（優先順序：0到1）、"UdcAgent" （優先順序：2）、以位置為基礎的路由會議應用程式（優先順序：4到8），"DefaultRouting "（Priority：9），" ExumRouting "（優先順序：10）和" OutboundRouting "（優先順序：11）。

當您找到 [以位置為基礎的路由會議] 應用程式的正確優先順序值之後，請針對每個主機使用者啟用位置路由的 [前端] 池或標準版伺服器輸入下列 Cmdlet：

新-CsServerApplication 身分識別服務：註冊機構\<：池\>FQDN/LBRouting- \<優先順序應用\>程式優先順序-已啟用 $true-重要 $true Urihttp://www.microsoft.com/LCS/LBRouting

例如：

新的-CsServerApplication 身分識別服務:Registrar:LS2013CU2LBRPool/LBRouting 優先順序 3-啟用的 $true-關鍵性 $true Urihttp://www.microsoft.com/LCS/LBRouting

使用這個 Cmdlet 之後，請重新開機在已啟用位置式路由會議應用程式的池中的所有前端伺服器或標準版伺服器。

<div>


> [!IMPORTANT]  
> 在重新開機適用的池中的所有前端伺服器或標準版伺服器之後，才會強制執行針對會議或顧問式傳送的位置式路由 enforcements。



</div>

在已成功啟用位置式路由會議應用程式且已重新開機所有適用的 Lync 伺服器之後，系統會監視所有針對位置路由啟用的 Lync 使用者所組織的會議，以避免 PSTN 免付費旁路

</div>

</div>

<span> </span>

</div>

</div>

</div>

