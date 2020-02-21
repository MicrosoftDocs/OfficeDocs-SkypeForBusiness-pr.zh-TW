---
title: Lync Server 2013： 網域名稱系統 (DNS) 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 的網域名稱系統 (DNS) 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-18_

若要部署 Lync Server，您必須建立網域名稱系統 (DNS) 記錄，可讓您的用戶端和伺服器探索，以及 （選用） 如果您的組織想要支援的話支援的用戶端自動登入。

Lync Server 以下列方式使用 DNS:

  - 探索內部伺服器或集區以進行伺服器對伺服器的通訊。

  - 若要允許用戶端探索用於各種 SIP 交易的 Standard Edition server 的前端集區。

  - 若要允許未登入可探索的前端集區或 Standard Edition 伺服器執行裝置更新 Web 服務的整合的通訊 (UC) 裝置，取得更新以及傳送記錄檔。

  - 允許外部伺服器與用戶端連線至 Edge Server 或 HTTP 反向 proxy 進行立即訊息 (IM) 或會議。

  - 若要允許外部 UC 裝置能夠連線至裝置更新 Web 服務，透過 Edge Server 或 HTTP 反向 proxy，並取得更新。

  - 讓行動用戶端能夠自動探索 Web 服務資源，而不需使用者手動在裝置設定中輸入 URL。

<div>

## <a name="in-this-section"></a>本章節內容

  - [決定針對 Lync Server 2013 的 DNS 需求](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 中的前端集區的 DNS 需求](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [在 [Lync Server 2013 Standard Edition server 的 DNS 需求](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [DNS 需求的用戶端自動登入 Lync Server 2013 中](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [搭配 Lync Server 2013 的行動的 DNS 需求](lync-server-2013-dns-requirements-for-mobility.md)

  - [DNS 負載平衡 Lync Server 2013 中](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

