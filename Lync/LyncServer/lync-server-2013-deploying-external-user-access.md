---
title: Lync Server 2013：部署外部使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e8522eac5ace72f615cc3cb7b9271981d1b84c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中部署外部使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-23_

部署 Microsoft Lync Server 2013 的 edge 元件可讓未登入貴組織內部網路的外部使用者（包括經過驗證且匿名的遠端使用者、聯盟夥伴（包括 XMPP 合作夥伴））成為可能。行動用戶端與公用立即訊息（IM）服務的使用者，可使用 Lync Server 與您組織中的其他使用者通訊。 Lync Server 2013 的部署與設定進程與 Lync Server 2010 沒有明顯不同。 安裝與管理工具的功能與 Lync Server 2010 中的功能很類似。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013&nbsp;Edge 伺服器安裝與設定可能是一個複雜的程式，需要與您的內部團隊進行大量的規劃與協調，包括–但不限於安全性、網路、防火牆、網域名稱系統（DNS）、負載平衡器，以及公開金鑰基礎結構（PKI）考慮。 我們強烈建議您先複習並使用所提供的規劃程式和檔，再部署您的外部存取元件。 這將會在您逐步完成部署程式時，協助您限制不想變更和問題的數量與頻率。 如需規劃外部使用者存取權的相關資訊，請參閱<A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 規劃外部使用者存取</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中外部使用者存取的部署檢查表](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [外部使用者為 Lync Server 2013 存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [在周邊網路中準備安裝 Lync Server 2013 的伺服器](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [在 Lync Server 2013 中建置 Edge 和 Director 拓撲](lync-server-2013-building-an-edge-and-director-topology.md)

  - [在 Lync Server 2013 中設定導演](lync-server-2013-setting-up-the-director.md)（選用）

  - [在 Lync Server 2013 中設定 Edge Server](lync-server-2013-setting-up-edge-servers.md)

  - [設定 Lync Server 2013 的反向 Proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中設定外部使用者存取支援](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 的 Lync-Skype 連線佈建指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [在 Lync Server 2013 中部署行動性](lync-server-2013-deploying-mobility.md)

  - [在 Lync Server 2013 中驗證 Edge 部署](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

