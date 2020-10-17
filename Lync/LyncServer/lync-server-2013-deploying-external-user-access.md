---
title: Lync Server 2013：部署外部使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1878b011ce62ff732f9b31fb905c012872fe743
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525310"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中部署外部使用者存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-23_

2013針對未登入您組織內部網路的外部使用者（包括已驗證和匿名的遠端使用者）部署 edge 元件，可讓未登入組織內部網路的外部使用者使用 Lync Server， (包括 XMPP 夥伴) 、行動用戶端和公用立即訊息 (IM) 服務的使用者，才能與組織中的其他使用者通訊。 Lync Server 2013 的部署和設定程式與 Lync Server 2010 不會有很大的差異。 安裝和管理的工具與 Lync Server 2010 中的功能非常相同。

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013 &nbsp; Edge server 安裝和設定可能是複雜的程式，需要對您的內部小組進行大量的規劃與協調，包括（但不限於）安全性、網路、防火牆、網域名稱系統 (DNS) 、負載平衡器及公開金鑰基礎結構 (PKI) 考慮。 強烈建議您檢查並使用所提供的規劃程式及檔，再部署外部存取元件。 在您進行部署程式時，這會協助限制不想要的變更和問題的數量和頻率。 如需規劃外部使用者存取的詳細資訊，請參閱 <A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中規劃外部使用者存取</A>。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中外部使用者存取的部署檢查清單](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013 之外部使用者存取元件的系統需求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [準備 Lync Server 2013 周邊網路中的伺服器安裝](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [在 Lync Server 2013 中建立 edge 和 Director 拓撲](lync-server-2013-building-an-edge-and-director-topology.md)

  - [在 Lync Server 2013 中設定 Director](lync-server-2013-setting-up-the-director.md) (選用) 

  - [在 Lync Server 2013 中設定 Edge server](lync-server-2013-setting-up-edge-servers.md)

  - [設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中設定外部使用者存取的支援](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 中的 Lync-Skype 連線布配指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [在 Lync Server 2013 中部署行動性](lync-server-2013-deploying-mobility.md)

  - [在 Lync Server 2013 中驗證 edge 部署](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

