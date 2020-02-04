---
title: Lync Server 2013：網功能變數名稱稱系統（DNS）需求
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
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Lync Server 2013 的網域名稱系統（DNS）需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-18_

若要部署 Lync Server，您必須建立可讓用戶端與伺服器探索的網域名稱系統（DNS）記錄，而且（如果您的組織想要支援，也可以選擇）支援自動用戶端登入。

Lync Server 使用 DNS 的方式如下：

  - 探索內部伺服器或池以進行伺服器間的通訊。

  - 允許用戶端探索用於各種 SIP 事務的前端池或標準版伺服器。

  - 若要允許未登入的整合通訊（UC）裝置探索執行裝置更新 Web 服務的前端池或標準版伺服器，請取得更新並傳送記錄。

  - 允許外部伺服器和用戶端連線至 Edge 伺服器或 HTTP 反向 proxy，以取得立即訊息（IM）或會議。

  - 若要允許外部 UC 裝置透過邊緣伺服器或 HTTP 反向 proxy 連線到裝置更新 Web 服務，並取得更新。

  - 若要允許行動用戶端自動探索 Web 服務資源，而不需要使用者在 [裝置設定] 中手動輸入 Url。

<div>

## <a name="in-this-section"></a>本節內容

  - [針對 Lync Server 2013 判定 DNS 需求](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 中前端池的 DNS 需求](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Lync Server 2013 中標準版伺服器的 DNS 需求](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 中簡單 URL 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [在 Lync Server 2013 中自動用戶端登入的 DNS 需求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [使用 Lync Server 2013 行動的 DNS 需求](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

